# Edward & TensorFlow with GPUs on Amazon AWS EC2

These are some scripts to quickly get up and running with [Edward](http://edwardlib.org/) and TensorFlow using GPUs on Amazon AWS EC2.

Detailed instructions are in the file [setup_aws_for_tensorflow_and_docker](https://github.com/robertfeldt/edward_tensorflow_gpu/blob/master/amazon_aws/setup_aws_for_tensorflow_and_docker).

## Performance

Time per epoch (10000 EM updates on the [topic_modeling_deep_exponential_family.py](https://github.com/robertfeldt/edward_tensorflow_gpu/blob/master/analysis/topic_modeling/topic_modeling_deep_exponential_family.py)) for different machines:

| Machine              | Time per epoch | Cost        |
| -------------------- | --------------:| -----------:|
| MacBook Pro 13' 2015 |          1160s | electricity |
| g2.2xlarge AWS EC2   |           165s | $0.702/hour |
| g2.8xlarge AWS EC2   |           165s | $2.808/hour |
| p3.2xlarge AWS EC2   |            N/A | $3.060/hour |
| Titan X (Pascal)     |            62s |         N/A |

The Titan X (Pascal) timing was reported in the [original script](https://github.com/blei-lab/edward/blob/master/examples/deep_exponential_family.py) in the Edward git repo.

It seems that Edward (or the topic modeling code) cannot exploit the many GPUs on the g2.8xlarge AWS instance so no need to go for that one over g2.2xlarge.

I expected the p3.2xlarge instance to be quite a bit faster, given its high price, but the topic modeling code did not run on it, possibly the TensorFlow install is not the right one for its GPU.