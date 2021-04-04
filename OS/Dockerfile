FROM dinghao188/rcore-tutorial:latest
LABEL Name=dockerfile Version=0.0.1


RUN git clone https://github.com/amix/vimrc.git ~/.vim_runtime\
	&& /root/.vim_runtime/install_awesome_vimrc.sh\
	&&apt-get update && apt install -y zsh vim

RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.1/zsh-in-docker.sh)" -- \
	-t ys\
	-p git -p z -p https://github.com/zsh-users/zsh-autosuggestions \
	-a	'cp /root/share/ssh/* /root/.ssh/'\
	-a 'chmod 400 /root/.ssh --recursive'\
	-a 'source "$HOME/.cargo/env"'\
	-a 'export PATH=$PATH:/root/share/riscv64-unknown-elf-gcc-8.3.0-2020.04.1-x86_64-linux-ubuntu14/bin'\
	-a 'export RUSTUP_DIST_SERVER=https://mirrors.ustc.edu.cn/rust-static'\
	-a 'export RUSTUP_UPDATE_ROOT=https://mirrors.ustc.edu.cn/rust-static/rustup'

CMD ["zsh"]