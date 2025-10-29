# PROJETO — Superitendência de Tecnologia de Informação  
**Disciplina:** Redes de Computadores — Ciência da Computação — UFBA  
**Professor:** Leobino Sampaio  
**Aluno(s):** [Nome dos integrantes]  

---

## DESCRIÇÃO DO CENÁRIO

A **Superitendência de Tecnologia de Informação** está implementando sua infraestrutura de rede local e de interconexão entre departamentos.  
O projeto consiste em planejar, configurar e testar uma rede corporativa composta por **4 departamentos**, utilizando o **Cisco Packet Tracer** como ambiente de simulação.
Abaixo os critérios do projeto:

- Cada departamento possui: **10 estações de trabalho (PCs)**
- **Infraestrutura de servidores centralizada** (na rede de Infraestrutura):
  - 2 Servidores de E-MAIL (**SMTP** e **POP3**)
  - 2 Servidores WEB (**HTTP**)
- Deve ser usada uma máscara de sub-rede que atenda a necessidade apresentada
- Para a numeração IPs, deve-se usar uma sequência nas sub-redes de acordo com a máscara adotada
- Cada departamento deve estar em uma sub-rede
- Configure uma Vlan nas subs-rede
- Configure uma VLAN nas sub-redes
- Os departamentos de Engenharia e T.I. Interno devem ser colocados IPs estáticos, já nos departamentos de compras e Infraestrutura devem ser colocados IPs dinâmicos, de maneira que siga a sequência dos IPs estáticos.

Departamentos:
- Engenharia  
- Compras  
- TI Interno  
- Infraestrutura (contém os servidores centrais da rede)  

---

## OBJETIVOS

- Criar uma topologia de rede lógica e funcional para a empresa **Superitendência de Tecnologia de Informação**.  
- Planejar e configurar **endereçamento IP**, **VLANs**, **DHCP**, **DNS**, **HTTP** e **E-MAIL (SMTP e POP)**.  
- Implementar **roteamento inter-VLAN (Router-on-a-Stick)** para comunicação entre departamentos.  
- Tornar os **servidores centrais acessíveis a partir de qualquer rede**.  
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
- Os **servidores centrais** (HTTP e E-MAIL) estão localizados na VLAN 40 (Infraestrutura).  
- Todos os outros departamentos acessam os serviços da VLAN 40 através do roteador.

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
   - DNS, HTTP e E-MAIL (SMTP e POP)
6. **Teste a configuração IP, enlaces e conexões de rede** usando pacotes **ICMP (ping)** e os **sniffers** do Packet Tracer.  
7. **Teste o serviço DHCP:**
   - Adicione dispositivos e verifique se eles obtêm IP automaticamente.  
8. **Teste o serviço DNS:**
   - Faça um **ping para `ufba.br`** e **`cisco.srv`**.  
9. **Teste o serviço HTTP (servidor da VLAN 40):**
   - Acesse o **site da Superitendência de Tecnologia de Informação** (HTTP) a partir de dispositivos de outras VLANs.  
   - Altere o arquivo `index.html` e verifique se as alterações aparecem ao acessar de outros dispositivos.  
10. **Teste o serviço de E-MAIL (SMTP e POP):**
    - Configure os clientes de e-mail nos PCs das outras VLANs.  
    - Envie e receba mensagens entre departamentos utilizando os servidores de e-mail da VLAN 40 (Infraestrutura).  
11. **Garanta que todos os serviços (HTTP, DNS, DHCP e E-MAIL)** estejam acessíveis por qualquer rede.

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
- Cada LAN deve possuir seus dispositivos (PCs e servidores) interligados via **Switch Cisco 2950-24**.  
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
- **Não é necessário configurar serviços de DNS, HTTP ou E-MAIL nesta etapa.**

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
  - E-MAIL (SMTP e POP)
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
