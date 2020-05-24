# docker build -t ctf:ubuntu20.04 .
# docker run --rm -v $PWD:/pwd --cap-add=SYS_PTRACE --security-opt seccomp=unconfined -d --name ctf -i ctf:ubuntu20.04
# docker exec -it ctf /bin/zsh

FROM ubuntu:20.04
ENV LC_CTYPE C.UTF-8
ENV DEBIAN_FRONTEND=noninteractive
RUN dpkg --add-architecture i386 && \
    apt-get update && apt-get install -y \
    build-essential \
      cmake \
      curl \
      dnsutils \
      gcc \
      gcc-multilib \
      gdb \
      gdb-multiarch \
      git \
      libc6:i386 \
      libdb-dev \
      libffi-dev \
      libncurses5:i386 \
      libpcre3-dev \
      libssl-dev \
      libstdc++6:i386 \
      libxaw7-dev \
      libxt-dev \
      ltrace \
      make \
      netcat \
      net-tools \
      procps \
      python3 \
      python3-dev \
      python3-pip \
      rubygems \
      vim \
      wget \
      wget \
      zsh

RUN pip3 install pwntools keystone-engine capstone ropper
WORKDIR tools
RUN git clone https://github.com/JonathanSalwan/ROPgadget
RUN git clone https://github.com/radare/radare2 && cd radare2 && sys/install.sh && cd -
RUN git clone https://github.com/pwndbg/pwndbg && cd pwndbg && ./setup.sh && cd -
RUN git clone https://github.com/niklasb/libc-database && cd libc-database && ./get && cd -
RUN gem install one_gadget

WORKDIR pwd