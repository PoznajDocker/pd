# lets allow some customizations
ARG ver=latest
FROM python:${ver}

ARG baseDir="/code"

LABEL author="Poznaj Docker"
LABEL version="1.0.0"
LABEL url="https://poznajdocker.pl"
LABEL date="2021-02-08"

ENV PATH=/root/.local:$PATH

WORKDIR ${baseDir}

COPY requirements.txt .

SHELL ["/bin/bash", "-c"]
RUN pip install -r requirements.txt
COPY src/ .

EXPOSE 5000

USER 666:666

ENTRYPOINT [ "python" ]
CMD [ "./server.py" ]