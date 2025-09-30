### SLA e Máquinas Virtuais (VMs)

* **SLA (Acordo de Nível de Serviço)**: É a **garantia de tempo no ar** de um serviço. Quanto maior a porcentagem (ex: 99,99%), menor o tempo de inatividade permitido, cainindo de horas para poucos minutos por mês.

* **Como Atingir um SLA Alto com VMs**:
    * Uma **única VM** oferece um SLA mais baixo.
    * Para um SLA elevado (ex: 99,99%), é preciso criar **redundância**.
    * A melhor prática é distribuir múltiplas VMs entre diferentes **Zonas de Disponibilidade** (datacenters separados), garantindo que sua aplicação continue funcionando mesmo que um local falhe.

# Instâncias de Banco de Dados no Azure

- Criar instância = definir tipo de banco (SQL, MySQL, PostgreSQL etc.), nome, região e credenciais.  
- Configurar **rede/firewall** para acesso externo ou interno.  
- Ajustar **desempenho, escalabilidade e backup** conforme necessidade.  
- Conectar usando a **string de conexão** fornecida pelo Azure.  

# Componentes de Arquitetura do Azure

A arquitetura do Microsoft Azure é composta por uma vasta gama de serviços e componentes que permitem a criação, implantação e gerenciamento de aplicações e serviços na nuvem. Abaixo estão os principais componentes de sua arquitetura:

### **1. Computação**

O pilar da execução de aplicações e serviços.

* **Máquinas Virtuais (VMs):** Servidores virtuais sob demanda que oferecem total controle sobre o sistema operacional e o ambiente de execução.
* **Serviços de Aplicativos (App Services):** Uma plataforma gerenciada para construir, implantar e escalar aplicações web e APIs sem se preocupar com a infraestrutura subjacente.
* **Funções do Azure (Azure Functions):** Um serviço de computação sem servidor (serverless) que permite a execução de código em resposta a eventos, ideal para microsserviços e processamento de dados.
* **Serviço de Kubernetes do Azure (AKS):** Um serviço gerenciado de orquestração de contêineres que simplifica a implantação e o gerenciamento de aplicações em contêineres.
* **Instâncias de Contêiner do Azure (ACI):** Permite executar contêineres Docker no Azure sem a necessidade de gerenciar servidores.

### **2. Armazenamento**

Serviços para armazenar e gerenciar dados de forma escalável e segura.

* **Armazenamento de Blobs do Azure:** Armazenamento de objetos otimizado para grandes volumes de dados não estruturados, como texto ou dados binários.
* **Arquivos do Azure:** Compartilhamentos de arquivos totalmente gerenciados na nuvem que podem ser acessados via protocolo SMB.
* **Armazenamento de Tabelas do Azure:** Um serviço NoSQL que armazena dados estruturados.
* **Armazenamento de Filas do Azure:** Um serviço para armazenar um grande número de mensagens que podem ser acessadas de qualquer lugar do mundo.

### **3. Banco de Dados**

Uma variedade de serviços de banco de dados gerenciados para diferentes necessidades de aplicação.

* **Banco de Dados SQL do Azure:** Um banco de dados relacional como serviço, inteligente e totalmente gerenciado.
* **Azure Cosmos DB:** Um banco de dados NoSQL multimodelo e distribuído globalmente, projetado para alta disponibilidade e baixa latência.
* **Banco de Dados do Azure para MySQL, PostgreSQL e MariaDB:** Serviços de banco de dados relacionais gerenciados para essas populares tecnologias de código aberto.

### **4. Rede**

Serviços para conectar e isolar recursos do Azure e locais.

* **Rede Virtual do Azure (VNet):** Permite que os recursos do Azure se comuniquem de forma segura entre si, com a internet e com redes locais.
* **Balanceador de Carga do Azure (Load Balancer):** Distribui o tráfego de entrada entre máquinas virtuais íntegras para fornecer alta disponibilidade e desempenho.
* **Gateway de Aplicativo do Azure:** Um balanceador de carga de tráfego da web que permite gerenciar o tráfego para suas aplicações web.
* **VPN Gateway:** Envia tráfego criptografado entre uma rede virtual do Azure e um local local pela internet pública.

### **5. Identidade e Segurança**

Ferramentas para gerenciar o acesso e proteger recursos e dados.

