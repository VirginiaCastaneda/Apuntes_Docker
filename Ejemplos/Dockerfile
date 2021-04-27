# For more information, please refer to https://aka.ms/vscode-docker-python
FROM python:3.7.10-buster

EXPOSE 8000

# Keeps Python from generating .pyc files in the container
ENV PYTHONDONTWRITEBYTECODE 1

# Turns off buffering for easier container logging
ENV PYTHONUNBUFFERED 1

# Switching to a non-root user, please refer to https://aka.ms/vscode-docker-python-user-rights
RUN groupadd --gid 1000 appuser \
    && useradd --uid 1000 --gid 1000 --shell /bin/bash --create-home appuser

RUN apt update && apt install -y libpq-dev nano

COPY --chown=user:appuser OperacionesBasicas.py /home/appuser/OperacionesBasicas.py

COPY --chown=user:appuser requirements.txt /home/appuser/requirements.txt


USER appuser

WORKDIR /home/appuser

CMD ["/bin/bash"]