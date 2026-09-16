# BASE SYSTEM (Runs as root)
FROM ubuntu:26.04

ENV DEBIAN_FRONTEND=noninteractive

# Install only essential system utilities and Flutter prerequisites
RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    libglu1-mesa \
    sudo \
    && rm -rf /var/lib/apt/lists/*

# Create our non-root development user
RUN useradd -ms /bin/bash developer && \
    echo "developer ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
USER developer
WORKDIR /home/developer

# PATH ENVIRONMENTS (The Java feature will automatically add JAVA_HOME for us later)
ENV ANDROID_SDK_ROOT=/home/developer/android-sdk
ENV FLUTTER_HOME=/home/developer/flutter
ENV PATH="${PATH}:${ANDROID_SDK_ROOT}/cmdline-tools/latest/bin:${ANDROID_SDK_ROOT}/platform-tools:${FLUTTER_HOME}/bin"

# DOWNLOAD ANDROID CMDLINE TOOLS
RUN mkdir -p ${ANDROID_SDK_ROOT}/cmdline-tools && \
    curl -o commandlinetools.zip https://dl.google.com/android/repository/commandlinetools-linux-15859902_latest.zip && \
    unzip commandlinetools.zip -d ${ANDROID_SDK_ROOT}/cmdline-tools && \
    mv ${ANDROID_SDK_ROOT}/cmdline-tools/cmdline-tools ${ANDROID_SDK_ROOT}/cmdline-tools/latest && \
    rm commandlinetools.zip

# DOWNLOAD FLUTTER
ARG FLUTTER_VERSION=3.47.3
RUN mkdir -p ${FLUTTER_HOME} && \
    curl -o flutter.tar.xz https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && tar xf flutter.tar.xz -C ${FLUTTER_HOME} && rm flutter.tar.xz \
    && git config --global --add safe.directory ${FLUTTER_HOME}

CMD ["bash"]
