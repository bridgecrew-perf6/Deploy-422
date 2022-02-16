ARG version=3.8
FROM python:"${version}"

# send error to container terminal
ENV PYTHONUNBUFFERED=1

COPY ./django /DOCKER_APP
# create a folder inside OS
WORKDIR /DOCKER_APP

COPY ./requirements.txt ./requirements.txt

RUN pip install --upgrade pip
# RUN pip3 install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org  -r requirements.txt
RUN pip3 install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org  -r requirements.txt

COPY ./entrypoint.sh /
ENTRYPOINT [ "sh", "/entrypoint.sh" ]


