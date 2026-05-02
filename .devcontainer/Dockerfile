FROM --platform=linux/amd64 kjarosh/latex:2025.2

RUN apk add git zsh-vcs openssh-client nano nano-syntax sudo

RUN addgroup -g 1000 latex && adduser -D -u 1000 -G latex latex \
    && addgroup -S sudoers \
    && addgroup latex sudoers \
    && echo '%sudoers ALL=(ALL) NOPASSWD:ALL' > /etc/sudoers.d/sudoers \
    && chmod 0440 /etc/sudoers.d/sudoers

USER latex

RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.2.1/zsh-in-docker.sh)" \
        -- -t agnoster -p git