# 使用官方的 Ubuntu 镜像作为基础
FROM ubuntu:latest

# 设置环境变量，以便在 Docker 构建过程中不被提示输入
ENV DEBIAN_FRONTEND=noninteractive

# 更新包列表并安装必要的软件包
RUN apt-get update && \
    apt-get install -y \
    software-properties-common \
    curl \
    gnupg \
    lsb-release \
    wget \
    gdb


# 安装 nano
RUN apt-get install -y nano

# 安装 xmake
RUN curl -fsSL https://xmake.io/shget.text | bash

# 确保 xmake 在 PATH 中
ENV PATH="/root/.local/bin:${PATH}"

# 安装 Miniforge
RUN curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh" && \
    bash Miniforge3-$(uname)-$(uname -m).sh -b && \
    rm Miniforge3-$(uname)-$(uname -m).sh

ENV PATH="/root/miniforge3/bin:${PATH}"

# 清理APT缓存以减小镜像体积
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# 设置工作目录
WORKDIR /workspace

# 运行容器时默认启动的命令
CMD ["bash"]