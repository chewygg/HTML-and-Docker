# :page_facing_up: HTML & Docker  :whale:
Registro de estudo - Como preparar um ambiente rapidamente para testar sua página HTML com Docker!
 
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/chewygg/HTML-and-Docker">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
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
      <a href="#about-the-project">About The Project</a>
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
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

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

### Installation

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
 [![Listar Imagens][output-imagels]](https://example.com)
 
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
[output-imagels]: images/output-imagels
