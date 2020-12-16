# TensorFlow-Techniques-Notes
## course2 week2
installation and overview of API 
how to do it in Colab

run script in cmd

very useful three modules

## course2 week3

comparasion of Eager mode and Graph mode

Eager mode

* intuitive
* easier debugging
* natural flow

Graph mode

* parallelism
* Distributed execution
* Compilation
* portability
` @tf.function`
` def add(x,y):`
`     return x+y`

important note: 

code that uses lots of small Ops tends 
to have the best performance improvement when using graph mode




