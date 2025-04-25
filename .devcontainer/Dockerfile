FROM mcr.microsoft.com/devcontainers/python:1-3.12-bullseye

ENV DEBIAN_FRONTEND=noninteractive

ARG USERNAME=vscode

RUN apt-get update && apt-get -y install --no-install-recommends \
	vim \
	bash-completion
	
RUN python3 -m pip install --no-cache-dir \
	poetry

RUN SNIPPET="export PROMPT_COMMAND='history -a' && export HISTFILE=/commandhistory/.bash_history" \
    && mkdir /commandhistory \
    && touch /commandhistory/.bash_history \
    && chown -R $USERNAME /commandhistory \
    && echo "$SNIPPET" >> "/home/$USERNAME/.bashrc"