* **Microsoft Entra ID (antigo Azure Active Directory):** Um serviço de gerenciamento de identidade e acesso baseado em nuvem que ajuda os funcionários a acessarem recursos.
* **Azure Key Vault:** Um serviço para armazenar e gerenciar com segurança segredos, chaves de criptografia e certificados.
* **Microsoft Defender for Cloud:** Uma plataforma de proteção de cargas de trabalho na nuvem e gerenciamento da postura de segurança.

### **6. Ferramentas de Gerenciamento e Governança**

Serviços para gerenciar, monitorar e governar o ambiente do Azure.

* **Azure Monitor:** Coleta, analisa e age sobre a telemetria de seus ambientes de nuvem e locais.
* **Azure Policy:** Ajuda a impor padrões organizacionais e a avaliar a conformidade em escala.
* **Azure Resource Manager (ARM):** O serviço de implantação e gerenciamento do Azure que permite criar, atualizar e excluir recursos em sua assinatura do Azure.

  # Serviços de Computação e Rede do Azure

## Serviços de Computação

Os serviços de computação do Azure formam a base para a execução de aplicações e cargas de trabalho na nuvem, oferecendo desde máquinas virtuais com controle total até plataformas totalmente gerenciadas.

### **Máquinas Virtuais (VMs)**
As VMs do Azure são servidores virtuais que fornecem a flexibilidade de um servidor físico, permitindo que você instale seu próprio sistema operacional (Windows ou Linux) e software. Elas são ideais para:
* **Migração de aplicações "lift-and-shift":** Mover aplicações existentes de um ambiente local para a nuvem com poucas ou nenhuma alteração.
* **Cargas de trabalho que exigem controle total:** Quando você precisa de controle granular sobre a configuração do ambiente.
* **Desenvolvimento e teste:** Criar ambientes de desenvolvimento e teste isolados de forma rápida e fácil.

### **Serviços de Aplicativos (App Services)**
O App Service é uma plataforma como serviço (PaaS) totalmente gerenciada para criar e implantar aplicações web e APIs. Ele cuida da infraestrutura, permitindo que você se concentre no código. Suas principais características incluem:
* **Suporte a várias linguagens e frameworks:** .NET, .NET Core, Java, Ruby, Node.js, PHP e Python.
* **Escalabilidade automática:** Ajusta automaticamente o número de instâncias com base na demanda.
* **Implantação contínua:** Integração com o Azure DevOps, GitHub e outros repositórios de código para automatizar o processo de implantação.

### **Funções do Azure (Azure Functions)**
O Azure Functions é um serviço de computação sem servidor (serverless) que permite executar pequenos trechos de código (funções) em resposta a eventos. Com o Functions, você não precisa se preocupar com o provisionamento ou gerenciamento de servidores. É ideal para:
* **Processamento de dados em tempo real:** Executar código em resposta a eventos de serviços do Azure, como o upload de um arquivo para o Blob Storage.
* **Criação de APIs sem servidor:** Construir APIs RESTful escaláveis e econômicas.
* **Orquestração de fluxos de trabalho:** Criar fluxos de trabalho complexos que integram diferentes serviços e APIs.

### **Serviço de Kubernetes do Azure (AKS)**
O AKS é um serviço gerenciado de orquestração de contêineres que simplifica a implantação, o gerenciamento e as operações de clusters Kubernetes. Ele oferece:
* **Gerenciamento simplificado de clusters:** O Azure gerencia o plano de controle do Kubernetes, tornando mais fácil a execução de aplicações em contêineres.
* **Escalabilidade e disponibilidade:** Permite escalar facilmente o número de nós no cluster e garante alta disponibilidade para suas aplicações.
* **Integração com o ecossistema do Azure:** Integra-se com outros serviços do Azure, como o Azure Monitor e o Microsoft Entra ID.

## Serviços de Rede

Os serviços de rede do Azure fornecem a base para conectar e proteger seus recursos do Azure, bem como estender sua rede local para a nuvem.

### **Rede Virtual do Azure (VNet)**
A VNet é o bloco de construção fundamental para sua rede privada no Azure. Ela permite que os recursos do Azure, como VMs, se comuniquem de forma segura entre si, com a internet e com suas redes locais. Com a VNet, você pode:
* **Isolar seus recursos:** Criar redes virtuais isoladas para diferentes ambientes, como

