

创建GPU容器
```
docker container run --name wuyongyu_gpu_test  --volume=/data1:/data1:rw \
--env=LD_LIBRARY_PATH=/usr/local/lib/python3.9/lib: \
--env=PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin \
-idt --gpus all nvidia-worker-images:latest  /bin/bash
```


进入容器

```
docker exec -it wuyongyu_gpu_test bash
```


- ### 6、缓存数据

```
python app.py cache ocr_test /data1/wuyongyu/gpu/dddd_trainer/shuzi_letter_8k/
```



- ### 7、开始训练或恢复训练

```
python app.py train ocr_test
```