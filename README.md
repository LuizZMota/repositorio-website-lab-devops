# repositório Website Lab DevOps

Repositório da aplicação web usada no laboratório.

## O que tem aqui

- `website/index.html`: estrutura da pagina.
- `website/css/style.css`: estilos da interface.
- `website/js/script.js`: interação simples para o laboratório.
- `Dockerfile`: empacotamento da aplicação em uma imagem Nginx.
- `.github/workflows/deploy.yaml`: pipeline para build da imagem, push no ECR e deploy na EC2.

## Objetivo

Este repositório representa a camada de aplicação do projeto:

- o site foi pensado para ser simples e didático;
- o foco nao e o frontend em si, mas o fluxo de conteinerização e deploy;
- ele serve como base para gerar imagem Docker e publicar no ECR;
- depois, essa imagem e executada na EC2.

## Pipeline de Deploy

O workflow em `.github/workflows/deploy.yaml` automatiza o fluxo da aplicação:

- faz build da imagem Docker;
- publica no Amazon ECR;
- acessa a EC2 por SSH;
- faz o pull da imagem e sobe o container novo.

Esse arquivo é importante porque mostra a ponte entre a aplicação e a automação de entrega.

## Como isso se conecta ao resto

- a infraestrutura esta em `infra-as-code`;
- o laboratório principal documenta as fases;
- este repositório concentra a parte da aplicação e da imagem Docker.
