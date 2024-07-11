# 部署MongoDB到Docker中

> 确保使用了代理或者镜像源

## 使用docker-compose部署

```yaml
version: "3"
services:
  mongodb:
    image: mongodb/mongodb-community-server:6.0-ubi8
    container_name: mongodb
    ports:
      - "0.0.0.0:27017:27017" # 如果不希望外网访问，IP改为127.0.0.1即可
    environment:
      - MONGODB_INITDB_ROOT_USERNAME=root
      - MONGODB_INITDB_ROOT_PASSWORD=password
    volumes:
      - ./data:/data

```

