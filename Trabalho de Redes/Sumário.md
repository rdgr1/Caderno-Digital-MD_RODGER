## Tema: **Protocolo OSPF**
### Etapas do trabalho:
# Trabalho de Simulação do Protocolo OSPF

## Etapas do Trabalho

1. **Instalação do Cisco Packet Tracer**
   - O grupo deverá instalar o Cisco Packet Tracer em um computador.
   - **Link do curso gratuito**: [Cisco Packet Tracer - Networking Simulation Tool](https://netacad.com) *(basta fazer uma conta e realizar o curso).*

2. **Simulação do Protocolo**
   - O grupo deverá simular o protocolo que escolheu.
   - Entender o que está acontecendo e como o protocolo funciona.
   - O ambiente simulado já existe no Packet Tracer:
     - Caminho: `File > Open Samples > 01 Networking`.
     - **OBS:** Todos os protocolos estão nessa pasta.

3. **Gravação do Vídeo**
   - O vídeo deverá conter:
     - **A explicação, por aluno, de tudo o que ocorre na simulação.** *(Não precisa gravar a instalação do Packet Tracer).*
     - A simulação deve aparecer no vídeo.
     - A gravação deve ser feita usando um software de videoconferência, como:
       - **Skype, Google Meet, Teams, etc.**
     - Todos os integrantes do grupo devem aparecer no vídeo.
       - Caso não tenha câmera no computador, usar celular.

4. **Envio do Vídeo**
   - O aluno deve disponibilizar o **link do vídeo** na atividade.
   - O vídeo pode ser enviado para o YouTube:
     - Configurado como **"Não listado"** (apenas quem tem o link poderá assistir).
   - Ou usar o Google Drive para disponibilizar o link.
   - **IMPORTANTE:** Não enviar vídeos em formato MP4 diretamente. Apenas o **link** será aceito.

5. **Critérios de Avaliação**
   - A apresentação será avaliada individualmente.
   - O vídeo deve ter um **tempo mínimo de 10 minutos** e **máximo de 20 minutos**.

---

## Estrutura Recomendada para o Vídeo

### 1. **Introdução (1-2 minutos)**
   - Todos os integrantes se apresentam.
   - Explicação do objetivo do vídeo:
     - **"Vamos simular o protocolo OSPF, explicar seu funcionamento e demonstrar suas operações no Packet Tracer."**

---

### 2. **Simulação no Packet Tracer (15-16 minutos)**

#### Divisão de conteúdo entre os integrantes:
- **Configuração Inicial**
  - Habilitar OSPF nos roteadores.
  - Associar interfaces às áreas (Área 0 e outras).
  - Exemplo de comando: 
    ```bash
    router ospf 1
    network [ip] [wildcard-mask] area 0
    ```
  - Configurar as redes conectadas.

- **Formação de Adjacências**
  - Demonstração de pacotes Hello.
  - Uso do comando:
    ```bash
    show ip ospf neighbor
    ```
  - Explicação dos estados de formação: Down, Init, 2-Way, Full.

- **Áreas e Design**
  - Mostrar áreas hierárquicas:
    - Área backbone (Área 0) conectada às demais.
  - Demonstrar o uso de links virtuais.

- **Cálculo de Rotas**
  - Alterar o custo de um enlace para observar o impacto no roteamento.
  - Explicação sobre o cálculo de rotas usando o Algoritmo de Dijkstra.
  - Comando para exibir rotas:
    ```bash
    show ip route
    ```

---

### 3. **Encerramento (2 minutos)**
   - Resumo dos principais conceitos abordados:
     - O que é OSPF?
     - Benefícios do protocolo em redes grandes.
     - Demonstrações práticas realizadas.
   - Todos os integrantes agradecem e encerram o vídeo.

---

## Dicas Finais

- **Ensaiem antes de gravar:** 
  - Cada integrante deve saber sua parte e a explicação correspondente.
  
- **Use comandos de verificação no Packet Tracer:**
  - Exemplos:
    ```bash
    show ip ospf
    debug ip ospf events
    ```

- **Gravação com Webcam:**
  - Cada aluno deve aparecer no vídeo enquanto fala.
  - Ferramentas recomendadas: Zoom, Google Meet, Skype.

- **Envio do Vídeo:**
  - Lembre-se de configurar o vídeo como **"Não listado"** no YouTube ou compartilhar pelo Google Drive.

