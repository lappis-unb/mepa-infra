# MEPA infraestrutura

Este repositório contém a configuração completa da infraestrutura para o sistema MEPA Contratos, incluindo as configurações do NGINX, Docker e os scripts de automação via Ansible.

O sistema MEPA Contratos é projetado para apoiar as instituições de ensino superior (IES) na gestão e avaliação de contratos de energia elétrica. Funciona por meio do registro das faturas mensais de energia e gera relatórios detalhados com recomendações para ajustes nos contratos, visando a otimização dos recursos e a redução de custos.


<div align="center">
  <img src="/image/full_architecture_1.png" width="800" alt="Descrição da Imagem">
</div>

## Visão geral
Esta configuração de infraestrutura foi projetada para oferecer suporte a um aplicativo web com backend Django, frontend Next.js e banco de dados PostgreSQL . Ele usa NGINX  como ponto de entrada principal, servidor web e proxy reverso, Docker para conteinerização e Ansible para automação.

## Configuração do NGINX

O NGINX desempenha um papel central na arquitetura da aplicação, atuando como uma camada crítica de entre os clientes e os serviços de backend e frontend. Sua configuração está distribuída em dois arquivos principais:
- nginx/nginx.conf: Contém as configurações globais do NGINX.
- nginx/conf.d/mepa_template.conf: Define as configurações específicas para nossa aplicação.
 
 #### Está configurado para atuar como:

- **Proxy de Borda (Edge Proxy)**: Atua como o ponto de entrada principal para todo o tráfego HTTP/HTTPS
- **Servidor Web**: Serve diretamente conteúdo estático e configura cabeçalhos HTTP apropriados
- **Proxy reverso**: Roteamento de requisições para o backend Django e frontend Next.js
- **Terminação SSL**: Gerencia certificados SSL/TLS, fornecendo comunicação segura (HTTPS)

## Automação com Ansible

Os playbooks do Ansible realizam as seguintes tarefas:

- **create_user.yml:** Cria e configura o usuário Ansible
- **install_essential.yml:** Instala pacotes básicos do sistema
- **install_docker.yml:** Instala e configura o Docker
- **setup_docker.yml:** Cria as redes Docker necessárias
- **setup_certbot.yml:** Instala o Certbot
- **generate_certificates.yml:** Gera certificados SSL usando Let's Encrypt

## Certificados SSL

Os certificados SSL são gerados usando Certbot e o serviço Let's Encrypt. Os playbooks **setup_certbot.yml** e **generate_certificates.yml** lidam com esse processo.

## Como utilizar
.
.
.


## Repositórios Relacionados

Backend: https://gitlab.com/lappis-unb/projetos-energia/mec-energia/mec-energia-api
Frontend: https://gitlab.com/lappis-unb/projetos-energia/mec-energia/mec-energia-web

## Licença
Este projeto está licenciado sob a.....




