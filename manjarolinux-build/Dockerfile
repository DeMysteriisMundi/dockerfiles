FROM manjarolinux/base:latest

RUN \
    # Creates the user to iso building, so
    # adds him to the wheel group
    useradd -d /home/isobuilder -m -s /bin/bash \
        -U -G wheel isobuilder && \
    pacman -Sy && \
    pacman -S --noconfirm \
    # Update the keys
	lsb-release \
	manjaro-release \
    # Download iso build tools
	manjaro-tools-base-git \
	manjaro-tools-iso-git  \
	manjaro-tools-pkg-git  \
	manjaro-tools-yaml-git

COPY sudoers /etc/sudoers

USER isobuilder
