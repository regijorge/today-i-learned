# Prefácio

## Filosofia dos 5S
1) Seiri - organização (ordenar)
Saber onde estão as coisas, usar abordagens como nomes adequados
> Deve-se escolher o nome de uma variável com cuidado, como se fosse seu primeiro filho

2) Seiton - arrumação (sistematizar)
Um pedaço de código deve estar onde vocẽ espera encontrá-lo. Caso não esteja, refatore-o e coloque lá!

3) Seiso - limpeza (polir)
Código cheio de comentários, livre-se deles

4) Seiketsu - padronização
Ter um estilo de programação consistente e uma séria de boas práticas

5) Shutsuke - disciplina
Isso significa ter disciplina para seguir as práticas e refletir frequentemente sobre isso no trabalho e estar disposto a mudar


> Lei de LeBlanc "Mais tarde é igual a nunca"

* O código limpo faz bem apenas uma coisa
> O código limpo parece que foi feito por alguém que se importa - Michael Feathers

* Efetue todos os testes
* Sem duplicação de código
* Expressa todas as ideias deo projeto que estão no sistema
* Minimiza o número de entidades como classes, metodos, funções e outras do tipo

> Não é a linguagem que faz o software parecer simples, é o programador!
> Deixe a área do acampamento mais limpa do que quando vocẽ a encontrou

## Dicas para criação de bons nomes
### Use nomes que revelem seu propósito
> O nome de uma variável, função ou classe deve responder todas as grandes questões. Ele deve lhe dizer porque existe, o que faz e como é usado, se um nome requer um comentário, então ele não revela seu propósito

### Evite informações erradas
> Devemos evitar passar dicas falsas que confundam o sentido do código. Devemos evitar usar palavras cujos significados fujam daquilo que desejamos. EX: não use "accountList" se não se trata de uma lista, a palavra "list" traz um significado de que é um array
> Evite usar palavras muito parecidas ex: "document" e "documents"

### Faça distinções significativas
Evite o seguinte uso: "product" e "productData", pois não conseguimos expressar exatamente do que trata cada uma. Faça as distinções dos nomes de uma forma que o leitor compreenda a diferença

### Use nomes pronunciáveis
Evite nomes como "genymdhms"

### Use nomes passíveis de busca
Crie nomes que seja fácil de buscar depois

### Evite o mapeamento mental
> Uma diferença entre um programador esperto e um profissional é que este entende que clareza é fundamental. Os profissionais usam seus poderes para o bem e escrevem códigos que os outros possam entender

### Nomes de classes
Classes e objetos devem ter nomes com substantivos como "Customer" e "WikePage" evite palavras como "Manager" e "Processor"

### Nomes de métodos
Devem ter verbos como "postPayment", "createUser"

### Selecione uma palavras por conceito
Escolha uma palavra por cada conceito abstrato e fique com ela. É confuso ter "fetch", "retrieve" e "get" como métodos equivalentes de classes diferentes

### Não faça trocadilhos
Evite usar a mesma palavra para dois propósitos. Usar o mesmo termo para ideias diferentes é basicamente um trocadilho

### Adicione um contexto significativo
Use prefixo caso haja necessidade de expressar um significado ex: "addFirstName"
Mas não adicione mais contexto a um nome além do que é necessário

## Funções
### Pequenas
A primeira regra das funções é que elas precisam ser pequenas.

### Blocos e endentação
* Blocos dentro de instruções "if, else", "while" e outros devem ter apenas uma linha, possivelmente uma chamada de função. Além de manter a função pequena isso adiciona um valor significativo pois a função chamada de dentro do bloco pode receber um nome descritivo
* O nível de identação de uma função deve ser de, no máximo, 1 ou 2, assim facilita a leitura e compreensão das funções

### Faça apenas uma coisa
> As funções devem fazer apenas uma coisa, devem fazer ela bem e devem fazer apenas ela
* Uma forma de saber se uma função faz mais de uma coisa é se vocẽ consegue extrair uma outra função a partir dela (sem que seja uma reformulação da implementação)

