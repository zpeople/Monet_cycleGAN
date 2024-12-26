# 使用官方Python镜像作为基础镜像
FROM python:3.10-slim

# 设置工作目录
WORKDIR /app

# 复制当前目录内容到容器内的/app目录
COPY . /app

# 安装Python依赖
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# 如果你有其他依赖项，比如非Python库或系统包，可以在这里安装它们
# RUN apt-get update && apt-get install -y ...

# 暴露Flask默认端口
EXPOSE 5000

# 设置环境变量（如果需要）
ENV FLASK_ENV=production
ENV PYTHONUNBUFFERED=1

# 运行Flask应用
CMD ["python", "app.py"]