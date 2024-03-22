# SiriusSafe

<p align="center">
  <img src="logo.png">
</p>

## Descrição

SiriusSafe é um serviço avançado de registro de backups de bancos de dados projetado para fornecer uma solução confiável e automatizada para o gerenciamento seguro de dados. Desenvolvido com foco na eficiência e facilidade de uso, o SiriusSafe combina o poder do framework FastAPI com a flexibilidade do Celery para oferecer uma solução robusta para agendamento de backups.

## Funcionalidades Principais

- **Agendamento Inteligente**: Agende backups automáticos do seu banco de dados em horários específicos, permitindo a definição de intervalos personalizados e cronogramas flexíveis para atender às necessidades específicas do seu sistema.
  
- **API RESTful Completa**: O SiriusSafe oferece uma API RESTful completa, construída com FastAPI, que permite interações simples e eficientes com o serviço, facilitando a integração com sistemas existentes e a automação de processos.

- **Monitoramento em Tempo Real**: Acompanhe o status e o histórico de execução de suas tarefas de backup em tempo real, fornecendo visibilidade total sobre o desempenho e a integridade dos backups do seu sistema.

## Pré-requisitos

Antes de começar, certifique-se de atender aos seguintes pré-requisitos:

- Python 3.6 ou superior
- Celery (Versão mais recente)
- Redis (Banco de dados de fila para Celery)

## Instalação e Configuração

Siga as etapas abaixo para instalar e configurar o SiriusSafe:

1. **Clone o Repositório**: 
    ```bash
    git clone https://github.com/seu-usuario/SiriusSafe.git
    cd SiriusSafe
    ```

2. **Instale as Dependências**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Configure as Variáveis de Ambiente**:
    - Crie um arquivo `.env` na raiz do projeto e adicione as seguintes variáveis de ambiente:
        ```plaintext
        # Configurações do Celery
        CELERY_BROKER_URL=redis://localhost:6379/0
        CELERY_RESULT_BACKEND=redis://localhost:6379/0

        # Configurações do Banco de Dados
        DATABASE_URL=sqlite:///./SiriusSafe.db
        ```

## Como Usar

Siga as instruções abaixo para iniciar e utilizar o SiriusSafe:

1. **Inicie o Servidor FastAPI**:
    ```bash
    uvicorn main:app --reload
    ```

2. **Inicie o Worker do Celery**:
    ```bash
    celery -A tasks worker --loglevel=INFO
    ```

## Documentação da API

A documentação completa da API está disponível em [http://localhost:8000/docs](http://localhost:8000/docs), fornecendo detalhes sobre todos os endpoints disponíveis, parâmetros de solicitação e exemplos de resposta.

## Contribuição

Contribuições são bem-vindas! Se você encontrar bugs ou tiver sugestões de melhorias, sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este projeto é licenciado sob a licença Apache 2.0. Consulte o arquivo LICENSE para obter mais detalhes.