### Um nível de abstração por função
Afim de afirmar se nossas funções fazem só uma coisa, precisamos verificar se todas as instruções dentro da função estão no mesmo nível de abstração
Vários níveis de abstração dentro de uma função sempre geram confusão

### Ler o código de cima para baixo (regra decrescente)
Desejamos que cada função seja seguida pelas outras no próximo nível de abstração de forma que possamo ler o programa descendo um nível de abstração de cada vez

### Switch
São aceitáveis se aparecerem apenas uma vez como como para a criação de objetos polimórficos e estiverem escondidas atrás de uma relação de herança de modo que o resto do sistema não possa enxergá-la

### Parâmetros de unção
A quantidade ideal de parâmetros para uma função é **zero** (nulo), depois vem **um** (mônade), seguido de **dois** (díade). Sempre que possível deve-se evitar **trés** parâmetros (tríade)

### Parâmetros lógicos
Passar um boolean para uma função, certamente é uma prática horrível!, ois ele complica imediatamente a assinatura de um método, mostrando explicitamente que a função faz mais de uma coisa. Ela faz uma coisa se o valor for vedadeira e outra se for falso!

### Objetos como parâmetros
Quando uma função parece precisar de mais de dois ou trẽs parâmetros, é possivel que alguns deles podem ser colocados em uma classe própria

### Listas como parâmetros
Se os parâmetros variáveis forem todos tratados da mesma forma, então eles serão equivalents á um único parâmetro.

### Verbos e palavras-chaves
Escrever bons nomes para funções pode ir desde explicar o propósito da função á ordem e à finalidade dos parâmetros. No caso de uma mônade a função e o parâmetro devem formar um belo par **verbo/substantivo** por exemplo "write(name)", um nome ainda melhor seria "writeField(name)" que nos diz que o nome é um campo

### Evite efeitos colaterais
Efeitos colaterais são "mentiras": sua função promete fazer uma coisa, mas ela faz outras coisas escondidas.

### Separação comando consulta
As funções devem fazer ou responder algo, mas não ambos. Sua função, ou altera o estado de um objeto ou retorna informações sobre ele. Efetuar as duas tarefas costuma gerar confusão.

### Tratamento de erro é uma coisa só!
As funções devem fazer uma coisa só. Tratamento de erro é uma coisa só! Portanto, uma função que trata de erros não deve fazer mais nada. Ao usar um try/catch, numa função o "try" deve ser a primeira instrução e nada mais deve vir após os blocos "catch/finally"

### Evite repetição
A duplicação pode ser a raíz de todos os males no software. Muitos princípios e práticas tem sido criados com a finalidade de controlá-la ou eliminá-la.

### Evite comentários
* Evite comentários, na maioria das vezes eles mentem

### Comentários TODO
É aceitável colocar notas TODO como comentários

# Formatação

## Formatação vertical
Quanto menos linhas um arquivo tiver, melhor!
Pode-se considerar um máximo de 500 linhas

### Espaçamento vertical
Adicionar linhas em branco entre o código para delimitar contextos facilita a leitura do código

### Continuidade vertical
Assim como espaçamento vertical indica agrupamento de conceitos, é importante manter as linhas relacionadas sempre unidas

### Funções dependentes
* Se uma função chama outra num mesmo arquivo, elas devem ficar verticalmente próximas
* A função que chamar deve ficar acima da qui foi chamada


## Formatação horizontal
No máximo até 120 caracteres por linha, o ideal seria 80

# Objetos e estruturas de dados

## Lei de Demeter
Um módulo não deve enxergar o interior dos objetos que ele manipula. Um objeto não deve expor sua estrutura interna por meio dos métodos acessores

# 7 Tratamento de erros

## Try-catch-finally
Um boa prática é usar o block "try-catch-finally" quando for escrever um código que talvez lance exceções

