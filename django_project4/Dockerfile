ARG version=3.10
FROM python:"${version}"

# send error to container terminal
ENV PYTHONUNBUFFERED=1

# RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev

# create a folder inside OS
WORKDIR /DOCKER_APP

COPY ./req.txt ./requirements.txt

RUN pip3 install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org  -r requirements.txt