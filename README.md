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

# Identidade, Acesso e Segurança no Azure

Os serviços de identidade, acesso e segurança do Azure formam uma camada de proteção fundamental para todos os recursos na nuvem. Eles garantem que apenas usuários e aplicações autorizadas possam acessar seus dados e infraestrutura, ao mesmo tempo que protegem contra ameaças cibernéticas.

### **1. Microsoft Entra ID (Anteriormente Azure Active Directory)**

O Microsoft Entra ID é o serviço de gerenciamento de identidade e acesso multinuvem da Microsoft. É a base para o controle de acesso no Azure e no Microsoft 365.

* **Gerenciamento de Identidade:** Funciona como um diretório central para gerenciar usuários, grupos e credenciais. Permite a autenticação de identidades para acessar aplicações e recursos.
* **Logon Único (Single Sign-On - SSO):** Permite que os usuários acessem milhares de aplicações SaaS (como Salesforce, Dropbox) com uma única credencial, simplificando o acesso e melhorando a segurança.
* **Autenticação Multifator (MFA):** Adiciona uma camada crítica de segurança ao processo de login, exigindo uma segunda forma de verificação (como um código no celular ou biometria) para comprovar a identidade do usuário.
* **Acesso Condicional:** Permite criar políticas de acesso granulares que avaliam condições específicas (como localização do usuário, dispositivo, aplicação) antes de conceder acesso aos recursos.

### **2. Gerenciamento de Acesso**

Esses serviços controlam *o que* os usuários autenticados podem fazer dentro do ambiente Azure.

* **Controle de Acesso Baseado em Função (RBAC - Role-Based Access Control):** Permite conceder permissões específicas aos usuários e grupos com base em suas funções. Em vez de dar acesso total, você concede apenas o necessário para realizar o trabalho (princípio do menor privilégio). Exemplos de funções são "Leitor", "Colaborador" e "Proprietário".
* **Azure AD Privileged Identity Management (PIM):** Um serviço avançado para gerenciar, controlar e monitorar o acesso a recursos importantes. Permite o acesso "just-in-time" a funções privilegiadas, o que significa que os usuários só recebem permissões elevadas por um tempo limitado quando precisam delas.

### **3. Segurança e Proteção contra Ameaças**

O Azure oferece um conjunto de ferramentas avançadas para proteger sua infraestrutura e dados contra ameaças e para gerenciar a postura de segurança do seu ambiente.

* **Microsoft Defender for Cloud:** É uma plataforma de gerenciamento de postura de segurança e proteção contra ameaças. Ele monitora continuamente seus recursos na nuvem (Azure e outras nuvens) e locais, fornecendo:
    * **Pontuação de Segurança (Secure Score):** Avalia sua postura de segurança e fornece recomendações para mitigar riscos.
    * **Proteção contra ameaças:** Detecta e alerta sobre atividades maliciosas, como tentativas de força bruta em VMs, ataques a bancos de dados SQL e atividades suspeitas em contas de armazenamento.
* **Azure Key Vault:** Um serviço seguro para armazenar e gerenciar segredos de aplicações, como chaves de API, senhas e certificados. As aplicações podem acessar esses segredos de forma programática e segura, evitando que sejam codificados diretamente no código-fonte.
* **Firewall do Azure:** Um serviço de segurança de rede inteligente e nativo da nuvem. Ele oferece proteção centralizada contra ameaças para todos os recursos em uma rede virtual, filtrando o tráfego de entrada e saída com base em regras definidas.
* **Proteção contra DDoS do Azure:** Protege os recursos do Azure contra ataques de negação de serviço distribuído (DDoS), que tentam sobrecarregar e esgotar os recursos de uma aplicação online.

* # Gerenciamento de Recursos no Azure

O gerenciamento de recursos no Azure refere-se ao conjunto de ferramentas e serviços que permitem implantar, organizar, governar e controlar os recursos (como máquinas virtuais, bancos de dados e redes) em sua assinatura. Uma gestão eficaz é crucial para otimizar custos, garantir a conformidade e manter a organização do ambiente na nuvem.

