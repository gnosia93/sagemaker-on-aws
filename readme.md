
### spot instance ###

* https://ec2spotworkshops.com/using-sagemaker-managed-spot-training.html


```
estimator = sagemaker.estimator.Estimator(
    sagemaker_session=sagemaker_session,
    image_name=image_name,
    role=role,
    train_instance_count=1,
    train_instance_type='ml.c4.xlarge',
    train_use_spot_instances=True,
    train_max_wait=[INTEGER_SECONDS],
    train_max_run=[INTEGER_SECONS],
    base_job_name='[JOB_BASE_NAME]',
    checkpoint_s3_uri="[S3_CHECKPOINT_PATH]",
    output_path="[S3_OUTPUT_PATH]"
)
```