## Forneça exceções com contexto
Cada exceção lançada deve fornecer contexto o suficiente para determinar a fonte e a localização de um erro

## Não retorne "null"
Quando retornamos "null" estamos criando mais trabalho para nós mesmo e estamos jogando problemas em cima de nossos "chamadores"
Se vocẽ ficar tentado a retornar "null" de um método, em vez disso, considere lançar uma exceção ou retornar um objeto Special Case

## Não passe "null"
Retornar "null" é ruim, mas passar ele é ainda pior

# Testes de Unidade
## As 3 leis do TDD
1) Não se deve escrever um código de produção até criar um teste de unidade de falhas (muitas vezes a diferença de tempo vai ser de 30 segundos)
2) Não se deve escrever mais de um teste de unidade do que o necessário para falhar, e o não compilar é falhar
3) Não se deve escrever mais códigos de produção do qeu é necessário para aplicar os teste de falha atual

Os códigos de teste são tão importantes quanto de produção. Ele requer raciocínio, planejamento e cuidado. É preciso mantẽ-lo tão limpo quanto o de produção

1) Fast: Os testes precisam ser rápidos, devem executar com rapidez.
2) Independent: Os teste não devem depender uns dos outro. Você deve ser capz de executar cada teste de forma independente e na ordem em que desejar
3) Repeatable: Deve-se poder repetir os teste sem qualquer ambiente
4) Sefl-validating: Devem ter um saída booleana. Obtendo ou não erro, vocẽ não deve ler um arquivo de registro ou comparar manualmente dois arquivos de texto apra saber qual o resultado.
5) Timely: Os testes precisam ser escritos em tempo hábil. Deve-se criar os testes de unidade imediatamente antes do de produção. Se criá-los depois, o teste do código de produção poderá ficar mais difícil ou talvez vocẽ não crie o código de produção da maneira que ele possa ser testado com facilidade.


# classes
## Organização das classes
* Uma classe deve começar com uma lista de variáveis, na ordem:
  * public
  * static
  * constant
  * private static
  * private
* As funções públicas devem vir após a lista de variáveis

## As classes devem ser pequenas
* Assim como nas funções, ser pequena é a regra principal ao criar classes
* O nome de uma classe deve descrever quais funcionalidades ela faz. Se não derivarmos um nome conciso para ela então provavelmente ela ficará grande com várias responsabilidades

## Princípio de responsabilidade única (SRP)
* Tente descrever brevemente em até 25 palavras o que a classe faz. Se houver algum "se", "e", "ou", "mas" na frase, provavelmente sua classe tem mais responsabilidades do que deveria

## Coesão
* A classe deve ter um pequeno número de variáveis de instância

# Sistemas
> Complexidade mata. Ela suga a vida dos desenvolvedores, dificulta o planejamento, a construção e os testes dos produtos - Ray Ozzie, CTO Microsoft

Os sistemas também devem ser limpos. Uma arquitetura invasiva afeta a agilidade e sobrepõe as lógicas do domínio porque os bugs se escondem mais facilmente e dificulta a implementação. Se a produtividade for comprometida, a produtividade também será

# Emergencia
## Regras para simplificar um projeto:
* Efetuar todos os testes
* Sem duplicação de código
* Expressar o propósito do programador
* Minimizar o número de classes e métodos

# Refinamento Sucessivo
* Para criar um código limpo, é preciso primeiro criar um sujo, e então, limpá-lo.
Assim como faziá-mos na escola antes de criar uma redação era necessário criar vários rascunhos e depois de muitos teríamos uma boa redação, com código funciona da mesma forma. Vocẽ poderá criar um código ruim de primeira, mas precisa refatorar ele para ir melhorando
* Muitos dos bons projetos de software se resumem ao particionamento - criar locais apropriados para colocar diferentes tipos de códigos. Essa separação de preocupações torna o código muito mais simples para se manter e compreender.

# Odores e heurísticas
## Lista de "odores"

