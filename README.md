# Fake Shop API

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/aws-232F3E?style=for-the-badge&logo=amazon&logoColor=white)

[![GitHub Repo](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/felipepanegalli/ms-cloud-fake-shop)

A **Fake Shop API** é uma API RESTful criada como parte de um curso de **DevOps & Cloud**, com foco em deploy utilizando **AWS** e **Kubernetes**. O projeto é uma aplicação de loja fictícia, simulando operações de e-commerce, como gerenciar produtos, usuários, pedidos, entre outros.


## **Objetivo do Projeto**

- Demonstrar conceitos fundamentais de DevOps & Cloud.
- Ensinar como realizar o deployment de uma aplicação moderna utilizando **AWS**.
- Implementar **Kubernetes** para orquestração de contêineres.
- Aplicar boas práticas de CI/CD e monitoramento.


## **Tecnologias Utilizadas**

- **Backend**: Flask
- **Banco de Dados**: Postgre
- **Docker**: Para criação e gerenciamento de contêineres
- **Kubernetes**: Orquestração de contêineres
- **AWS**:
  - EC2 e EKS
- **CI/CD**: GitHub Actions

## **Configuração e Deploy**

### **1. Configuração Local**

1. Clone o repositório:
   ```bash
   git clone https://github.com/felipepanegalli/ms-cloud-fake-shop.git
   cd ms-cloud-fake-shop
   ```

2. Instale as dependências:
   ```bash
   pip install -r src/requirements.txt
   ```

3. Configure as variáveis de ambiente :
   ```env
    DB_HOST	=> Host do banco de dados PostgreSQL.
    DB_USER => Nome do usuário do banco de dados PostgreSQL.
    DB_PASSWORD	=> Senha do usuário do banco de dados PostgreSQL.
    DB_NAME	=>	Nome do banco de dados PostgreSQL.
    DB_PORT	=>	Porta de conexão com o banco de dados PostgreSQL.
   ```

4. Execute o servidor localmente:
   ```bash
   chmod +x /src/entrypoint.sh && ./src/entrypoint.sh
   ```


### **2. Docker**

1. Crie a imagem Docker:
   ```bash
   docker build -t fake-shop-api .
   ```

2. Execute o contêiner:
   ```bash
   docker run -p 5000:5000 fake-shop-api
   ```


### **3. Kubernetes**

1. Configure os manifests:
   - Os arquivos YAML para deployment e serviços estão disponíveis na pasta `k8s`.

2. Aplique os manifests no cluster:
   ```bash
   kubectl apply -f k8s/deployment.yaml
   ```

3. Verifique os pods e serviços:
   ```bash
   kubectl get pod
   kubectl get all
   kubectl get svc
   ```


### **4. Deploy na AWS**

1. Configure seu cluster EKS:
   - Use `eksctl` ou o console AWS para criar um cluster.

2. Faça o deploy utilizando os manifests do Kubernetes:
   ```bash
   kubectl apply -f k8s/
   ```

3. Configure o acesso ao banco de dados MongoDB Atlas e verifique o funcionamento da API.


## **Autor do projeto**

Fabrício Veronez
GitHub: fabricioveronez
Projeto Original: Repositório Original

Sinta-se à vontade para contribuir e explorar o projeto!