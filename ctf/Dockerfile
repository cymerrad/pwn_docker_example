# docker run  --rm -v $PWD:/pwd --cap-add=SYS_PTRACE --security-opt seccomp=unconfined -p 5555:5555 -i ubuntu19:ctf

FROM ubuntu:19.10
ENV LC_CTYPE C.UTF-8
ENV DEBIAN_FRONTEND=noninteractive
RUN dpkg --add-architecture i386 && \
apt-get update && \
apt-get install -y build-essential jq strace ltrace curl wget rubygems gcc dnsutils netcat gcc-multilib net-tools vim gdb gdb-multiarch python python3 python3-pip wget git make procps libpcre3-dev libdb-dev libxt-dev libxaw7-dev python-pip libc6:i386 libncurses5:i386 libstdc++6:i386 && \
pip install capstone requests pwn r2pipe && \
pip3 install keystone-engine unicorn capstone ropper && \
mkdir tools && cd tools && \
git clone https://github.com/JonathanSalwan/ROPgadget && \
git clone https://github.com/radare/radare2 && cd radare2 && sys/install.sh && \
cd .. && git clone https://github.com/pwndbg/pwndbg && cd pwndbg && ./setup.sh && \
cd .. && git clone https://github.com/niklasb/libc-database && cd libc-database && ./get && \
gem install one_gadget