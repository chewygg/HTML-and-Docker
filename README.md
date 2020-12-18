# :page_facing_up: HTML & Docker  :whale:
Registro de estudo - Como preparar um ambiente rapidamente para testar sua página HTML com Docker!
 
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/chewygg/HTML-and-Docker">
   <img src="images/apache-docker.png" alt="Logo" width="400" height="200">
  </a>
  <h3 align="center">  :page_facing_up: HTML & Docker  :whale: </h3>

  <p align="center">
    Técnica simples e muito útil para desenvolvedores e para aqueles que querem se tornar um!
    <br />
    <a href="https://github.com/chewygg/HTML-and-Docker/README.md"><strong>Explore the docs »</strong></a>
    <br />
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>INDICE</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project </a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
##   :books: :computer:  About The Project  :computer: :books:

Me aventurando no mundo dos containers notei o quão fácil foi subir uma página HTML localmente usando Docker.
Decidi então, registrar meus estudos e mostrar o quão fácil pode ser fazer isso, sem precisar de muitos conhecimentos técnicos em Linux ou em Docker.
Passarei rapidamente sobre alguns conceitos, caso queiram conhecer mais, não exitem em ler a documentação oficial do Docker em  [https://docs.docker.com/](https://docs.docker.com/)).

### Built With

O Processo que será mostrado a seguir pode ser feito em qualquer desktop que cumpra os requisitos mínimos do docker(podem ser encontrados na [documentação](https://docs.docker.com/get-docker/)).
E é claro, sua página HTML.

<!-- GETTING STARTED -->
## Getting Started

Agora, que você leu a documentação e garantiu que seu desktop cumpre todos os pré requisitos exigidos pelo Docker, basta instala-lo.

* [Docker para Windows](https://docs.docker.com/docker-for-windows/install/)
* [Docker para MAC](https://docs.docker.com/docker-for-mac/install/)
* [Docker para Linux](https://docs.docker.com/engine/install/)

 :exclamation: No caso do Windows 10, por experiência própria, recomendo muito que sigam a documentação da própria Microsoft sobre a instalação do [WSL 1](https://docs.microsoft.com/pt-br/windows/wsl/install-win10) e do [WSL 2](https://docs.microsoft.com/pt-br/windows/wsl/install-win10#step-2---update-to-wsl-2), onde, tanto a parte prática, quanto a teórica estão muito bem explicadas.  :exclamation:

### :package: Installation  :package:

Com o Docker instalado, vamo ao Docker Hub procurar uma imagem que irá servir de alicerce para sustentar minha página HTML.
Neste caso, será um servidor Apache.

O Docker trabalha com imagens, então podemos realizar o download de uma imagem de um servidor Apache para posteriormente colocarmos esta nossa infraestrutura backend em execução.
Mais sobre esta imagem pode ser visto em [https://hub.docker.com/_/httpd](https://hub.docker.com/_/httpd)

* Download da imagem httpd 
  ```sh
  docker pull httpd
  ```

<!-- USAGE EXAMPLES -->
## Usage

Já temos o Docker e uma imagem de um servidor Apache instalados, basta colocar tudo para funcionar!
Liste as imagens que temos baixadas:
```sh
docker image ls
 ```
A resposta deve ser parecida com isso:
[![Listar Imagens][output-imagels]]
 
Para rodar a imagem, ou seja, torna-la um container, basta usar o seguinte comando:

```sh
docker run httpd
```

### Iniciando o Servidor Apache
Porém, como o container apartado do restante do sistema, ainda não conseguiríamos fazer muito apenas com esse comando. Para resolvermos isso podemos usar as seguintes opções e argumentos:

```sh
docker run -dit -v "$PWD"/site:/usr/local/apache2/htdocs/ --name <nome qualquer> -p 80:80 httpd
```
:mag: Agora, vamos a explicação de cada opção e argumento  :mag:

:mag: **-d**  :point_right: Executa o container de maneira que não ocupe o terminal, ou seja, em background;

:mag: **-i**  :point_right: Permite que interação de entrada (stdin) com o container, ou seja, que interprete aquilo que digitarmos;

:mag: **-t**  :point_right: Aloca uma TTY para que as interações da opção **-i** sejam reconhecidas e lidas por um interpretador de linha de comando;

:mag: **-v**  :point_right: Permite declarar um volume de montagem, e o argumento que o segue **"$PWD"/site:/usr/local/apache2/htdocs/** nos diz que tudo que colocarmos no diretório **/site** será também "mapeado" para **/usr/local/apache2/htdocs/**, portanto, se colocarmos nosso HTML no diretório **/site** deremos o mesmo documento sendo sustentado pela estruturado do apache, ou seja, teremos um site funcionando localmente;

:mag: **--name**  :point_right: declara um nome para um container;  

:mag: **-p**  :point_right:  Faz o mapeamento de portas do container para a máquina que está rodando o Docker, sem esta opção, o meu computador não entenderia que ao fazer uma requisição para aquele IP na porta 80, deveria me devolver algo dentro do servidor Apache! Por isso faz-se necessário declarar que requisições para a porta 80, devem ser redirecionadas à porta 80 do container Apache;

:mag: **httpd**  :point_right: E por fim, **httpd** é apenas o nome da imagem que irá gerar o container.

### Inserindo a página HTML no servidor

Observe que após o comando anterior, o diretório **/site** foi criado no meu diretório atual:
[![Listar diretorio site][dir-site]]

<!-- CONTACT -->
## Contact

Gabriel Guedes - [gabriel.guedes2001@gmail.com](gabriel.guedes2001@gmail.com)

Project Link: [https://github.com/chewygg/HTML-and-Docker](https://github.com/chewygg/HTML-and-Docker/)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Img Shields](https://shields.io)


<!-- MARKDOWN LINKS & IMAGES -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/gguedescruz/
[output-imagels]: images/output-imagels.png
[dir-site]: images/dir-site.png
