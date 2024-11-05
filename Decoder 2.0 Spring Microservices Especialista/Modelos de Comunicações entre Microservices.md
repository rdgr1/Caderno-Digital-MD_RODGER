## Base de Dados compartilhada ou Base de Dados por microservices
### Base de Dados Compartilhada
- Na migração de Monolítico para Microservices o uso de base de dados compartilhada é comum no inicio.
- Base de dados compartilhada garante forte consistência.
- Base de dados compartilhada gera forte acoplamento, sem isolamento de modelagem de dados.
### Base de Dados pro Microservices(Distrubuída)
Base de dados por microservice geram menor acoplamento na arquitetura e maior isolamento da modelagem de dados
Com base de dados por microservice temos que lidar com sincronia e replicação dos dados distribuídos
## Gestão de Dados Distribuidos 
![[Pasted image 20241105145206.png]]

![[Pasted image 20241105145133.png]]

### A busca é sempre pela maior disponibilidade possível...
Mesmo não exisitindo na realidade uma garantia de disponibilidade de 100%.
Por isso é comum vermos casos como disponibilidade de 99,99 ou 99,9999.....

## Disponibiliade em Microservices
Não criamos Microservices para que qualquer um possa parar em algum momento sem afear os demais,==mas sim para que alguns possam parar eventualmente e o sistema continuar disponível==
E isso já é muito melhor do que se nenhum pudesse parar.

![[Pasted image 20241105150339.png]]

## UUIDs - Identificadores Distribuídos
![[Pasted image 20241105150506.png]]

IDs do tipo UUID são identificadores temporais universalmente exclusivos e essenciais para a sincronia e replicação de dados distribuídos.

Podem ser gerados em qualquer lugar                   Garantem maior manuntenibilidade

Facilitam a replicação de dados                               Ùnicos em qualquer base de dados

## Modelo de Comunicações entre Microservices
- Comunicação via APIs 
- Comunicação via Mensageria
- Comunicação Híbrida

### Comunicação Sínctrona via APIs
![[Pasted image 20241105151026.png]]

Comunicação síncrona utilizando de métodos HTTP:
*GET*,*POST*,*PUT*,*DELETE*...

Modelo que requer o `Registry Discovery Pattern`,`Distributed Tracing Pattern`,`Circuit Breaker Pattern`...

*Pontos positivos*
- Forte consistência

**Pontos de atenção**
- Disponibilidade comprometida
- Comunicação bloqueante 
- Aumento acoplamento entre os Microservices

## Comunicação Assíncrona via APIs
![[Pasted image 20241105152019.png]]

*Pontos Positivos*
- Maior Disponibilidade
- Comunicação não bloqueante 
**Pontos de atenção**
- Aumento acoplamento entre os Microservices

![[Pasted image 20241105152215.png]]

![[Pasted image 20241105152313.png]]

![[Pasted image 20241105152425.png]]

## Mensageria via Comandos e Eventos 
![[Pasted image 20241105152819.png]]

Mensagerias via comando é quando uma api solicita ou no manda e envia mensagem para outro enviando sua solicitação

Já com eventos ele apenas notifica que tal ação ou tal evento ocorreu em certo microservice

## Comunicação Assíncrona via Mensageria Comandos
![[Pasted image 20241105153236.png]]

![[Pasted image 20241105153418.png]]

*Pontos positivos*
- Maior disponibilidade
- Menor Acoplamento
- Em casos de falhas, preserva-se a mensagem(tratativas das filas DLQ, reprocessamento....)

![[Pasted image 20241105153715.png]]

*Pontos positivos*
- Maior Disponibilidade
- Comunicação não bloqueante 

![[Pasted image 20241105153916.png]]

## Comunicação Assíncrona via Mensageria Eventos
![[Pasted image 20241105154320.png]]

*Pontos positivos*
- Menor acoplamento ainda 

![[Pasted image 20241105154350.png]]

![[Pasted image 20241105154447.png]]


## Comunicação Híbrida via API e Mensageria 
![[Pasted image 20241105154854.png]]

# Resumo de Modelos de Comunicações em Microservices
![[Pasted image 20241105154932.png]]

