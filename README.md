# Desafio de Projeto: Configurando uma instância de Banco de Dados na Azure

Neste desafio o objetivo é praticar o processo de configuração de uma instância de Bancos de Dados na plataforma Microsoft Azure. Assim, o aluno é desafiado a criar esse Banco de Dados e descrever como foi o processo de implementação. O relatório foi feito guiado pela experiência do aluno e o guia disponibilizado pela Microsoft no link [Criar um banco de dados individual](https://learn.microsoft.com/pt-br/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal).

## Criando uma instância

Podemos criar uma implementação deBanco de Dados SQL da Azure usando o portal da Azure, o PowerShell ou a CLI do Azure.

## Pré-requisitos

Ter uma assinatura da Azure. O que é trabalhado nesse relatório pode ser feito apenas no portal da Azure. Tem um tópico em que para criar um Banco de Dados SQL da Azure fora do portal é necessário ter permissões para fazê-lo, e está presente no guia como fazê-las..

# Criando um Banco de Dados SQL no Azure

## Passos Principais

### 1. Acessar o Portal
- Entre no **Portal do Azure** e vá para **Bancos de Dados SQL**.  
- Localize e Clique em **Criar**.
<br>

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-22-31.png)

### 2. Configurações Básicas

Aqui é feito as configurações básicas do Banco de daos, criar o nome, o servidor em que vai está o banco, se vai ser para produção ou desenvolvimento (muda o preço dependendo da escolha) e o é selecionado o usuário a utilizar o banco.

- **Assinatura:** escolha a desejada.  
- **Grupo de recursos:** crie `myResourceGroup`.  
- **Nome do banco de dados:** `mySampleDatabase`.  
- **Servidor:** crie um novo com:  
  - Nome exclusivo (`mysqlserver...`)  
  - Localização  
  - Autenticação SQL (usuário: `azureuser`, senha definida pelo usuário)  
- **Pool elástico:** Não.  
- **Ambiente de carga de trabalho:** Desenvolvimento.  
<br>

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-22-43.png)
![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-23-01.png)
![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-23-24.png)
![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-26-04.png)
![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-28-44.png)


### 3. Computação + Armazenamento
Aqui é escolhida uma camada de Serviço SQL e um nível de desempenho que melhor se ajuste às necessidades de aplicativo.

- Defina **Uso Geral (Sem Servidor)**.  
- **Camada de computação:** Sem servidor.  
- Configure a **Redundância do Armazenamento de Backup** (local, zona ou geográfica).<br>

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-28-39.png)  

### 4. Rede
Aqui é onde é configurado o acesso à rede e a conectividade do servidor. Toda configuração selecionada é aplicada ao servidor e a todos os bancos que ele gerencia.

- **Método de conectividade:** Ponto de extremidade público.  
- **Firewall:**  
  - Adicionar IP atual: **Sim**  
  - Permitir serviços do Azure: **Não**  
- **TLS:** manter em 1.2.  <br>

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-29-27.png)

### 5. Segurança

Aqui você decide se ativa ou não o pacote de segurança Microsoft Defender par aSQL.

- Opção de ativar avaliação gratuita do **Microsoft Defender for SQL**.  
- Possibilidade de configurar **TDE (Transparent Data Encryption)** com chave gerenciada.  <br>

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-29-47.png)

### 6. Configurações Adicionais
Aqui você tem algumas configurações personalizadas, que servem para criar um banco de dados em branco, uma amostra e até um backup de outro banco SQL e o uso de ordenação do banco de dados, que define as regras que classificam e comparam dados.

- **Fonte de dados:** selecione **Exemplo (AdventureWorksLT)**.  
- Opções de agrupamento e janela de manutenção podem ser ajustadas. <br> 

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-29-55.png)

### 7. Revisar e Criar
- Clique em **Examinar + Criar** e depois em **Criar**.
<br>

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-31-52.png)
![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-33-44.png)
![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-34-27.png)

---

## Consultar o Banco de Dados
- Acesse o banco no portal e abra o **Editor de consultas (versão prévia)**.  
- Faça login com autenticação SQL.  


## Limpeza dos Recursos
- Para excluir tudo:
  - Vá em Grupos de recursos
  - Selecione `MyResourceGroup`
  - Clique em **Excluir grupo de recursos**

## Curiosidades

Ao criar o banco, é disponibilizados alguns tutoriais de treinamento gratuito da Microsoft, para aprofundar os conhecimento em Bancos de Dados SQL do Azure.
<br>

![foto](images/Captura%20de%20tela%20de%202025-08-29%2009-35-08.png)