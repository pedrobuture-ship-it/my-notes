---
quiz: true
---
# Mini Prova: TCP e UDP

## 1. O protocolo TCP é orientado à conexão, enquanto o UDP é não orientado à conexão (connectionless).
= true
> O TCP estabelece uma sessão (handshake) antes de enviar dados, ao contrário do UDP que apenas envia os datagramas sem garantia de entrega.

## 2. Qual protocolo garante a entrega dos pacotes, realizando a retransmissão em caso de perda?
- [x] TCP
- [ ] UDP
- [ ] IP
- [ ] HTTP
> O TCP possui mecanismos de controle de erro, controle de fluxo e retransmissão, garantindo que os dados cheguem corretamente e em ordem ao destino.

## 3. O protocolo ___ é frequentemente usado para streaming de áudio/vídeo e jogos online porque é mais rápido e tem menor latência.
= UDP | udp | User Datagram Protocol
> Como não exige handshake (aperto de mão) nem confirmação de entrega, o UDP tem menor latência, ideal para aplicações em tempo real onde a velocidade é mais importante que a precisão absoluta.

## 4. O processo conhecido como "Three-way Handshake" é utilizado por qual protocolo para estabelecer uma conexão?
- [ ] UDP
- [ ] ICMP
- [x] TCP
- [ ] DNS
> O TCP usa o aperto de mão de 3 vias (SYN, SYN-ACK, ACK) para iniciar e sincronizar uma conexão confiável entre cliente e servidor antes da troca de dados.

## 5. Cite uma situação ou tipo de aplicação em que é mais vantajoso utilizar o protocolo UDP em vez do TCP e explique brevemente o motivo.
? É mais vantajoso usar UDP em transmissões de vídeo ao vivo (streaming), chamadas de voz (VoIP) ou jogos online. O motivo é que o UDP é mais rápido por não exigir confirmação de recebimento (menor latência), e a perda de um pequeno pacote nessas aplicações (como um pequeno travamento na voz ou na imagem) não compromete a experiência geral.
> Em aplicações de tempo real, a entrega imediata dos dados é prioridade sobre a confiabilidade total, pois dados atrasados perdem sua utilidade.
