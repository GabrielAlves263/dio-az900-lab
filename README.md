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