### Comentários
* Informações inapropriadas
  * Não é apropriado para um comentário deter informações que ficariam melhores em outro tipo diferente de sistema como github ou qualquer outro sistema que mantenha registros
* Comentário Obsoleto
  * Um comentário que ficou velho, irrelevante ou incorreto é obsoleto. Comentários ficam velhos muito rápido, logo é melhor não escrever um que e tornará obsoleto
  * Caso vocẽ encontre um, é melhor atualizá-lo ou se livrar dele o quanto antes
* Comentários redundantes
  * Um comentário é redundante se ele descreve algo que já descreve a si mesmo
    ex: ```i++ // incrementa "i"```
  * Os comentários devem informar o que o código não se descreve por si só, caso contrário são redundantes
* Comentário mal escrito
  * Um comentário que valha ser escrito deve ser bem escrito. Se for criar um, não tenha pressa e certifique-se de que seja o melhor comentário que vocẽ já escreveu. Não erre a gramática, não diga o óbvio, seja breve
* Código comentado
  * Quem sabe a época em que foi escrito? Quem sabe se é ou não significativo? Mesmo assim ninguém o exclui pos todos assumem que outra pessoa precisa dele ou tem planos para ele.
  * > Colocar os códigos como comentários é uma abominação
  * Quando vocẽ ver um código comentado: exclua!

### Ambiente
* "Build" requer mais de uma etapa
  * "Bildar" um projeto deve ser uma operação simples e única. Tudo deve ser disparado em apenas um comando
* Testes requerem mais de uma etapa
  * Vocẽ deve ser capaz de rodar todos os testes de unidade com apenas um comando. No melhor dos casos vocẽ pode executar os teste ao clicar em um botão em sua IDE. No pior dos casos deve ser capaz de dar um único comando simples no prompt
* Parâmetros em excesso
  * As funções devem ter um número pequeno de parâmetros.
    * Nenhum (o ideal)
    * Um
    * Dois
    * Trẽs
    * Mais que trẽs deve-se evitar ou substituir por um objeto
* Parâmetros de saída
  * Evite-os
* Parâmetros lógicos
  * Parâmetros booleanos explicitamente declaram que a função faz mais de uma coisa. Evite.
* Função morta
  * Devem-se descartar os métodos que nunca são chamados. Não tenha medo de excluir uma função não mais utilizada, lembre-se de que seu controle de versão manterá ela no histórico

### Geral
* Comportamento óbvio não é implementado
  * Seguindo o "Princípio da Menor Surpresa" qualquer função ou classe deve implementar os comportamentos que outro programador possivelmente esperaria.
  * Quando um comportamento não é implementado, os leitores do código não podem mais depender de suas intuições sobre o que indica o nome da função.
* Comportamento incorreto nos limites
  * Nao dependa de sua intuição, cuide de cada condição e crie testes para cobrir cada cenário
* Seguranças anuladas
  * Nunca anule a segurança. Ex: desabilitar os testes de falha é tão ruium quanto achar que seu cartão de crédito é dinheiro grátis
* Duplicação
  * Essa é uma das regras mais importantes.
  * Sempre que vocẽ vir uma duplicação no código, significa que vocẽ perdeu uma chance para abstração. Aquela duplicação poderia se tornar uma sub-rotina ou talvez uma outra classe completa.
* Códigos no nível errado de abstração
  * É importante criar abstrações que separem conceitos gerais de níveis mais altos dos conceitos detalhados de níveis mais baixos
  * Por exemplo: constantes, variáveis ou funções que possuem apenas a implementação detalhada não devem ficar na classe base. Essa não deve saber nada sobre o resto
* As classes base dependem de suas derivadas
  * As classes bases não devem enxergar nada em suas derivadas, não devem depender delas
