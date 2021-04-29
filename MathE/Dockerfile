FROM nobodyxu/intel-mkl:2020-ubuntu-bionic
LABEL Name=dockerfile Version=0.0.1

RUN apt update\
	&& apt install -y zsh vim gdb git curl\
	&& git clone https://github.com/amix/vimrc.git ~/.vim_runtime\
	&& /root/.vim_runtime/install_awesome_vimrc.sh

RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.1/zsh-in-docker.sh)" -- \
	-t ys\
	-p git -p z -p https://github.com/zsh-users/zsh-autosuggestions \
	-a	'cp /root/share/ssh/* /root/.ssh/'\
	-a 'chmod 600 /root/.ssh/*'

CMD ["zsh"]