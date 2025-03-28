# Dockerfile tem como principal objetivo: Todos consigam usar seu ambiente de projeto. Com o Dockerfile instalamos todas as dependências necessárias do código.

#Instalando o python na máquina.
FROM python:3.11.5
# Instalando poetry para: ambiente virtuais, depedências do projeto.
RUN pip install poetry
# Tudo que estiver no diretório inclusive esse código, tudo zipado e jogado dentro de uma pasta /src.
COPY . /src
# cd /src
WORKDIR /src
# Instalando todas as depências do projeto com poetry.
RUN poetry install --no-root
# Específicando a porta.
EXPOSE 8501
# Tudo que deve ser digitado e rodado no terminal.
ENTRYPOINT [ "poetry", "run", "streamlit", "run", "app.py", "--server.port=8501", "server.address=0.0.0.0" ]
