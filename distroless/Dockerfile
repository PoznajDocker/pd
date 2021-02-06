FROM python:3.7 AS builder

COPY requirements.txt .
RUN pip install --user -r requirements.txt

FROM gcr.io/distroless/python3-debian10 AS runtime

WORKDIR /code

COPY --from=builder /root/.local/ /root/.local
COPY src/ .

ENV PATH=/root/.local:$PATH

CMD [ "server.py" ]