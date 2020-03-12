## Mapeando... 

Me veio a cabeça como eu faria para detectar em um range de IP´s , quais destes seriam estações ou servidores windows. Alguém pensou SMBGhost?! ;D  Então, depois de quebrar a cabeça de como eu faria para filtrar toda a saída do nmap para só me mostrar o IP e o "fingerprint" do sistema, se usava CUT, TAIL, HEAD, AWK, etc., acabei chegando em uma solução que funcionou para mim, que foi: 

*Vou colocar um marcador ("=>") na informação que eu quero e depois faço um grep pelo marcador* e voilá. 

  nmap  -O -T5 -Pn -n XX.XX.XX.XX/XX | sed -e 's/Nmap scan report for/SERVER =>/' -e 's/OS CPE:/OS CPE =>/' -e sed 's/Aggressive OS guesses:/OS =>/' | grep '=>'

Talvez hajam outras formas muito mais elegantes e até mais rápidas, mas para mim, deu o resultado que eu queria ;D

### Sem mais por enquanto

Apenas um espaço a mais para colocar minhas anotações para mim mesmo e para quem mais julgar que valha a pena ler. Não tenho nenhum compromisso com a verdade, pois não sei qual é ela, logo o que escrevo aqui pode estar certo mas também pode estar errado, já que o caminho é um aprendizado feito de erros para se chegar nos acertos ;D

Por favor, será de grande valia se, o que estiver errado aqui, seja apontado com a proposição da correção. Todos nos ajudaremos. 
