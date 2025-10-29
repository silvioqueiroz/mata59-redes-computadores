# PROJETO — Superitendência de Tecnologia de Informação  
**Disciplina:** Redes de Computadores — Ciência da Computação — UFBA  
**Professor:** Leobino Sampaio  
**Aluno(s):** [Nome dos integrantes]  

---

## DESCRIÇÃO DO CENÁRIO

A **Superitendência de Tecnologia de Informação** está implementando sua infraestrutura de rede local e de interconexão entre departamentos.  
O projeto consiste em planejar, configurar e testar uma rede corporativa composta por **4 departamentos**, utilizando o **Cisco Packet Tracer** como ambiente de simulação.

Cada departamento possui:
- **10 estações de trabalho (PCs)**
- **2 impressoras**
- **2 servidores**
- **Total: 14 hosts por departamento**

Departamentos:
- Engenharia  
- Compras  
- TI Interno  
- Infraestrutura  

---

## OBJETIVOS

- Criar uma topologia de rede lógica e funcional para a **Superitendência de Tecnologia de Informação**.  
- Planejar e configurar **endereçamento IP**, **VLANs**, **DHCP**, **DNS**, **HTTP** e **Wireless**.  
- Implementar **roteamento inter-VLAN (Router-on-a-Stick)** para comunicação entre departamentos.  
- Garantir **conectividade total (LAN ↔ WAN)** entre todos os dispositivos.  
- Validar o funcionamento dos serviços de rede e da comunicação entre os setores.

---

## PLANEJAMENTO DE ENDEREÇAMENTO IP

| Departamento | VLAN | Rede | 1º IP válido | Último IP válido | Broadcast | Gateway |
|---------------|------|-------------|----------------|------------------|------------|-----------|
| Engenharia | 10 | 192.168.100.0/28 | 192.168.100.1 | 192.168.100.14 | 192.168.100.15 | 192.168.100.1 |
| Compras | 20 | 192.168.100.16/28 | 192.168.100.17 | 192.168.100.30 | 192.168.100.31 | 192.168.100.17 |
| TI Interno | 30 | 192.168.100.32/28 | 192.168.100.33 | 192.168.100.46 | 192.168.100.47 | 192.168.100.33 |
| Infraestrutura | 40 | 192.168.100.48/28 | 192.168.100.49 | 192.168.100.62 | 192.168.100.63 | 192.168.100.49 |

---

## TOPOLOGIA GERAL

- **Roteador Cisco 2811** — realizando roteamento inter-VLAN (Router-on-a-Stick).  
- **Switches Cisco 2950-24** — um por departamento.  
- **Topologia Estrela**, com o roteador como ponto central.  
- **Quatro VLANs**: Engenharia (10), Compras (20), TI Interno (30) e Infraestrutura (40).  

---

## 🧭 INSTRUÇÕES

1. **Baixe e instale o Cisco Packet Tracer.**  
2. **Baixe e abra o arquivo `template.pkt`.**  
3. **Coloque os dispositivos e equipamentos de rede**, conforme o planejamento do projeto.  
4. **Conecte-os usando os enlaces apropriados (cabos e interfaces corretas).**  
5. **Configure as redes e serviços**:
   - VLANs
   - Endereçamento IP (estático e DHCP)
   - Roteamento inter-VLAN (Router-on-a-Stick)
   - DNS e HTTP
6. **Teste a configuração IP, enlaces e conexões de rede** usando pacotes **ICMP (ping)** e os **sniffers** do Packet Tracer.  
7. **Teste o serviço DHCP:**
   - Adicione dispositivos e verifique se eles obtêm IP automaticamente.  
8. **Teste o serviço DNS:**
   - Faça um **ping para `ufba.br`** e **`cisco.srv`**.  
9. **Teste o serviço HTTP do provedor:**
   - Altere o arquivo `index.html` e verifique se as alterações aparecem ao acessar de outros dispositivos.  
10. **Teste o serviço HTTP local da rede amarela:**
    - Acesse o site interno pelos dispositivos da rede amarela e também de redes externas.  

