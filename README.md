# 🌐 Topologia WAN com 3 Roteadores Cisco (VLSM & Roteamento Estático)

## 📌 Visão Geral
Este laboratório simula uma infraestrutura de rede corporativa conectando três matrizes/filiais distantes através de uma rede WAN. O objetivo é demonstrar o planejamento de endereçamento IP eficiente (VLSM), configuração de interfaces seriais/gigabit e roteamento estático no Cisco Packet Tracer.

![Topologia da Rede](Topologia%20da%20Rede.png)

---

## 📐 Arquitetura & Endereçamento IP

A rede foi dividida utilizando máscaras **/24** para as LANs e **/30** para os links ponto a ponto (WAN) entre os roteadores, otimizando o uso dos endereços IP.

| Dispositivo / Rede | Interface | Endereço IP / Máscara | Função / Descrição |
| :--- | :--- | :--- | :--- |
| **LAN Roteador 0** | Fa0/0 | `192.168.10.1/24` | Gateway Rede Local 1 |
| **Link WAN 0-1** | Fa0/1 | `10.0.0.1/30` | Conexão R0 <-> R1 |
| **Link WAN 0-1** | Fa0/1 | `10.0.0.2/30` | Conexão R1 <-> R0 |
| **Link WAN 1-2** | Fa0/0 | `10.0.0.5/30` | Conexão R1 <-> R2 |
| **Link WAN 1-2** | Fa0/1 | `10.0.0.6/30` | Conexão R2 <-> R1 |
| **LAN Roteador 2** | Fa0/0 | `192.168.20.1/24` | Gateway Rede Local 2 |

---

## ⚙️ Configurações Aplicadas

### 1. Roteamento Estático
Foram configuradas rotas estáticas manuais em todos os roteadores para garantir o tráfego de pacotes ponta a ponta entre as redes locais e as interfaces dos links de conexão.

---

## ✅ Validação e Testes de Conectividade

Para validar o funcionamento da topologia, foram realizados testes de `ping` entre as estações de extremidades opostas (Laptop0 até Laptop2/Laptop3), confirmando 100% de conectividade (`0% loss`):

![Teste de Ping](Teste%20de%20Ping.png)

---

## 📂 Como executar este projeto
1. Baixe o arquivo `.pkt` disponibilizado neste repositório.
2. Abra o **Cisco Packet Tracer**.
3. Carregue o projeto e realize testes de envio de pacotes ICMP (ping) no Command Prompt dos Laptops.
