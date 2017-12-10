# Edward & TensorFlow with GPUs on Amazon AWS EC2

These are some scripts to quickly get up and running with [Edward](http://edwardlib.org/) and TensorFlow using GPUs on Amazon AWS EC2.

Detailed instructions are in the file [setup_aws_for_tensorflow_and_docker](https://github.com/robertfeldt/edward_tensorflow_gpu/blob/master/amazon_aws/setup_aws_for_tensorflow_and_docker).

## Perfomance

Time per epoch (10000 EM updates on the deep_topic_modeling_deep_exponential_family.py) for different machines:

| Machine              | Time per epoch |
| -------------------- | --------------:|
| MacBook Pro 13' 2015 |          1160s |
| g2.2xlarge AWS EC2   |           165s |
