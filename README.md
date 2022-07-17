# Docker Labz
A ideia aqui desse repositóeio é aprender Docker do zero mesmo, sem enrolação e seguindo as boas práticas de mercado. Vamos passar pelos seguintes tópicos até que seja possível ter um volume para nossa aplicação e tudo mais, inclusive um `Docker Compose`.

## Sumario

- [Docker Labz](#docker-labz)
  - [Sumario](#sumario)
  - [Create the Dockerfile](#create-the-dockerfile)
  - [Buid your Dockerfile](#buid-your-dockerfile)
  - [Check and acess the URL](#check-and-acess-the-url)
  - [Development](#development)
  - [Contributing](#contributing)
  - [License](#license)

- Executando seu primeiro contêiner
- Construir contêineres
- Aprender quais contêineres estão sendo executados e removê-los
- Usando volumes para persistir dados
- Usando montagens de ligação para apoiar o desenvolvimento
- Usando a rede de contêineres para oferecer suporte a aplicativos de vários contêineres
- Usando o Docker Compose para simplificar a definição e o compartilhamento de aplicativos
- Usando cache de camada de imagem para acelerar compilações e reduzir o tamanho de push/pull
- Usando compilações de vários estágios para separar dependências de tempo de compilação e de tempo de execução

## Create the Dockerfile

```dockerfile
# syntax=docker/dockerfile:1
FROM node:12-alpine
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```

## Buid your Dockerfile
Hora de criar o build do Dockerfile, veja o comando abaixo para ajustar:

` docker build -t getting-started .`

## Check and acess the URL

Once it has started, you can open your browser to [http://localhost](http://localhost).

## Development

This project has a `docker-compose.yml` file, which will start the mkdocs application on your
local machine and help you see changes instantly.

```bash
docker-compose up
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[GNU GENERAL PUBLIC LICENSE](https://github.com/Docker-Tutorialz/sample-application/blob/main/LICENSE)