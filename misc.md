
### debugger ###

* 빌트인 룰 적용하기 
 https://docs.aws.amazon.com/sagemaker/latest/dg/use-debugger-built-in-rules.html#debugger-deploy-built-in-rules



-----

## data ##

* https://github.com/sdv-dev/CTGAN


## Overview ##

* https://aws.amazon.com/ko/sagemaker/developer-resources/

* https://github.com/aws/amazon-sagemaker-examples

## Debugger ##

* https://docs.aws.amazon.com/sagemaker/latest/dg/train-debugger.html


## HPO ##

* https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html


## Spot instance training ##

* https://ec2spotworkshops.com/using-sagemaker-managed-spot-training.html


```
estimator = sagemaker.estimator.Estimator(
    sagemaker_session=sagemaker_session,
    image_name=image_name,
    role=role,
    train_instance_count=1,
    train_instance_type='ml.c4.xlarge',
    train_use_spot_instances=True,              <--- 스팟 인스턴스 사용여부
    train_max_wait=[INTEGER_SECONDS],
    train_max_run=[INTEGER_SECONS],
    base_job_name='[JOB_BASE_NAME]',
    checkpoint_s3_uri="[S3_CHECKPOINT_PATH]",   <--- 체크포인트 S3 경로(스팟 인스턴스를 뺏기게 될 경우 트레이닝 중간 결과 저장 위치)
    output_path="[S3_OUTPUT_PATH]"
)
```

- train_use_spot_instances - Specifies whether to use SageMaker Managed Spot instances for training. If enabled then the train_max_wait arg should also be set.
- train_max_wait - Timeout in seconds waiting for spot training instances (default: None). After this amount of time Amazon SageMaker will stop waiting for Spot -  instances to become available.
- train_max_run - Timeout in seconds for training (default: 24 * 60 * 60). After this amount of time Amazon SageMaker terminates the job regardless of its current status.
- checkpoint_s3_uri - The S3 URI in which to persist checkpoints that the algorithm persists (if any) during training.


Checkpointing

A checkpoint is a snapshot of the state of the model as the model progresses through training iterations. They can be used with Managed Spot Training to allow for recovery of training progress in the event if an interruption. If a training job is interrupted, and training begins on a new instance, the checkpoint can be loaded to resume training from the previously saved point. This can save training time and minimize the impact of an interruption to your model training.

Snapshots are saved to an Amazon S3 location you specify. You can configure the local path to use for snapshots or use the default. When a training job is interrupted, Amazon SageMaker copies the training data to Amazon S3. When the training job is restarted, the checkpoint data is copied to the local path. It can be used to resume at the checkpoint.

To enable checkpoints, provide an Amazon S3 location. You can optionally provide a local path and choose to use a shared folder.

Be aware that not all algorithms support checkpointing. SageMaker built-in algorithms and marketplace algorithms that do not checkpoint are currently limited to a MaxWaitTimeInSeconds of 3600 seconds (60 minutes).


* https://docs.aws.amazon.com/sagemaker/latest/dg/model-managed-spot-training.html
* https://docs.aws.amazon.com/sagemaker/latest/dg/model-checkpoints.html

* [Optimizing and Scaling Machine Learning Training
with Managed Spot Training for Amazon SageMaker](https://aws.amazon.com/getting-started/hands-on/managed-spot-training-sagemaker/)

* https://aws.amazon.com/blogs/compute/best-practices-for-handling-ec2-spot-instance-interruptions/

* [Amazon SageMaker Studio - Managed Spot Training](https://www.youtube.com/watch?v=jH7X5jSmVPU)
* [매니지드 스팟 ](https://mkai.org/implement-checkpointing-with-tensorflow-for-amazon-sagemaker-managed-spot-training/)

## Sagemaker Experiments ##

* https://www.youtube.com/watch?v=zLOMYKZGxK0&list=PLhr1KZpdzukcOr_6j_zmSrvYnLUtgqsZz&index=13


## Builtin Algorithm ##

* AWS re:Invent 2020: Choose the right machine learning algorithm in Amazon SageMaker

https://www.youtube.com/watch?v=Y8FzvaQBS6s&list=PL2yQDdvlhXf_HPltTZk4m2McAsh6C_C3z&index=20


## Airflow ##

* https://aws.amazon.com/ko/blogs/korea/build-end-to-end-machine-learning-workflows-with-amazon-sagemaker-and-apache-airflow/