# Serviços de Armazenamento no Azure

A plataforma Microsoft Azure oferece um conjunto robusto e escalável de serviços de armazenamento para atender a diversas necessidades de dados na nuvem. Esses serviços são projetados para serem duráveis, seguros e altamente disponíveis. Os principais tipos de armazenamento são agrupados na conta de Armazenamento do Azure.

### **1. Armazenamento de Blobs do Azure (Azure Blob Storage)**

O Armazenamento de Blobs é a solução de armazenamento de objetos do Azure. É otimizado para armazenar grandes volumes de dados não estruturados, como texto, imagens, vídeos e arquivos de backup.

* **Casos de Uso Comuns:**
    * Streaming de áudio e vídeo.
    * Armazenamento de arquivos para acesso distribuído.
    * Armazenamento de dados para backup, restauração, recuperação de desastres e arquivamento.
    * Análise de dados (data lakes) com serviços como o Azure Data Lake Storage Gen2.
* **Tiers (Camadas de Acesso):**
    * **Hot:** Otimizado para dados acessados com frequência.
    * **Cool:** Otimizado para dados armazenados por pelo menos 30 dias e acessados com pouca frequência.
    * **Cold:** Novidade para dados armazenados por pelo menos 90 dias, com requisitos de latência flexíveis.
    * **Archive:** Otimizado para dados raramente acessados, com requisitos de latência flexíveis (várias horas), oferecendo o menor custo de armazenamento.

### **2. Arquivos do Azure (Azure Files)**

O serviço de Arquivos do Azure oferece compartilhamentos de arquivos totalmente gerenciados na nuvem, que podem ser acessados usando os protocolos Server Message Block (SMB) e Network File System (NFS).

* **Casos de Uso Comuns:**
    * Substituir ou complementar servidores de arquivos locais.
    * Aplicações "lift and shift" que precisam de um compartilhamento de arquivos para armazenar dados.
    * Centralizar o armazenamento de arquivos de configuração ou ferramentas compartilhadas para desenvolvimento e diagnóstico.
    * Pode ser montado simultaneamente por implantações na nuvem ou locais do Windows, Linux e macOS.

### **3. Armazenamento de Discos do Azure (Azure Disk Storage)**

O Armazenamento de Discos oferece discos de bloco de alto desempenho e duráveis, projetados para serem usados com Máquinas Virtuais do Azure. É semelhante a um disco rígido físico, mas virtualizado.

* **Tipos de Discos:**
    * **Ultra Disks:** Para cargas de trabalho de uso intensivo de dados, como SAP HANA e bancos de dados de nível superior.
    * **Premium SSDs:** Discos de alto desempenho para cargas de trabalho de produção e sensíveis à latência.
    * **Standard SSDs:** Opção econômica para servidores web, aplicações empresariais pouco usadas e ambientes de desenvolvimento/teste.
    * **Standard HDDs:** A opção mais econômica, ideal para backups e dados não críticos com acesso pouco frequente.

### **4. Armazenamento de Filas do Azure (Azure Queue Storage)**

O Armazenamento de Filas é um serviço para armazenar um grande número de mensagens. Ele permite o desacoplamento de componentes de uma aplicação, possibilitando que eles se comuniquem de forma assíncrona.

* **Casos de Uso Comuns:**
    * Criar uma lista de trabalhos para processamento assíncrono.
    * Passar mensagens entre diferentes partes de uma aplicação distribuída sem que elas precisem estar online ao mesmo tempo.
    * Ajudar a gerenciar picos de tráfego, enfileirando tarefas para processamento posterior e tornando a aplicação mais resiliente.

### **5. Armazenamento de Tabelas do Azure (Azure Table Storage)**

O Armazenamento de Tabelas é um serviço que armazena grandes volumes de dados NoSQL estruturados. É um repositório de chave-atributo com um design sem esquema.

* **Casos de Uso Comuns:**
    * Armazenar conjuntos de dados flexíveis, como dados de utilizador para aplicações web, catálogos de endereços ou outras informações de metadados.
    * Aplicações que não necessitam de junções complexas, chaves externas ou procedimentos armazenados.
    * *Nota: Atualmente, o Azure Cosmos DB for Table é a oferta recomendada para novas aplicações que precisam de armazenamento de tabelas, pois oferece funcionalidades premium.*
