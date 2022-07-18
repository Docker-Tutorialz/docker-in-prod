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


### Create the Dockerfile

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

### Buid your Dockerfile
Hora de criar o build do Dockerfile, veja o comando abaixo para ajustar:

` docker build -t getting-started .`


<details>
  <summary><b></b> <em>(clique para ver a resposta)</em></summary>

```bash
Sending build context to Docker daemon  4.654MB   
Step 1/7 : FROM node:12-alpine
 ---> bb6d28039b8c
Step 2/7 : RUN apk add --no-cache python2 g++ make
 ---> Running in a067c51c395d
fetch https://dl-cdn.alpinelinux.org/alpine/v3.15/main/x86_64/APKINDEX.tar.gz
fetch https://dl-cdn.alpinelinux.org/alpine/v3.15/community/x86_64/APKINDEX.tar.gz
(1/22) Installing binutils (2.37-r3)
(2/22) Installing libgomp (10.3.1_git20211027-r0)
(3/22) Installing libatomic (10.3.1_git20211027-r0)
(4/22) Installing libgphobos (10.3.1_git20211027-r0)
(5/22) Installing gmp (6.2.1-r1)
(6/22) Installing isl22 (0.22-r0)
(7/22) Installing mpfr4 (4.1.0-r0)
(8/22) Installing mpc1 (1.2.1-r0)
(9/22) Installing gcc (10.3.1_git20211027-r0)
(10/22) Installing musl-dev (1.2.2-r7)
(11/22) Installing libc-dev (0.7.2-r3)
(12/22) Installing g++ (10.3.1_git20211027-r0)
(13/22) Installing make (4.3-r0)
(14/22) Installing libbz2 (1.0.8-r1)
(15/22) Installing expat (2.4.7-r0)
(16/22) Installing libffi (3.4.2-r1)
(17/22) Installing gdbm (1.22-r0)
(18/22) Installing ncurses-terminfo-base (6.3_p20211120-r1)
(19/22) Installing ncurses-libs (6.3_p20211120-r1)
(20/22) Installing readline (8.1.1-r0)
(21/22) Installing sqlite-libs (3.36.0-r0)
(22/22) Installing python2 (2.7.18-r4)
Executing busybox-1.34.1-r5.trigger
OK: 229 MiB in 38 packages
Removing intermediate container a067c51c395d
 ---> b2d61b824b3f
Step 3/7 : WORKDIR /app
 ---> Running in 8b5bc690e742
Removing intermediate container 8b5bc690e742
 ---> 4fcb2e6472f6
Step 4/7 : COPY . .
 ---> e80020eac517
Step 5/7 : RUN yarn install --production
 ---> Running in 5d658e33e289
yarn install v1.22.18
[1/4] Resolving packages...
warning Resolution field "ansi-regex@5.0.1" is incompatible with requested version "ansi-regex@^2.0.0"
warning Resolution field "ansi-regex@5.0.1" is incompatible with requested version "ansi-regex@^3.0.0"
[2/4] Fetching packages...
[3/4] Linking dependencies...
[4/4] Building fresh packages...
Done in 12.93s.
Removing intermediate container 5d658e33e289
 ---> 6fca0dcd5d22
Step 6/7 : CMD ["node", "src/index.js"]
 ---> Running in 26d081688136
Removing intermediate container 26d081688136
 ---> fc006139a264
Step 7/7 : EXPOSE 3000
 ---> Running in c0ecacfd20dc
Removing intermediate container c0ecacfd20dc
 ---> 633c01ce663d
Successfully built 633c01ce663d
Successfully tagged getting-started:latest
```
</details>

### Check and acess the URL

Once it has started, you can open your browser to [http://localhost](http://localhost).

### Development

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