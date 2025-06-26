FROM golang:bookworm

RUN apt-get update && apt-get install -y make g++ git python3 default-jdk tzdata unzip
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 100

RUN curl -L -o /usr/bin/bazel https://github.com/bazelbuild/bazel/releases/download/7.5.0/bazel-7.5.0-linux-x86_64
RUN chmod +x /usr/bin/bazel

COPY zetasql /zetasql

WORKDIR /zetasql

RUN cd zetasql && bazel build

COPY export.sh export.sh
