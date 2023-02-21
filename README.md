# Traffic Filter using state machines

<div align="center"> 
In this traffic filter, a combination is expected. When this combination is detected, the alarm is triggered and the system is locked, preventing an attack. More information in the report bellow.
 </div>
 <div align="center"> 
This traffic filter was a proof of my graduation in computer engineering.
 </div>
<div align="center"> 
<img src="https://media0.giphy.com/media/qi29MoLjWNPUI/giphy.gif?cid=ecf05e475d54lco64cgouxmhrd1qjycjye72z01yts9ascc2&rid=giphy.gif&ct=g" >
  </div>
  <div align="center"> 
 🙋‍♂️ Thanks for visiting my repository!
</div>

# Traffic Filter (Portuguese)

<div align="left"> 
A máquina de estados implementada possui quatro estados: espera, buscando, perigo e blocking. Cada estado recebe um valor de “prog” ou, enquanto no estado buscando, um 
“match” e executa determinada ação. Assim, gerando o funcionamento correto do sistema.
 </div>
 <div align="left"> 
Estado espera: esse estado é ativado quando o sistema está esperando um valor de 
“prog” para executar determinada ação, ou seja, enquanto o prog continua com valor 
zero, continuará esse estado ativo. Assim, quando o estado receber prog=1 ativará a
comparação com o padrão 1 (ent1=’1’), quando receber prog=2 ativará a comparação 
com o padrão 2 (ent2=’1’), e quando receber prog=3 ativará a comparação com o 
padrão 3 do sistema (ent3=’1’)
 </div>
 <div align="left"> 
 Estado buscando: é ativado no momento em que é recebido um prog=4 no estado espera. Enquanto estiver nesse estado, é verificado se ocorre alguma igualdade no sistema, assim, se ocorrer (recebe um match dos comparadores), é ativado o estado perigo. Caso receba um prog=5, é ativado diretamente o estado blocking. Se receber um prog=7 o sistema reativa o estado espera. Nesse estado, o contador de clocks 
(cont) está sempre em 0.
 </div>
  <div align="left"> 
 Estado Perigo: É acionado, como explicado anteriormente, pelo match=1 recebido pelo estado buscando. Ele fica ativo até quatro clocks com o alarme ativado e retorna, 
posteriormente, ao estado buscando, caso não receba prog=5 (ativaria o estado blocking) e zera o contador de clocks (cont).
 </div>
 <div align="left"> 
Estado Blocking: fica ativo quando recebe um prog=5 (ataque) no estado perigo ou buscando, os quais podem detectar um ataque, e ativa o alarme. Após o bloqueio dos 
dados, quando recebe um prog=7, o estado espera é reativado. Também, o estado blocking pode reativar o estado buscando quando receber um prog=6.
 </div>
 
 
 

