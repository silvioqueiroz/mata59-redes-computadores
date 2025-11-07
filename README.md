# PROJETO — Superitendência de Tecnologia de Informação  
**Disciplina:** Redes de Computadores — Ciência da Computação — UFBA  
**Professor:** Leobino Sampaio  
**Aluno(s):** [Nome dos integrantes]  

---

## DESCRIÇÃO DO CENÁRIO

A **Superitendência de Tecnologia de Informação** está implementando sua infraestrutura de rede local e de interconexão entre departamentos.  
O projeto consiste em planejar, configurar e testar uma rede corporativa composta por **4 departamentos**, utilizando o **Cisco Packet Tracer** como ambiente de simulação.
Abaixo os critérios do projeto:
- Implementar **roteamento inter-VLAN (Router-on-a-Stick)** em um roteador 1941 com extensão de portas HWIE-4ESW
- Utilizar **topologia estrela**, com um **switch 2950-24** por departamento
- Cada departamento possui: **19 estações de trabalho (PCs)**, **2 Servidores** e **2 Impressoras**.
- Utilizar **endereçamento IP Classe C**
- Cada departamento deve estar em uma sub-rede
- Para a numeração IPs, deve-se usar uma sequência nas sub-redes de acordo com a máscara adotada
- Cada departamento será uma **VLAN distinta**
- Deve ser usada uma máscara de sub-rede que atenda a necessidade apresentada
- Configurar **endereçamento estático** para Engenharia e TI Interno
- Configurar **endereçamento dinâmico (DHCP)** para Compras e Infraestrutura
- As VLANs vedem ter 10 (VLAN01) e 09 (VLAN02) estações

Departamentos:
- Engenharia  
- Compras  
- TI Interno  
- Infraestrutura

---

## OBJETIVOS

- Criar uma topologia de rede lógica e funcional para a empresa **Superitendência de Tecnologia de Informação**.  
- Planejar e configurar **endereçamento IP**, **VLANs**, **DHCP**, **Gateways**.  
- Implementar **roteamento inter-VLAN (Router-on-a-Stick)** para comunicação entre departamentos.  
- Tornar os **servidores centrais acessíveis a partir de qualquer rede**.  
- Garantir **conectividade total entre todas as VLANs** entre todos os dispositivos.  
- Validar o funcionamento dos serviços de rede e da comunicação entre os setores.

---

## PLANEJAMENTO DE ENDEREÇAMENTO IP

| Departamento | Rede | 1º IP válido | Último IP válido | Broadcast | Gateway |
|---------------|-------------|----------------|------------------|------------|-----------|
| Engenharia |  x.x.x.x/z |  |  |  |  |
| Compras  | x.x.x.x/z |  |  |  |  |
| TI Interno |  x.x.x.x/z |  |  |  |  |
| Infraestrutura |  x.x.x.x/z |  |  | | |

---

## TOPOLOGIA GERAL

- **Roteador 1941** — realizando roteamento inter-VLAN (Router-on-a-Stick).  
- **Switches Cisco 2950-24** — um por departamento.  
- **Topologia Estrela**, com o roteador como ponto central.  
- **Quatro VLANs**: Engenharia, Compras, TI Interno e Infraestrutura.


---

## 🧭 INSTRUÇÕES

1. **Baixe e instale o [Cisco Packet Tracer](https://www.netacad.com/resources/lab-downloads?courseLang=en-US).**  
2. **Baixe e abra o arquivo [`template.pkt`](https://github.com/silvioqueiroz/mata59-redes-computadores/raw/refs/heads/main/template.pkt).**  
3. **Coloque os dispositivos e equipamentos de rede**, conforme o planejamento do projeto.  
4. **Conecte-os usando os enlaces apropriados (cabos e interfaces corretas).**  
5. **Configure as redes e serviços**:
   - VLANs
   - Endereçamento IP (estático e DHCP)
   - Roteamento inter-VLAN (Router-on-a-Stick)
   - Servidores e Impressoras
6. **Teste a configuração IP, enlaces e conexões de rede** usando pacotes **ICMP (ping)**.
7. Teste o serviço DHCP:
   - Adicione dispositivos e verifique se eles obtêm IP automaticamente.  
8. **Garanta que todos os serviços (HTTP, impressoras e DHCP)** estejam acessíveis por qualquer rede.

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
- **Não é necessário conectar as VLAN nesta etapa.**

---

## 🌐 2) ENTREGA DA INTERCONEXÕES DAS VLANS

### Arquivos exigidos
- Arquivo texto (**.txt**) contendo:
  - Nome / número do grupo  
  - Nome dos integrantes  
- Arquivo do Packet Tracer (**.pkt**)

### O que deve conter
- Dispositivos das **redes LANs** devidamente conectados e configurados.  
- O roteador Cisco 1941 deve estar configurado para realizar **roteamento inter-VLAN**.  
- Cada departamento deve estar em uma VLAN com gateway configurado no roteador.  
- **DHCP configurado apenas para Compras e Infraestrutura.**

### Critério de validação
- Comunicação entre todos os dispositivos das redes LAN e VLANS (ping entre departamentos).  
- Conectividade garantida por meio do roteamento configurado.  

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
- Configuração completa das **redes LAN e VLANS** com todos os dispositivos.  
- Todos os enlaces devidamente configurados e operantes.  
- **Conectividade total entre todos os dispositivos finais (ICMP ping).**  
- **Serviços de rede configurados e testados:**
  - DHCP
    
### Critério de validação
- Todas as redes (LAN e VLANS) funcionando e interconectadas.  
- Comunicação funcional entre todos os dispositivos (ping e acesso a serviços).  

---

## CONCLUSÃO

O projeto da **Superitendência de Tecnologia de Informação** propõe a implementação completa de uma rede corporativa, abordando desde o planejamento de endereçamento até a integração VLAN com todos os serviços de rede ativos.  
Através da simulação no **Cisco Packet Tracer**, o grupo deverá demonstrar conhecimento prático em VLANs, roteamento, DHCP e HTTP, garantindo conectividade e confiabilidade de comunicação entre os departamentos.

---

**Autor(es):** [Nomes dos integrantes]  
**Grupo:** [Número]  
**Curso:** Ciência da Computação — UFBA  
**Professor:** Leobino Sampaio   
