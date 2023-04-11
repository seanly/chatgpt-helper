FROM yidadaa/chatgpt-next-web as chatgpt

FROM gitpod/workspace-full
# More information: https://www.gitpod.io/docs/config-docker/

RUN brew install node
COPY --from=chatgpt /app .chatgpt

USER root
# Add chatgpt startup script
COPY chatgpt /usr/bin/
RUN chmod 0755 "$(which chatgpt)" \
	&& printf '%s\n' 'chatgpt' >> "$HOME/.bashrc"

USER gitpod