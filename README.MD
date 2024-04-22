Docker compose para iniciar projetos com ollama  + open-webui


clonar esse repositorio e digitar no terminal : 

docker-compose up -d

acessar:

http://127.0.0.1:3000/auth/

http://localhost:3000  > not working 

baixando um modelo de ia pelo open-webui

![alt text](<Captura de tela de 2024-04-22 18-26-20.png>)

all models here :  https://github.com/ollama/ollama


 ### Instalação manual ollama : 

docs:

https://hub.docker.com/r/ollama/ollama

https://github.com/ollama/ollama?tab=readme-ov-file


- baixar ollama com docker :
  - docker pull ollama/ollama

- executar ollama   version cpu only :
  - docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

- listar containers:
  - docker ps

- acessar container e executar comandos no terminal do container :
  - exemplo : docker exec -it <mycontainer> bash
  - docker exec -it acff4a1b5aa2 bash

- executar modelo :
  - ollama run llama3

- listar modelos :
  - ollama list

- remover  modelo :
  - ollama remove llama3

- iniciar ou parar o ollama
  - docker container stop ollama
  - docker container start ollama


### Instalação manual Open-Webui com ollama no docker

docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/ollama-webui/ollama-webui:main
