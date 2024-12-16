# GoCase - Desafio DevOps
# 🚀 Projeto de Dockerização de Aplicações - Frontend, Backend e Banco de Dados

Este pojeto visa o encapsulamos uma aplicação frontend, backend e banco de dados PostgreSQL em containers Docker. Aqui está documentado todo o processo, incluindo como os serviços estão estruturados, as tecnologias usadas e a configuração de uma pipeline CI/CD com GitHub Actions. 🌟

---

## 📂 Estrutura do Projeto

Este repositório contém:

- **Frontend**: Aplicação construída em react.
- **Backend**: API construída com Ruby on Rails.
- **Banco de Dados**: PostgreSQL configurado com persistência de dados.
- **Docker Compose**: Arquivo para orquestração dos serviços.
<!-- - **GitHub Actions**: Pipeline CI/CD para deploy do frontend. -->

---

## 🛠️ Tecnologias Utilizadas

- **Docker** 🐳: Para containerização das aplicações.
- **Docker Compose**: Para orquestrar os serviços.
- **PostgreSQL** 🗄️: Banco de dados relacional.
- **GitHub Actions**: Para automação do deploy do frontend.
- **Vercel** 🌐: Hospedagem do frontend.

---

## ⚙️ Configuração do Docker Compose

O arquivo `docker-compose.yml` organiza os seguintes serviços:

| Serviço       | Porta Local | Porta no Container | Descrição                          |
|---------------|-------------|---------------------|--------------------------------------|
| Frontend      | 80          | 80                  | Aplicação frontend (nginx).        |
| Backend       | 3000        | 3000               | API em Ruby on Rails.              |
| Banco de Dados| 5432        | 5432               | PostgreSQL para persistência.      |


---

## 🚀 Deploy na Vercel

O frontend foi publicado na Vercel e está disponível no seguinte domínio:
🔗 **[Frontend Deployado na Vercel](https://pokeapiweb-devlucasvcarvalho.vercel.app/)**

> 💡 Observação: O Vercel é uma plataforma que hospeda apenas aplicações frontend. No caso de backend Rails, você pode configurá-lo para ser deployado em um ambiente diferente, como o Railway, Render, Heroku, ou um servidor próprio.
---

## 🛡️ Configuração de CI/CD com GitHub Actions

Foi utilizado o **GitHub Actions** para automatizar o deploy do frontend na Vercel. A pipeline é acionada automaticamente a cada push na branch `main`.

### Etapas da Pipeline
1. **Configuração da Máquina Virtual** 🖥️:  Uma máquina virtual Ubuntu é provisionada no GitHub Actions.
2. **Instalação do Node.js** 🛠️: A versão 18 do Node.js é configurada para o ambiente de execução.
3. **Instalação de Dependências e Build** ⚙️: As dependências do frontend são instaladas e o projeto é compilado.
3. **Deploy na Vercel** 🚀: O projeto é publicado na Vercel utilizando a ferramenta Vercel CLI.

---

## 📝 Instruções de Uso

### Pré-requisitos
- **Docker** instalado na máquina.
- **Docker Compose** configurado.

### Passos para Execução Local

1. **Clone o repositório**:
   ```bash
   git clone [https://github.com/SeuUsuario/seu-projeto.git](https://github.com/devlucasvcarvalho/Pokeapiweb.git)
   ```

2. **Suba os containers**:
   ```bash
   docker-compose up -d
   ```

3. **Acesse os serviços**:
   - Frontend: [http://localhost:80](http://localhost:80)
   - Backend: [http://localhost:3000](http://localhost:3000)

4. **Derrube os containers** (quando terminar):
   ```bash
   docker-compose down
   ```

---

## 📌 Considerações Técnicas

1. **Master Key no Backend**: Uma nova `master.key` foi gerada dentro do container do backend devido à ausência da chave original no repositório. Para projetos reais, recomenda-se armazenar essa chave em variáveis de ambiente seguras.
2. **Volumes**: Persistência de dados configurada para o banco PostgreSQL e para os dados temporários do backend.
3. **Conexão entre Serviços**: Frontend e backend conectados via `localhost` e banco de dados via rede interna do Docker.

---

## 🧑‍💻 Autor
Este projeto foi desenvolvido por **Lucas Carvalho**.

Entre em contato:
- 📧 Email: prolucascarvalho@gmail.com
- 🌐 LinkedIn: [Lucas Carvalho](https://www.linkedin.com/in/lucascarvalhopro/)
<!-- - 🐙 GitHub: [zerobetone01](https://github.com/zerobetone01) -->

---

**Obrigado por conferir este projeto!** 🎉
