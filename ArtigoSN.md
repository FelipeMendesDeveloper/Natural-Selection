# Seleção Natural
Uma breve simulação sobre a seleçao natural de Darwin

A ideia do projeto surgiu quando eu estava lendo sobre como a seleção natural funciona, quando tive a ideia de criar uma simulação desse processo, basicamente, criar indivíduo com características diferentes que podem: Reproduzir(Tendo em mente que as características dos filhos deverão ser herdadas do Pai), e Morrer.

Então, devemos considerar duas características genéticas, a camuflagem e a reprodução, quanto maior a camuflagem, menos chance do índivíduo morrer, e quanto maior a chance de reprodução, mais chance de ele ter um filho.

Porém devemos ter em mente, "quando", isso vai acontecer, por isso o programa usa "Turnos", em um turno será gerada uma chance de: Os indivíduos morrerem, e dos indivíuos terem filhos, em cada turno cada um individualmente pode morrer ou ter um filho, isso depende das chances indivíduais de cada um dos indivíduos, tendo em mente que indivíduos com mais de 50% de chance de camuflagem, terão filhos com mais de 50% de chance de camuflagem, e vice-versa para os com menos de 50%.

Logo, no início, serão gerados, 10 indivíduos com características totalmente aleatórias entre 1/100%, com 20 turnos para sobreviverem, e então serem deixados, se a seleção natural estiver correta, por volta do 5º todos os desaprovadoscom (com menos de 50% de camuflagem), devem ser extintos, e por volta do turno 14, deve acontecer um aumento exponencial na população de aprovados, acontecendo assim exatamente o que Darwin previu, a sobrevivência dos que melhor se adaptaram ao ambiente(De melhor camuflagem), e extinção dos que não se adaptaram(De menor camuflagem).

# Algoritmo para determinar as características de um filho(Genética)

Ok, vamos supor que um indivíduo X tem uma chance alta de reprodução, e consequentemente, teve um filho, como determinar as características desse filho?

Primeiro devemos definir, as características vão ser melhores ou piores do que as do pai? Nesse caso criamos uma chance binária para cada característica, se o resultado for 1, menor, se for 2, maior. Mas, quão maior ou quão menor? nesse caso, devemos gerar uma chance aleatória, considerando que X é aprovado a camuflagem do filho pode estar entre 50/100%, se fosse desaprovado, estaria entre 1/49%. Mas levando em conta que X é aprovado, criamos uma chance aleatória do quanto ele vai perder.

Vamos supor que nesse caso, o algoritmo está decidindo a camuflagem do filho de X, sendo que a camuflagem de X é 80% e que ela vai abaixar, e vai abaixar em 50%, com esses dados, para descobrir a camuflagem do filho, o seguinte calculo deve ser feito:

C = CP - (CP * CH / 100)

C = Camuflagem do Filho,
CP = Camuflagem do pai,
CH = O quão menor/maior a camuflagem vai ser,

*Nota-se, que o - foi usado pois foi gerado aleatóriamente que essa característica seria menor, caso fosse maior, seria usado +

Nesse caso temos:

C = 80 - (80 * 50 / 100).

C = 80 - 40.

C = 40.

Logo, temos como resultado do nosso algoritmo que a camuflagem do filho de X será de 40%, mas temos um erro aqui, X é um aprovado, é geneticamente impossível ele ter um filho desaprovado, logo, o algoritmo percebendo que o valor é menor que 50, coloca o valor mínimo que um aprovado deve ter ou seja "C" na verdade, é 50 ao invés de 40 por razões puramente genéticas, porém o contrário também poderia acontecer.

Se um desaprovado tivesse um filho, e a penultima parte do algoritmo desse ao filho dele um valor maior que 49%, o valor seria jogado para 49% que seria a maior camuflagem possível para um desaprovado.

# Sistema de morte

Como o algoritmo de morte funciona?

Bom, é dependente da camuflagem, é basicamente, 100 - C, se sua camuflagem é de 90%, você tem 10% de chance de morrer a cada turno, é básico e pode ser observado no código, mas decidi que seria necessário uma cessão sobre para esclarecer as demais dúvidas

# Avaliações finais

No fim, será  criado duas coisas:
Uma lista, que vai mostrar os indivíduos, e seus atributos.

E um gráfico de linhas sendo a linha vertical o número de indivíduos por turno, e na linha horizontal, os turnos, podendo ser observado o crescimento populacional quando o programa é rodado, sendo observado exatamente o que foi previsto anteriormente, desaprovados sendo extintos por volta do 3º turno, e aprovados tendo um crescimento exponencial a partir do 12º turno.
