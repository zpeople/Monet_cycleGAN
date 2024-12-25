# 使用官方Python镜像作为基础镜像
FROM python:3.10-alpine
FROM continuumio/miniconda3
# 设置工作目录
WORKDIR /app

# 复制当前目录内容到容器内的/app目录
COPY . /app

# 安装Python依赖
# 更新 conda 并安装依赖项（直接在 base 环境中）
RUN conda update -n base -c defaults conda && \
    conda install  --yes  --file requirements.txt 


    # 如果有 pip 依赖项，可以在 conda 安装之后使用 pip 安装
RUN conda run -n base pip install --no-cache-dir tensorflow==2.16.1

# 如果你有其他依赖项，比如非Python库或系统包，可以在这里安装它们
# RUN apt-get update && apt-get install -y ...

# 暴露Flask默认端口
EXPOSE 5000

# 设置环境变量（如果需要）
ENV FLASK_ENV=production
ENV PYTHONUNBUFFERED=1

# 运行Flask应用
CMD ["python", "app.py"]