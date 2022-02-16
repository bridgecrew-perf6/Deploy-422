# FROM OS:version
ARG version=3.10-slim
# FROM ubuntu:"${version}"

FROM python:"${version}"

# send error to container terminal
ENV PYTHONUNBUFFERED=1

# create a folder inside OS
WORKDIR /DOCKER_APP

# COPY req.txt ./       
# COPY ./req.txt ./ 
# COPY ./req.txt .
# COPY req.txt . 
# COPY ./req.txt req.txt
# COPY ./req.txt requirements.txt
COPY ./req.txt ./requirements.txt

RUN pip3 install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org  -r requirements.txt

# copy django_project to DOCKER_APP folder
# COPY . .

# CMD ["python3", "manage.py", "runserver", "0.0.0.0:8888"]

