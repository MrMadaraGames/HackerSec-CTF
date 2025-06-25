 # #Crypto

![screenshot](/challenges/level-1/crypto/img/challenge.png)

*Iniciei lendo sobre o desafio e logo de início é notavel que a flag estará com algumas camadas a mais de proteção, mas vamos lá.*

*Sempre início com a leitura do código fonte, e algo muito estranho me chamou a atenção. Observe a imagem abaixo, tem algo estranho aqui ...*

 ![screenshot](/challenges/level-1/crypto/img/code_review.png)

*Confesso que não sabia do que se travava, e fui fazer as minhas pesquisas. Por incrível que pareça, estas linhas se trata de uma linguagem de programação "esoterica", (termo esse utlizado pela wikipedia em https://en.wikipedia.org/wiki/Brainfuck), criada em 1993 por Urban Muller.
Bem, entendendo melhor agora do que se tratava, utilizei a própria ferramenta de quebra de cifras disponivel na hackersec.*

*Baseado nisso, obtive o resultado abaixo:*

![screenshot](/challenges/level-1/crypto/img/brainfuck.png)

*Muito interessante, temos um arquivo oculto, mas onde estará este arquivo pass-.txt? Vamos procurar ...
O meu primeiro passo foi inspecionar a página do site e verificar no fonte se encontrava algum arquivo com este nome. Até encontrei vários arquivos, como sempre, vários e vários arquivos javascript, mas não encontrei nada.
Partir para testar a URL e no primeiro momento usei https://capturetheflag.com.br/challenge/crypto/pass-.txt mas não funcionou :(*

*Conhece algum hacker que desiste fácil? Eu não! Vamos continuar testando ... Fiz um novo teste, agora modificando a URL retirando o ```/crypto``` https://capturetheflag.com.br/challenge/pass-.txt e olha o que encontramos :-)*

![screenshot](/challenges/level-1/crypto/img/save_file.png)

*Achamos um arquivo, e logo fiz o download do mesmo. (Lembrando de sempre documentar cada passo do caminho!).
Dentro do arquivo encontrei os seguintes dados:*

```
MDIvMTIvMjEgLSBTZW5oYSBjcmlwdG9ncmFmYWRhIGVtIEMmZWFjdXRlO3Nhci4gKGVudHJlIGEgcm90YSZjY2VkaWw7JmF0aWxkZTtvIDYgZSAxMCk=
02/01/22 - I amvpi nwq itbmzili vwdiumvbm, iowzi mab&iikcbm; mu Dqomvmzm (kwu i amvpi kbn).
ekdrmtjl

```

*Oba, temos algo muito interessante aqui, temos um base64! Novamente utilizamos a ferramenta interna da hackersec e obtive mais informações, conforme segue abaixo:*

![screenshot](/challenges/level-1/crypto/img/base64.png)

*Com essas informações, partimos para quebrar essa criptografia de César. Seguindo a dica utilizamos a rotação 8 e funcionou ...*

![screenshot](/challenges/level-1/crypto/img/cesar.png)

*Sentir que estava muito próximo de conseguir resolver este desafio e assim obter a flag.
Diante da informação de que se tratava de cifra de Vegenere, partimos para quebrar mais essa também.*

*PS: Precisei realizar vários testes até conseguir, porque logo de início não conseguir entender qual seria o texto necessario para quebrar essa cifra, até entender que seria ``` ekdrmtjl ```*

![screenshot](/challenges/level-1/crypto/img/key.png)

*Após isso conseguir quebrar a cifra e encontrar a flag ```cryptohs ```*

![screenshot](/challenges/level-1/crypto/img/vegenere.png)

*E BINGoO. Flag!!*

![screenshot](/challenges/level-1/crypto/img/flag.png)
