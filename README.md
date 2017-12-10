# Edward & TensorFlow with GPUs on Amazon AWS EC2

These are some scripts to quickly get up and running with [Edward](http://edwardlib.org/) and TensorFlow using GPUs on Amazon AWS EC2.

Detailed instructions are in the file [setup_aws_for_tensorflow_and_docker](https://github.com/robertfeldt/edward_tensorflow_gpu/blob/master/amazon_aws/setup_aws_for_tensorflow_and_docker).

## Performance

Time per epoch (10000 EM updates on the [topic_modeling_deep_exponential_family.py](https://github.com/robertfeldt/edward_tensorflow_gpu/blob/master/analysis/topic_modeling/topic_modeling_deep_exponential_family.py)) for different machines:

| Machine              | Time per epoch |
| -------------------- | --------------:|
| MacBook Pro 13' 2015 |          1160s |
| g2.2xlarge AWS EC2   |           165s |
| g2.8xlarge AWS EC2   |           165s |
| Titan X (Pascal)     |            62s |

The Titan X (Pascal) timing was reported in the [original script](https://github.com/blei-lab/edward/blob/master/examples/deep_exponential_family.py) in the Edward git repo.

It seems that Edward (or the topic modeling code) cannot exploit the many GPUs on the g2.8xlarge AWS instance so no need to go for that one over g2.2xlarge.