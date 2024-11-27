
## **Capítulo 6: Camada de Enlace**

---

### **6.1 - Introdução à camada de enlace**

#### **6.1.1 Os serviços fornecidos pela camada de enlace**

- A camada de enlace é responsável por mover os dados de um nó a outro em uma rede.
- Serviços fornecidos:
    - **Framing:** Divide o fluxo de bits da camada física em quadros.
    - **Detecção de erros:** Identifica erros causados por ruídos durante a transmissão.
    - **Controle de fluxo:** Coordena a velocidade de transmissão entre emissor e receptor.

#### **6.1.2 Onde a camada de enlace é implementada?**

- Implementada no adaptador de rede (NIC).
- Pode ser implementada em hardware ou software, dependendo do dispositivo.

---

### **6.2 - Técnicas de detecção e correção de erros**

#### **6.2.3 Verificação de Redundância Cíclica (CRC)**

- **Conceito:** O CRC é um algoritmo para detecção de erros. Baseia-se na divisão polinomial entre a mensagem e um gerador polinomial.
- Processo:
    1. Acrescenta-se r bits de 0 à mensagem (onde r = grau do gerador).
    2. Realiza-se a divisão binária.
    3. O resto da divisão é o **CRC**.

#### **Aplicação na questão 4:**

- Gerador: `1001`
- Dados: `10011111`  
    **Resposta:** Após realizar a operação:
    - Resultado do CRC: **110**

---

### **6.3 - Enlaces e Protocolos de Acesso Múltiplo**

#### **6.3.2 Protocolos de Acesso Aleatório - CSMA/CD**

- **CSMA/CD:** Carrier Sense Multiple Access with Collision Detection.
- Funcionamento:
    1. Escuta o canal antes de transmitir (Carrier Sense).
    2. Se o canal estiver livre, envia os dados.
    3. Caso ocorra uma colisão, os dispositivos detectam e retransmitem após um atraso aleatório.

---

### **6.4 - Redes Locais Comutadas**

#### **6.4.1 Endereçamento na camada de enlace e ARP**

- **Endereços MAC:** São endereços físicos únicos de 48 bits atribuídos ao adaptador de rede.
- **Protocolo ARP (Address Resolution Protocol):** Converte endereços IP em endereços MAC.

---

## **Capítulo 4: A camada de rede - Plano de Dados**

---

### **4.1 Visão Geral da Camada de Rede**

#### **4.1.1 Repasse e roteamento**

- **Repasse (Forwarding):** Movimenta pacotes entre portas de entrada e saída no roteador.
- **Roteamento (Routing):** Determina o caminho que os pacotes percorrem até o destino.

#### **4.1.2 Modelo de serviço de rede**

- Define como os dados são entregues (e.g., melhor esforço, garantias de atraso, etc.).

---

### **4.2 O que há dentro de um roteador?**

#### **4.2.1 Processamento na porta de entrada e repasse baseado em destino**

- **Processamento na porta de entrada:**
    - Examina o cabeçalho do pacote.
    - Consulta a tabela de repasse.
- **Repasse baseado em destino:** O roteador decide a interface de saída com base no endereço de destino do pacote.

---

### **4.3 Protocolo IPv4, endereçamento e IPv6**

#### **Formato de datagrama IPv4**

- Componentes principais:
    - **Cabeçalho:** Contém informações como endereço de origem, destino, e TTL.
    - **Dados (Payload):** Informações úteis transportadas no pacote.

#### **Endereçamento IPv4**

- Formado por 32 bits, dividido em 4 octetos (valores de 0 a 255).
- Utiliza máscaras de sub-rede para dividir redes em sub-redes menores (CIDR).

#### **IPv6**

- Endereçamento de 128 bits.
- Resolve as limitações do IPv4, como o número reduzido de endereços disponíveis.

---

### **Fragmentação**

- Ocorre quando um pacote excede o tamanho máximo permitido pela rede.
- Os pacotes são divididos em fragmentos e reagrupados no destino.

---

### **Protocolo DHCP**

- **Dynamic Host Configuration Protocol (DHCP):**
    - Configura automaticamente endereços IP e outros parâmetros de rede (gateway, DNS).
- **Vantagens:**
    - Reduz erros manuais e facilita a administração.
- **Desvantagens:**
    - Pode ser vulnerável a ataques como spoofing.

---