* Informações excessivas
  * Módulos bem definidos possuem interfaces pequenas que permitem fazer muito com pouco. Já os mal definidos possuem interfaces grandes e longas que lhe obriga a usar muitas formas diferentes para efetuar coisas simples.
  * Uma interface bem definida não depende de muitas funções, portanto há baixo acoplamento
  * Já uma interface mal definida depende de diversas funções que devem ser chamadas, gerando um algo acoplamento
  * Quanto menos métodos tiver uma classe, melhor. Quanto menos variáveis uma função usar, melhor. Quanto menos variáveis tiver uma classe melhor.
* Código morto
  * Um código morto é aquele não executado. Exclua-o
* Separação vertical
  * Deve-se declarar as variáveis e funções próximas de onde são usadas
  * Devem-se declarar as variáveis locais imediatamente acima de seu primeiro uso, e o escopo deve ser vertical. Não queremos que variáveis locais sejam declaradas centenas de linhas afastadas de onde são utilizadas
  * Devem-se declarar as funções privadas imediatamente abaixo de seu primeiro uso. Elas pertencem ao escopo de toda a classe, mesmo assim, aidna desejamos limitar a distãncia vertical entre as chamadas e as declarações. Encontrar uma função privada deve ser uma questão de buscar para baixo a partir de seu primeiro uso
* Inconsistẽncia
  * Se vocẽ fizer algo de uma determinada maneira, faça da mesma forma todas as outras coisas similares.
  * Tenha atenção ao escolher suas convenções, mua vez escolhidas atente-se para continuar seguindo-as
* Entulho
  * De que serve um construtor sem implementação alguma? Só serve para entulhar o código com pedaços inúteis
  * Variáveis que não são usadas, funções que jamais são chamadas, comentários que não acrescentam informações e assim por diante, são todos entulhos e devem ser removidos.
* Acoplamento artificial
  * Coisas que não dependem uma da outra não devem ser acopladas artificialmente.
  * Tome um tempo para descobrir onde devem ser declaradas as funções, as constantes e as variáveis. Não as jogue no local mais conveniente e  fácil.
* Feature Envy
  * Os métodos de uma classe devem ficar interessados nas variáveis e funções da classe a qual eles pertencem, e não nas de outras classes.
  * Quando um método usa métodos de acesso e de alteração de algum outro objeto para manipular os dados dentro deste objeto, o método inveja o escopo da classe daquele outro objeto. Ele queria estar dentro daquela outra classe de modo que pudesse ter acesso direto às variáveis que está manipulando
* Propósito Obscuro
  * Queremos que o código seja o mais expressivo possível.
* Responsabilidade mal posicionada
  * Onde colocar o código é uma das decisões mais importantes que um desenvolvedor de software deve fazer
  * Às vezes damos uma de espertinhos na hora de posicionar certa funcionalidade. Colocando-a em uma coluna função que é conveniente para nós, mas não necessariamente intuitiva para o leitor.
* Use variáveis descritivas
  * Uma das formas mais poderosas de tornar um programa legível é separar os cálculos em valores intermediários armazenados em variáveis com nomes descritivos
* Nomes de funções devem dizer o que elas fazem
  * Se você tiver de olhar a implementação (ou a documentação) da função para saber o que ela faz, então é melhor selecionar um nome melhor ou reorganizar a funcionalidade de modo que esta possa ser colocada em funções com nomes melhores
* Entenda o Algoritimo
  * Antes de achar que já terminou com uma função, certifique-e de que vocẽ entenda como ela funciona. Ter passado em todos os testes não basta. Vocẽ deve compreender que a solução está correta.
  * Geralmente a melhor form a de obter esse conhecimento e entendimento é refatorar a função em algo que seja tão limpo e expressivo que fique óbvio que ela funciona
* Torne dependências lógicas em físicas
  * Se um módulo depende deoutro, essa dependẽncia deve ser física, e não apenas lógica. O módulo dependente não deve fazer suposições (dependências lógicas) sobre o módulo no qual ele depende. Em vez disso, ele deve pedir explicitamente áquele módulo todas as informações das quais ele depende
