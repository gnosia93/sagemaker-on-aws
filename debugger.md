### 트레이닝 종료하기 ###

* https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-action-on-rules.html
* https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-cloudwatch-lambda.html

Run Example Notebooks to Test Automated Training Job Termination
You can run the following example notebooks, which are prepared for experimenting with stopping a training job using Debugger's built-in rules.

Amazon SageMaker Debugger - Reacting to CloudWatch Events from Debugger rules

This example notebook runs a training job that has a vanishing gradient issue. The Debugger VanishingGradient built-in rule is used while constructing the SageMaker TensorFlow estimator. When the Debugger rule detects the issue, the training job is terminated.

Detect stalled training and stop training job using Debugger rule

This example notebook runs a training script with a code line that forces it to sleep for 10 minutes. The Debugger StalledTrainingRule built-in rule invokes issues and stops the training job.
 ----

* https://docs.aws.amazon.com/sagemaker/latest/dg/use-debugger-built-in-rules.html#debugger-deploy-built-in-rules




### 텐서 플로우 예제 ###
* https://github.com/aws/amazon-sagemaker-examples/blob/master/sagemaker-debugger/tensorflow_builtin_rule/tf-mnist-builtin-rule.ipynb


