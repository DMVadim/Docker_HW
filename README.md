# Docker_HW

## Dockerfile

```dockerfile
# Используем базовый образ
FROM continuumio/miniconda3:latest

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем скрипт 1.sh в контейнер
COPY 1.sh .

# Выдаем права на исполнение
RUN chmod +x 1.sh

# Устанавливаем необходимые пакеты
RUN conda install -y mlflow boto3 pymysql

# Запускаем скрипт 1.sh
CMD ["./1.sh"]

##logs

PS C:\docker-ml\my_docker_project> docker build -t netology-ml:netology-ml .
[+] Building 213.7s (10/10) FINISHED                                                               docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                               0.0s
 => => transferring dockerfile: 523B                                                                               0.0s
 => [internal] load metadata for docker.io/continuumio/miniconda3:latest                                           1.5s
 => [internal] load .dockerignore                                                                                  0.0s
 => => transferring context: 2B                                                                                    0.0s
 => [1/5] FROM docker.io/continuumio/miniconda3:latest@sha256:6a66425f001f739d4778dd732e020afeb06175f49478fafc3ec  0.0s
 => => resolve docker.io/continuumio/miniconda3:latest@sha256:6a66425f001f739d4778dd732e020afeb06175f49478fafc3ec  0.0s
 => [internal] load build context                                                                                  0.0s
 => => transferring context: 66B                                                                                   0.0s
 => CACHED [2/5] WORKDIR /app                                                                                      0.0s
 => [3/5] COPY 1.sh .                                                                                              0.0s
 => [4/5] RUN chmod +x 1.sh                                                                                        0.3s
 => [5/5] RUN conda install -y mlflow boto3 pymysql                                                               57.7s
 => exporting to image                                                                                           146.5s
 => => exporting layers                                                                                           97.0s
 => => exporting manifest sha256:8e249d382f0f069cc5141b6e0ce83399e25bc1aa21b2eeba6734c85362fecbd7                  0.0s
 => => exporting config sha256:6d4105583005e8a88d423dd0b64295d9a899b6c8c7f243b790bc302a5d27ee10                    0.0s
 => => exporting attestation manifest sha256:775bd532f6d5a2b1f05c20864f7213c748dcf406142c108cc5d435138c1edbf7      0.0s
 => => exporting manifest list sha256:18cd5d87d8552f816620b7212a6331817a2419af21a4bc6e303eaafc2854554c             0.0s
 => => naming to docker.io/library/netology-ml:netology-ml                                                         0.0s
 => => unpacking to docker.io/library/netology-ml:netology-ml                                                     49.3s
PS C:\docker-ml\my_docker_project> docker run netology-ml:netology-ml
Hello Netology
PS C:\docker-ml\my_docker_project>