---

# 🧩 ENTREGÁVEIS

Este trabalho está dividido em **3 entregas parciais**, cada uma com seu conjunto de arquivos e documentos.

Ao término de cada etapa, cada grupo deve submeter os **arquivos solicitados (entregáveis)**.

---

## 🧱 1) ENTREGA DAS REDES LAN

### Arquivos exigidos
- Arquivo texto (**.txt**) contendo:
  - Nome / número do grupo  
  - Nome dos integrantes  
- Arquivo do Packet Tracer (**.pkt**)

### O que deve conter
- Configuração **das redes LAN** de cada departamento (Engenharia, Compras, TI Interno e Infraestrutura).  
- Cada LAN deve possuir seus dispositivos (PCs, impressoras e servidores) interligados via **Switch Cisco 2950-24**.  
- O roteador central pode estar presente, mas **sem conexão entre LANs ainda configurada**.

### Critério de validação
- Todos os dispositivos **de uma mesma LAN** devem se comunicar via **ping (ICMP)**.  
- Cada VLAN deve estar corretamente configurada no switch correspondente.  
- **Não é necessário conectar LAN ↔ WAN nesta etapa.**

---

## 🌐 2) ENTREGA DA REDE WAN

### Arquivos exigidos
- Arquivo texto (**.txt**) contendo:
  - Nome / número do grupo  
  - Nome dos integrantes  
- Arquivo do Packet Tracer (**.pkt**)

### O que deve conter
- Dispositivos das **redes LAN e WAN** devidamente conectados e configurados.  
- O roteador Cisco 2811 deve estar configurado com as **subinterfaces 802.1Q** para realizar **roteamento inter-VLAN**.  
- Cada departamento deve estar em uma VLAN com gateway configurado no roteador.  
- **DHCP configurado apenas para Compras e Infraestrutura.**

### Critério de validação
- Comunicação entre todos os dispositivos das redes LAN e WAN (ping entre departamentos).  
- Conectividade garantida por meio do roteamento configurado.  
- **Não é necessário configurar serviços de DNS, HTTP ou Wireless nesta etapa.**

---

## 🧾 3) ENTREGA FINAL

### Arquivos exigidos
- **Slides de apresentação (.pdf)**  
- **Relatório final (.pdf)**  
  - Descrevendo o que foi feito, como foi feito e por quem foi feito (integrantes da equipe).  
  - Seguindo as normas da **ABNT**.  
  - Estrutura mínima: **Introdução, Metodologia, Resultados e Discussão, Conclusão**.  
- **Arquivo Packet Tracer (.pkt)**

### O que deve conter
- Configuração completa das **redes LAN e WAN** com todos os dispositivos.  
- Todos os enlaces (cabeados e wireless) devidamente configurados e operantes.  
- **Conectividade total entre todos os dispositivos finais (ICMP ping).**  
- **Serviços de rede configurados e testados:**
  - DHCP
  - DNS
  - HTTP
  - Wireless (SSID, senha e segurança)
- **Registros DNS configurados corretamente** nos servidores primário e secundário.  

### Critério de validação
- Todas as redes (LAN e WAN) funcionando e interconectadas.  
- Comunicação funcional entre todos os dispositivos (ping e acesso a serviços).  
- Servidores HTTP acessíveis por nome (resolução DNS).  
- DHCP, DNS e Wireless devidamente operacionais.

---

## CONCLUSÃO

O projeto da **Superitendência de Tecnologia de Informação** propõe a implementação completa de uma rede corporativa, abordando desde o planejamento de endereçamento até a integração WAN com todos os serviços de rede ativos.  
Através da simulação no **Cisco Packet Tracer**, o grupo deverá demonstrar conhecimento prático em VLANs, roteamento, DHCP, DNS e HTTP, garantindo conectividade e confiabilidade de comunicação entre os departamentos.

---

**Autor(es):** [Nomes dos integrantes]  
**Grupo:** [Número]  
**Curso:** Ciência da Computação — UFBA  
**Professor:** Leobino Sampaio   
