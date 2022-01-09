## O que é um protocólo ?
- É uma linguagem de comunicação que vai ser utilizado entre 2 dispositivos para trocar informacoes entre um emissor e receptor.

## Modelo OSI
- É um modelo **teórico** que define como os protocólos vão se comunicar.
- A camada OSI possui 7 camadas que são as descritas abaixo
![teste](https://www.dltec.com.br/blog/wp-content/uploads/2019/02/osi-tcp-ip.png)
### PDU
- Cada camada vai criar seu próprio pacote de dados de controle, isso é chamado de PDU(Protocol Data Unit), isso significa que em as camadas(mesmo nem todas gerando novos cabecalhos) adicionam o cabecalho para área de dados da próxima camada, fazendo assim com que nenhuma camada tenha acesso ao cabecalho da outra.
### Aplicacão
- É a camada mais externa, tem maior contato com a aplicacaO. PDU é a mensagem
### Apresentacao
-  Responsável entre a conversão de formatos, compresão de dados, protocólo de criptografia como o SSL(Secure Socket Layer) e TLS. A mensagem ainda está inteira e não foi picotada até o momento.
### Sessão
- Cria uma sessão entre o emissor e o receptor, criar uma sessão é importante para caso algum problema ocorra na transferencia de dados seja possível recuperar a partir do ponto que deu problema.
### Transporte
- Serve de interface entre as camadas anteriores que são de alto nível com as camadas de baixo nível. Essa camada pega a mensagem da camada anterior e vai dividir essa mensagem em pacotes de dados menores para serem transportadas pelas próximas camadas. A camada de transporte pode trabalhar com alguns protocólos de comunicao como o TCP e UDP e tem abordagens distintas, já que sabemos que o TCP é um protocólo confiavel e o UDP não.
- Quando a camada de transporte utiliza o protocólo TCP para a comunicacão ele segmenta e numera cada segmento, e quando o dado for recebido para o receptor ele irá avisar que os dados chegaram tranquilo e depois ordena os pacotes 
### Rede
- Temos alguns protocolos que vão ser utilizados, o IPv4, IPv6. IPsec e ICMP que são protocolo de comunicacao entre redes. O pdu é o Datagrama IP. O Ipv4 utiliza o checksum apenas no cabecalho.
- Existe o endereco físico é o endereco daquela máquina (MAC) o endereco lógico são atribuidos na camada de rede e o engenheiro de redes que vai definir 
### Link de Dados
- Encapsula a o datagrama IP em mum quadro(tamanho variável) ou uma Célula(tamanho fixo)
## TCP/IP

### Aplicação
- É a camada que recebe a requisicao, ou seja o browser faz uma chamada HTTP e envia o dado nessa camada. No cabecalho é setado a porta que vai ser acessada no lado receptor.

### Transporte
- Na Camada de transporte a PDU define qual o protocólo será utilizado, o TCP ou PDU no cabecalho

### Rede ou Internet
- Encapsula toda o Camada anterior e cria datagrama IP, que é o resultado que será enviado para a camanda de Acesso a Rde, no  entanto se o tamamnho do dado enviado seja maior do que a camada de redes aguenta o datagrama IP vai ser quebrado em pedacos menores. No cabecalho será adicionado o Ip de origem e de destino. No cabecalho será descrito qual tipo de rede que vai ser direcionado(IPV4,IPV6 entre outros)

### Link de dados
- Vai verificar novamente se o tamanho do datagrama é compatível com a camada de Link de dados, e quebrar ele caso não seja, no en