* Prefira polimorfismo a if/else ou switch/case
  * Pode existir mais de uma estrutura switch para um dado tipo de seleção. Os casos nos quais o switch deva criar objetos polifórmicos que substituam outras estruturas switch no resto do sistema.
* Siga as convenções padrões
  * Cada equipe deve seguir um padrão de programação baseando-se nas normas comuns do mercado.
  * A equipe não deve precisar de um documento que descreva essas convenções porque seus códigos fornecem os exemplos
* Substitua os números mágicos por constantes com nomes
  * De modo geral é uma péssima ideia ter números soltos em seu código. Deve-se scondẽ-los em constantes com nomes bem selecionados.
* Seja preciso
  * Quando vocẽ tomar uma decisão no seu código, certifique-se de fazê-la precisamente. Saiba por que a tomou e como lidará com quaisquer exceções. Não seja desleixado com a precisão de suas decisões.
  * Se decidir chamar uma função que retorne "null", certifique-se de verificar por "null"
* Estrutura acima de convenção
  * Insista para que as decisões do projeto baseem-se em estrutura acima de convenção
* Encapsule as condicionais
  * A lógica booleana já é difícil o bastante de entender sem precisar vẽ-la no contexto de um if ou shile. Extraia funções que expliquem o propósito da estrutura condicional
  * ```if(shouldBeDeleted(timer))``` é melhor que ```if(timer = 20 && day === 10)```
* Evite condicionais negativas
  * É um pouco mais difícil entender condições negativas do que afirmativas. Portanto, sempre que possível use condicionais afirmativas.
* As funções devem fazer uma coisa só
  * Funções que fazem mais de uma coisa devem ser divididas em várias funções que fazem uma coisa cada
* Acoplamentos temporais ocultos
  * Acoplamentos temporais costumam ser necessários, mas vocẽ não deve ocultar o acoplamento.
  * Organize os parametros de suas funções de modo que a ordem na qual são chamados fique óbvia.
* Não seja arbitrário
  * Tenha um motivo pelo qual vocẽ estruture seu código e certifique-se de que tal motivo seja informado na estrutura. Se esta parece arbitrária, as outras pessoas se sentirão no direito de alterá-la. Mas se uma estrutura parece consistente por todo o sistema, as outras pessoas irão usá-la e preservar a convenção utilizada.
* Encapsule as condições de limites ("s+1")
  * Condições de limite são difíceis de acompanhar. Coloque o processamento para elas em um único lugar. Não as deixe espalhadas pelo código.
* Funções devem descer apenas um nível de abstração
  * As instruções dentro de uma função devem ficar todas no mesmo nível de abstração, o qual deve ser um nível abaixo da operação descrita pelo nome da função.
* Mantenha os dados configuráveis em níveis altos
  * Se vocẽ tiver uma constante, como um valor padrão ou de configuração, que seja conhecida e esperada em um nível alto de abstração, não a coloque numa função de nível baixo.
  * Exponha a constante como parãmetro para tal função, que será chamada por outra de nível mais alto.
* Evite a navegação transitiva
  * De modo geral, não queremos que um único módulo saiba muito sobre seu colaboradores. Mais especificamente, se A colabora com B e B colabora com C, não queremos que os módulos que usem A enxerguem C (lei de Demeter)
  * Resume-se a se garantir que os módulos saibam sobre seus colaboradores imediatos apenas e não sobre o mapa de navegação de todo o sistema
  * Se muitos módulos usam algum tipo de instrução "a.getB().getC()" então seria difícil alterar o projeto e a arquitetura para introduzir um Q entre B e C.

### Java
* Não herde as constantes
  * Um programador coloca algumas constantes em uma interface e ganha acesso a elas herdando daquela interface. Essa é uma prática horrível! As constantes ficam escondidas no topo da hierarquia de herança. Não use a herança como um meio de burlar as regras de escopo da linguagem

