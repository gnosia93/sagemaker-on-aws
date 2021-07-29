
### spot instance ###

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
