# Repositorio Website Lab DevOps

Repositorio da aplicacao web usada no laboratorio.

## O que tem aqui

- `website/index.html`: estrutura da pagina.
- `website/css/style.css`: estilos da interface.
- `website/js/script.js`: interacao simples para o laboratorio.
- `Dockerfile`: empacotamento da aplicacao em uma imagem Nginx.
- `.github/workflows/deploy.yaml`: pipeline para build da imagem, push no ECR e deploy na EC2.

## Objetivo

Este repositorio representa a camada de aplicacao do projeto:

- o site foi pensado para ser simples e didatico;
- o foco nao e o frontend em si, mas o fluxo de containerizacao e deploy;
- ele serve como base para gerar imagem Docker e publicar no ECR;
- depois, essa imagem e executada na EC2.

## Pipeline de Deploy

O workflow em `.github/workflows/deploy.yaml` automatiza o fluxo da aplicacao:

- faz build da imagem Docker;
- publica no Amazon ECR;
- acessa a EC2 por SSH;
- faz o pull da imagem e sobe o container novo.

Esse arquivo e importante porque mostra a ponte entre a aplicacao e a automacao de entrega.

## Como isso se conecta ao resto

- a infraestrutura esta em `infra-as-code`;
- o laboratorio principal documenta as fases;
- este repositorio concentra a parte da aplicacao e da imagem Docker.