### Nomes
* Escolha nomes descritivos
  * Não se apresse ao escolher um nome. Certifique-se de que ele seja descritivo.
  * Nomes em softawres são 90% responsáveis pela legibilidade do software.
  * O poder de nomes cuidadosamente selecionados é que eles preenchem a estrutura do código com descrições. Esse preenchimento faz com que os leitoress saibam o que esperar das outras funções no módulo
* Escolha nomes no nível apropriado de abstração
  * Não escolha nomes que indiquem a implementação, mas nomes que reflitam o nível de abstração da classe ou função na qual vocẽ está trabalhando.
* Use uma nomenclatura padrão onde for possível
  * Nomes são mais fáceis de entender se baseados em uma convenção ou uso já existente.
  * Utilize a linguagem ubíqua
* Nomes não ambíguos
  * Escolha nomes que não deixem as tarefas de uma função ou variável ambíguas.
* Use nomes longos para escopos grandes
  * O comprimento de um nome deve estar relacionado com o escopo. Você pode usar nomes de variáveis muito curtos para escopos minúsculos. Mas para escopos grandes deve-se usar nomes extensos
  * Nomes de variáveis "i" num loop são bons pois o escopo geralmente é pequeno
* Evite codificações
  * Não se deve codificar nomes com informações sobre o tipo ou o escopo
* Nomes devem descrever os efeitos colaterais
  * Nomes devem descrever tudo o que uma função, variável ou classe, é ou faz. Não oculte os efeitos colaterais com um nome.
  * Não use um simples verbo para descrever uma função que faça mais de umba ação

### Testes
* Testes insuficientes
  * Uma coleção de testes deve testar tudo o que pode vir a falhar.
  * Os testes são insificientes enquanto houver condições que não tenham sido exploradas pelos testes ou cálculos que não tenha sido validados.
* Use uma ferramenta de cobertura
  * Ferramentas de cobertura informam lacunas em sua estratégia de testes. Elas facilitam o encontro de módulos, classes e funções que são testado de modo insuficiente
* Não pule testes triviais
  * Eles são fáceis de escrever e seu valor de documentação é maior do que o custo de produzí-los
* Teste as condições de limites
  * Dẽ atenção especial aos testes de condições de limites. Geralmente, entendemos a parte central de um algoritmo, mas erramos sobre seus limites
* Teste abundantemente bugs próximos
  * Bugs tendem a se reunir. Quando encontrar um bug numa função, é sábio fazer um teste exaustivo nela. Provavelmente vocẽ verá que o bug não está só
* Padõres de falhas são reveladores
  * De vez em quando, você pode diagnosticar um problema ao encontrar padrões na forma pela qual os casosde teste falharam. Esse é outro argumento para tornar os casos de teste os mais completos possíveis. Eles, quando ordenados de uma maneira lógica, expõem os padrões.
* Padrões de cobertura de testes podem ser reveladores
  * Analisar o código que é ou não executado pelos testes efetuados dá dicas do porquẽ de os testes qu falharam estão falhando
* Testes devem ser rápidos
  * Um teste lento é um que não será rodado. Quando as coisas ficam apertadas, são os testes lentos que serão descartados da coleção, portanto, faça o que puder para manter seus testes rápidos.

## Epílogo
Em 2005, durante a conferência sobre o Agile, Elisabeth Hedrickson me deu uma fitinha verde de punho. Nela estava escrito "Obcecado por testes" Com satisfação, amarrei-a em meu punho e a usei com orgulho. Desde que Kent Beck me ensinou, em 1999, sobre o TDD, fiquei, de fato, obcecado pelo desenvolvimento dirigido a testes.
Porém, algo estranho aconteceu. Descobri que eu não poderia retirar minha fitinha do punho. Não por que ela estivesse presa a ele, mas por estar moralmente presa. A fita fazia uma afirmação evidente sobre minha ética profissional. Era uma indicação visual do meu comprometimento em criar o melhor código que eu pudesse. Tirá-la seria como trair talética e comprometimento.
