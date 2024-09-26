### Internet:

A **Internet** é um rede de computadores que *interconecta* bilhões de dispositivos de **computação** ao redor do mundo.

#### Descrição dos componentes de Rede:

Na *área de rede* todos os equipamentos conectados são chamados de *hospedeiros* e *sistemas finais*.

**Sistemas Finais** são conectados entre si por **enlaces**(*links*) **de comunicação** e **comutadores**(*switches*) **de pacotes**.
#### Nó:
Um nó (ou **nó de rede**) é um ponto de interconexão dentro de uma rede de comunicação. Em termos simples, é qualquer dispositivo ou sistema que esteja conectado à rede e tenha a capacidade de enviar, receber ou transmitir dados.
##### Enlace:
Existem vários tipos de **enlaces** que são *constítuidos* de diferentes *tipos* de meios **físicos**, entre eles cabos *coaxiais*, fios de *cobre*, fibras *óticas* e ondas de *rádio*, enlaces diferentes podem transmitir dados em taxas diferentes, sendo a **taxa de transmissão** de uma enlace medida em bits por segundo.
##### Processo de envio de dados:
Quando um *sistema final* possui dados para enviar para outro *sistema final*, o sistema emissor segmenta esses *dados* e adiciona *bytes* no cabeçalho a cada segmento. Os blocos de informação *resultantes*, conhecidos como **pacotes** no jargão de redes de computadores, são enviados através da rede ao sistema *final de destino,* onde são *remontados* na forma dos *dados originais.*

##### Comutadores de pacotes:
Um nó de *comutação* de pacotes encaminha o pacote que está chegando em um de seus enlaces de comunicação de *entrada* para um de seus enlaces de comunicação de *saída*.
Há comutadores de pacotes de todos os *tipos e formas* mas os dois mais *proeminentes* na Internet de hoje são **Roteadores** e **Switches.** Esses dois tipos de nós de comutação encaminham pacotes a seus destinos finais. Os switches geralmente são utilizados em **redes locais**, enquanto os roteadores são utilizados principalmente na parte mais *interna da rede*.

![[Pasted image 20240926125752.png]]

A sequência de *enlaces de comunicação* e *nós de comutação de pacotes* que um pacote percorre desde o sistema final *remetente* até o sistema final *receptor* é conhecida como rota ou caminho através da rede. 

### Analogia:

As redes **comutadas** por *pacotes* (que transportam pacotes) são, de muitas maneiras, semelhantes às redes de transporte de *rodovias, estradas e cruzamentos* (que são percorridas por veículos). Considere, por exemplo, uma fábrica que precise transportar uma quantidade de *carga muito grande* a algum depósito localizado a *milhares de quilômetros*. Na fábrica, a carga é dividida e carregada em uma frota de *caminhões*. Cada caminhão viaja, de modo independente, pela rede de rodovias, estradas e cruzamentos ao depósito de destino. No depósito, a carga é *descarregada* e *agrupada* com o resto da carga pertencente à mesma remessa. Deste modo, os *pacotes* se assemelham aos *caminhões*, os enlaces de comunicação representam *rodovias e estradas*, os nós de comutação seriam os cruzamentos, e cada sistema final se assemelha aos *depósitos*. Assim como o caminhão faz o percurso pela rede de transporte, o pacote utiliza uma rede de computadores.

##### ISPs 
Sistemas finais acessam a Internet por meio de **ISPs**, (do inglês **Internet Service Providers** — Provedores de Serviços de Internet), entre eles: **ISPs** residenciais como empresas de TV a cabo ou empresas de telefonia; corporativos, de universidades e que fornecem acesso sem fio em aeroportos, hotéis, cafés e outros locais *públicos*;
##### ISPs Móveis
que oferecem acesso aos nossos smartphones e a outros dispositivos.
Cada **ISP** é uma rede de *nós* de *comutação* e enlaces de comunicação.
**ISPs** oferecem aos **sistemas** finais uma variedade de tipos de acesso à rede, incluindo acesso residencial de banda larga como modem a cabo ou DSL *(do inglês digital subscriber line — linha digital de assinante),* acesso por **LAN** de alta velocidade e acesso **sem fio móvel.** Os **ISPs** também fornecem acesso a provedores de **conteúdo**, conectando servidores diretamente à Internet. A **Internet** trata fundamentalmente da conexão entre os **sistemas finais**; portanto, os **ISPs** que fornecem acesso a esses sistemas também devem se **interconectar**. Esses **ISPs** de nível mais **baixo** são interconectados por meio de ISPs de nível mais **alto**, *nacionais e internacionais.* Um ISP de nível mais **alto** consiste em roteadores de *alta velocidade* interconectados com *enlaces* de fibra ótica de *alta velocidade*. Cada rede *ISP*, seja de nível mais *alto ou mais baixo*, é gerenciada de forma *independente*, executa o *protocolo IP* (ver adiante) e obedece a certas convenções de *nomeação* e *endereçamento*.

Os sistemas finais, os nós de comutação e outras peças da Internet executam protocolos que controlam o envio e o recebimento de informações.

##### TCP:
do inglês *Transmission Control Protocol* — Protocolo de Controle de Transmissão.
##### IP:
do inglês *Internet Protocol* — Protocolo da Internet.
O protocolo IP especifica o formato dos pacotes que são enviados e recebidos entre roteadores e sistemas finais.

#### RFCs: 
**RFCs** (do inglês Request For Comments — pedido de comentários). Os **RFCs** começaram como **solicitações** gerais de **comentários** (daí o nome) para resolver **problemas** de **arquitetura** que a *precursora da Internet* enfrentava (Allman, 2011). Os **RFCs** costumam ser bastante técnicos e detalhados. Definem protocolos como **TCP, IP, HTTP** (para a Web) e **SMTP** (para e-mail). Hoje, existem quase *9.000 RFCs.*

##### Aplicações Distribuidas:
Além de aplicações tradicionais como **correio eletrônico** e **navegação na Web**, as aplicações de Internet incluem **aplicativos** para **smartphones** e **tablets**, incluindo serviços de **mensagem** instantânea, **mapeamento** com informações em tempo real sobre condições de **trânsito**, **streaming** de *músicas*, *filmes* e *televisão*, mídias sociais on-line, videoconferência, jogos **multiplayer** e sistemas de **recomendação** baseados em **localização**. Essas aplicações são conhecidas como **aplicações distribuídas*** , uma vez que envolvem diversos sistemas finais que trocam informações *mutuamente*.