### **1. Azure Resource Manager (ARM)**

O ARM é o serviço de implantação e gerenciamento do Azure. Ele funciona como uma camada de gerenciamento unificada que processa todas as solicitações de API para criar, ler, atualizar ou excluir recursos.

* **Implantação Declarativa:** Em vez de escrever scripts com comandos sequenciais, você define o estado final desejado da sua infraestrutura em um modelo (template). O ARM cuida para que o estado implantado corresponda ao que foi declarado.
* **Modelos ARM (ARM Templates):** São arquivos JSON (ou Bicep, uma linguagem mais simples) que definem todos os recursos, dependências e configurações para uma implantação. Isso permite a prática de Infraestrutura como Código (IaC), tornando as implantações consistentes, repetíveis e automatizadas.
* **Consistência:** Todas as ferramentas de gerenciamento (Portal do Azure, Azure PowerShell, CLI do Azure, APIs REST) usam o ARM, garantindo uma experiência de gerenciamento consistente em toda a plataforma.

### **2. Grupos de Recursos (Resource Groups)**

Um Grupo de Recursos é um contêiner lógico no qual os recursos do Azure são implantados e gerenciados. É a unidade fundamental de organização e gerenciamento.

* **Ciclo de Vida:** Todos os recursos em um grupo compartilham o mesmo ciclo de vida. Se você excluir o grupo de recursos, todos os recursos contidos nele também serão excluídos.
* **Organização:** Geralmente, os recursos que compõem uma mesma aplicação ou solução são agrupados. Por exemplo, uma aplicação web pode ter sua VM, banco de dados, conta de armazenamento e rede virtual no mesmo grupo de recursos.
* **Controle de Acesso e Faturamento:** Permissões de acesso (via RBAC) e custos podem ser aplicados e monitorados no nível do grupo de recursos, simplificando a administração.

### **3. Marcações (Tags)**

Tags são metadados (pares de chave-valor) que você pode aplicar aos seus recursos e grupos de recursos do Azure para organizá-los logicamente.

* **Casos de Uso:**
    * **Gerenciamento de Custos:** Marcar recursos por departamento (ex: `Departamento: Marketing`) ou projeto (`Projeto: LançamentoProdutoX`) para rastrear e alocar custos.
    * **Automação:** Usar tags para acionar scripts de automação. Por exemplo, um script pode desligar todas as VMs marcadas com `Ambiente: Desenvolvimento` fora do horário comercial.
    * **Governança e Conformidade:** Identificar recursos que estão sujeitos a políticas de conformidade específicas.

### **4. Azure Policy**

O Azure Policy é um serviço que permite criar, atribuir e gerenciar políticas que impõem regras e efeitos sobre seus recursos. Ele garante que os recursos permaneçam em conformidade com os padrões corporativos e os contratos de nível de serviço.

* **Aplicação de Regras:** Você pode criar políticas para, por exemplo, permitir a criação de VMs apenas em determinadas regiões, exigir a aplicação de tags específicas em todos os recursos ou proibir a criação de IPs públicos.
* **Avaliação de Conformidade:** O serviço avalia continuamente seus recursos em relação às políticas atribuídas e fornece um painel para visualizar o estado de conformidade do seu ambiente.
* **Remediação:** Para recursos não conformes, o Azure Policy pode acionar tarefas de remediação para corrigir a configuração automaticamente.

### **5. Azure Blueprints**

O Azure Blueprints permite que arquitetos de nuvem e grupos de TI definam um conjunto repetível de recursos do Azure que implementam e aderem aos padrões e requisitos de uma organização.

* **Artefatos:** Um blueprint é um pacote que pode conter:
    * Atribuições de função (RBAC).
    * Atribuições de política (Azure Policy).
    * Modelos do Azure Resource Manager (ARM templates).
    * Grupos de recursos.
* **Governança em Escala:** Simplifica a implantação de ambientes em larga escala, garantindo que novas assinaturas sejam criadas já com a governança, segurança e conformidade necessárias pré-configuradas.
