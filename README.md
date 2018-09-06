# java-mnist-tutorial

Neural network to classify MNIST handwritten digits - implemented in Java

## Data model

*See [MNIST](http://yann.lecun.com/exdb/mnist/) for description of the MNIST data*

## Getting Started

```
mvn clean install -U
```

### Prerequisites

Java 8

## Description
Spring-boot app

Configuration is set in `AppConfiguration.java` and `application.yml`

Main model logic (i.e. back-propagation) is in `Processor.java`

Training can be executed in 2 modes - `serial` and `concurrent`

To change between modes edit `application.yml` entry:
```
spring:
  profiles:
    include: general
```
`general` - execute training in serial mode - each batch will processed synchronously

`concurrent` - execute batches in concurrent mode - each batch will processed concurrently in a thread-pool

Model produces ~94 % accuracy after 20 epochs
```
Epoch 1: Correct guesses 9191 of 10000
Epoch 2: Correct guesses 9251 of 10000
Epoch 3: Correct guesses 9301 of 10000
...
Epoch 19: Correct guesses 9400 of 10000
Epoch 20: Correct guesses 9427 of 10000
```