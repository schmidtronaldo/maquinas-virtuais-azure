# Bootcamp Bradesco Java Cloud Native
## Digital Innovation One
## Especialista: Valéria Baptista
- Head of Cloud and Cybersecurity, CloudData Tech & DevOps
  
### Objetivo
- Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure
- Validar modelos de VMs e controle de carga

### Passos: 

Criar e gerenciar VMs (Máquinas Virtuais) no Microsoft Azure envolve vários passos, desde a criação da VM até a configuração de balanceamento de carga. Abaixo, vou detalhar o passo a passo para criar uma VM no Azure e configurar o controle de carga.

### Passo 1: Criar uma Máquina Virtual no Azure

1. **Acesse o Portal do Azure:**
   - Acesse o [Portal do Azure](https://portal.azure.com).

2. **Criar uma Nova Máquina Virtual:**
   - No painel esquerdo, clique em "Criar um recurso".
   - Selecione "Máquina Virtual" na seção "Computação".

3. **Configurações Básicas:**
   - **Assinatura:** Selecione a assinatura que deseja usar.
   - **Grupo de Recursos:** Crie um novo grupo de recursos ou selecione um existente.
   - **Nome da Máquina Virtual:** Dê um nome para sua VM.
   - **Região:** Selecione a região onde a VM será hospedada.
   - **Imagem:** Escolha uma imagem do sistema operacional (por exemplo, Windows Server ou uma distribuição Linux).
   - **Tamanho:** Selecione o tamanho da VM com base nas suas necessidades de CPU, memória e armazenamento.

4. **Configurações de Administrador:**
   - **Nome de Usuário:** Defina um nome de usuário para acessar a VM.
   - **Senha ou Chave Pública SSH:** Escolha entre usar uma senha ou uma chave SSH para autenticação.

5. **Configurações de Rede:**
   - **Rede Virtual:** Crie uma nova rede virtual ou selecione uma existente.
   - **Sub-rede:** Defina a sub-rede para a VM.
   - **IP Público:** Escolha se deseja atribuir um IP público à VM.
   - **Grupo de Segurança de Rede (NSG):** Configure as regras de segurança para permitir tráfego (por exemplo, permitir SSH na porta 22 ou RDP na porta 3389).

6. **Configurações de Armazenamento:**
   - **Disco do Sistema Operacional:** Escolha o tipo de disco (HDD Standard, SSD Standard ou SSD Premium).
   - **Discos de Dados:** Adicione discos de dados adicionais, se necessário.

7. **Revisar e Criar:**
   - Revise todas as configurações e clique em "Criar" para iniciar a implantação da VM.

### Passo 2: Configurações Essenciais

1. **Conectar à VM:**
   - Após a criação da VM, você pode se conectar a ela usando SSH (para Linux) ou RDP (para Windows).
   - No portal do Azure, vá para a VM e clique em "Conectar" para obter as instruções de conexão.

2. **Instalar Software Necessário:**
   - Instale qualquer software ou serviço necessário na VM, como um servidor web, banco de dados, etc.

3. **Configurar Firewall e Segurança:**
   - Configure o firewall da VM para permitir apenas o tráfego necessário.
   - Atualize o sistema operacional e instale patches de segurança.

### Passo 3: Controle de Carga (Balanceamento de Carga)

1. **Criar um Balanceador de Carga:**
   - No portal do Azure, clique em "Criar um recurso".
   - Selecione "Balanceador de Carga" na seção "Rede".

2. **Configurar o Balanceador de Carga:**
   - **Nome:** Dê um nome ao balanceador de carga.
   - **Tipo:** Escolha entre "Público" (para balanceamento de carga externo) ou "Interno" (para balanceamento de carga interno).
   - **IP Público:** Selecione ou crie um IP público para o balanceador de carga.
   - **Região:** Selecione a mesma região onde suas VMs estão localizadas.

3. **Configurar o Pool de Backend:**
   - No balanceador de carga, vá para "Pools de Backend" e adicione as VMs que deseja incluir no pool.
   - Associe as VMs ao pool de backend.

4. **Configurar Regras de Balanceamento de Carga:**
   - Vá para "Regras de Balanceamento de Carga" e crie uma nova regra.
   - Defina a porta de frontend (por exemplo, 80 para HTTP) e a porta de backend (por exemplo, 80).
   - Associe a regra ao pool de backend.

5. **Configurar Investigação de Integridade:**
   - Vá para "Investigações de Integridade" e crie uma nova investigação.
   - Defina o protocolo (HTTP, TCP, etc.) e a porta que será usada para verificar a integridade das VMs.
   - Configure o intervalo de verificação e o limiar de falha.

6. **Testar o Balanceamento de Carga:**
   - Após configurar o balanceador de carga, teste o acesso ao serviço através do IP público do balanceador.
   - Verifique se o tráfego está sendo distribuído entre as VMs no pool de backend.

### Passo 4: Monitoramento e Ajustes

1. **Monitorar o Desempenho:**
   - Use o Azure Monitor para acompanhar o desempenho das VMs e do balanceador de carga.
   - Configure alertas para notificá-lo sobre problemas de desempenho ou falhas.

2. **Ajustar Configurações:**
   - Com base no monitoramento, ajuste as configurações do balanceador de carga, como regras de balanceamento, investigações de integridade e tamanho do pool de backend.

3. **Escalabilidade:**
   - Considere usar conjuntos de escala de máquinas virtuais (VM Scale Sets) para escalar automaticamente o número de VMs com base na demanda.

### Conclusão

Seguindo esses passos, podemos criar e configurar VMs no Azure, além de implementar um controle de carga eficiente para distribuir o tráfego entre várias instâncias. Isso garante alta disponibilidade e escalabilidade para suas aplicações.
