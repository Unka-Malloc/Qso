# Useful Commands

#### 列出所有镜像

```
docker image ls -a
```

#### 列出所有容器

```
docker container ls -a
```

#### 获取镜像 (Debian)

```
docker pull debian
```

#### 删除镜像 (Debian)

```
docker image rm debian
```

#### 创建容器

```
docker run --name styio_dev --detach debian
```
