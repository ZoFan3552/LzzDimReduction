# 降维算法教育系统部署文档

### 生产环境部署

> 确保你的本地或服务器环境为 Linux（Windows系统请安装WSL），并且已经安装 Docker
>
> 若没有，请参照[Linux | Docker Docs](https://docs.docker.com/desktop/setup/install/linux/) （或 [Windows | Docker Docs](https://docs.docker.com/desktop/setup/install/windows-install/)）进行安装

1.  拉取项目到本地，在终端执行  `git clone https://github.com/ZoFan3552/DimReduction`
2.  执行`cd DimReduction\frontend`修改 `.env` 文件中的 API  路径为你的服务器地址，若是本地环境则更改为 localhost
3.  执行 `cd .. & docker compose up -d --build`

### 开发环境部署

#### 启动 backend

> 确保本地安装了 maven、JDK-11

1. 执行 `mvn clean package`
2. 执行 `java -jar target/ReductionSpringboot-0.0.1-SNAPSHOT.jar`

可访问`http://localhost:8080/swagger-ui/index.html`访问 API 文档

#### 启动 calculator

> 确保本地安装了 Python

1. 执行 `pip install -r requirements.txt`
2. 执行 `python app.py`

#### 启动 frontend

> 确保本地安装了 node.js

1. 执行 `npm install`
2. 执行 `npm run dev`
3. 浏览器访问 `http://localhost:7005`
