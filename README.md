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
