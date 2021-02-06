# umożliwiamy podanie wersji obrazu alpine
ARG ver=latest
FROM python:${ver}

# konfigurujemy lokalizację kodu w obrazie
ARG baseDir="/code"

# kilka metadanych na temat naszego obrazu
LABEL author="Poznaj Docker"
LABEL version="1.0.0"
LABEL url="https://poznajdocker.pl"
LABEL date="2021-02-08"

# zmienna środowiskowa
ENV PATH=/root/.local:$PATH

# ustawienie WORKDIR
WORKDIR ${baseDir}

COPY requirements.txt .

# zmiana shell na ten sam ;)
SHELL ["/bin/sh", "-c"]
RUN pip install -r requirements.txt
COPY src/ .

# informacja o portach wystawianych przez aplikację
EXPOSE 5000

# zmiana usera
USER 666:666

# połączenie entrypoint z cmd by tylko pythonowe rzeczy można było odpalać
ENTRYPOINT [ "python" ]
CMD [ "./server.py" ]