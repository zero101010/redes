## Pacote de dados
- O pacote de dados possui uma estrutura básica que é cabecalho, área de dados e o Rodapé.
### Cabecalho
- Possui informacoes de controle, como endereco do dispositivo que vai enviar o dado, do dispositivo que vai receber e o tamanho dos dados 

### Área de dados
- Contém os dados a serem transmitidos
### Rodapé
- Normalmente envia dados que são necessários mas que não são definidos no cabecalho, um exemplo é o resultado do checksum

## Tipos de mensagens eviadas pelos pacotes
### Unicast
- Mensagem que envia o dado para somente um destinatário
### Broascast
- Mensagem que é enviada para todas as máquinas das redes
### Multicast
- A mensagem é enviada somente pra um grupo de máquinas das redes

// TODO ver uma forma de fixar essa parte 
## Confirmaçao de entrega de dados
### Acknowledge (ACK)
- É um pacote de confirmacao da entrega de dados é enviado pelo emissor dentro de um período de tempo esperado, ele sabe que o destinatário não recebeu o pacote, é muito comum em tipos de mensagens que precisam de uma garantia, como por exemplo o TCP

### Negative Acknowledge
- É quando não é necessário enviar um pacote de confirmacao para garantir que o pacote foi recebido, isso é muito comum em tipos de mensagens que precisam de menos complexidade e mais velocidade, como o UDP(que é para jogos)

## Handshake
- É um pacote de controle para estabelecer uma conexão entre 2 máquinas, após conexão ser estabelecida elas trocam os informacoes através de pacotes.


## Tratativas de erros ao enviar pacotes de dados
### Repetição
- É quando o emissor envia o mesmo pacote de dados uma quantidade x de vezes, e o receptor compara os x pacotes para verifiar se os pacotes estão iguais, caso não esejam iguais é retornado um erro dizendo que o dado foi corrompido e requerindo que o pacote seja reenviado novamente. O problema dessa abordagem é o fato de consumir mais banda que o necessário para garantir o envio do pacote.
### Checksum
- Soma uma quantidade x de bits da mensagem, e salva no rodapé do pacote. Após o envio o servidor que recebeu o pacote vai ler o rodapé, pegar o dado do checksum anterior, fazer a soma novamente dos x bits e comparar com o valor pego no rodapé, caso dê um valor diferente retorna mensagem dizendo q o valor está corrompido, o problema de se utilizar essa forma é a possibilidade pequena, mas n nula de gerar um falso positivo, por conta da quantidade x de bits ser limitada, então não é possível fazer a soma de todos os bits do pacotes, somente de um conjunto x. Um exemplo é ter um pacote com 65 bits e usar como base para o checksum somente os últimos 16 bits menos significativos, essa chance de erro é chamado de colisão, pois se acontecer algum problema fora dos últimos 16 bits ele vai retornar um falso positivo.

### CRC( Cyclical Redundancy Check)
- É equivalente ao checksum, no entanto ao invés de somar executamos uma divisão com a soma de todo o pacote por um valor que é decidido, salva no rodapé e compara novamente no receptor executando a mesma divisão e verifica se o resultado é o mesmo que está no rodapé
