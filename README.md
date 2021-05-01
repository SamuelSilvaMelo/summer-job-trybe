# CSS Flexbox
## O que vamos aprender?

Olá Tryber! Hoje vamos aprender um dos recursos mais sensacionais do CSS. O Flexbox!

Sabe aquela luta que todo desenvolvedor iniciante enfrenta para conseguir organizar o conteúdo corretamente dentro do seu site? Aquela tristeza em redimensionar a tela e quebrar totalmente o design da sua aplicação? Todos (ou quase :stuck_out_tongue_closed_eyes:) todos os seus problemas estarão solucionados ao final desse conteúdo.

O Flexbox (_Flexible Box Module_) é uma funcionalidade nativa presente no __CSS__ que permite estruturar o seu layout de maneira __responsiva e flexível__ sem a necessidade da utilização de elementos do tipo __block__, __inline__ ou __inline-block__. Você também não irá se preocupar mais com as aberrações que podem surgir ao se criar um elemento flutuante (_float_) ou então com a falta de flexibilidade ao se utilizar um posicionamento específico para uma parte do seu site (__static__, __relative__, __fixed__ ou __abolute__).

Com o uso do Flexbox você atribui aos elementos um comportamento dinâmico baseado em proporções, o que significa que os elementos podem "flexionar" seus tamanhos, tanto crescendo para preencher o espaço não utilizado ou encolhendo para evitar a quebra dos limites do elemento pai. Na prática você irá observar que trabalhar com Flexbox é como organizar uma grande fila, sendo que você como desenvolvedor irá definir a direção e prioridade do posicionamento dos itens dessa grande "fila" de elementos _HTML_.

Hoje serão apresentados as especificações Flexbox relativas ao elemento _container_ pai, que atribuem a ele um comportamento flexível: 

- ```display: flex;```;
- ```flex-direction```;
- ```flex-wrap```;
- ```flex-flow```;
- ```justify-content```;
- ```align-itens```;
- ```align-content```.

## Você será capaz de:

- Tornar qualquer elemento do seu _HTML_ flexível;
- Configurar o elemento _container_ pai como flexível;
- Utilizar corretamente os eixos do Flexbox;
- Alinhar os conteúdos verticalmente e horizontalmente;

## Por que isso é importante

Você irá perceber que o grande diferencial da utilização do Flexbox é a sua capacidade de inclusão devido à suas propriedades de dimensionamento dos elementos. Isso quer dizer que ao estilizar seu site utilizando propriedades flexíveis em seus elementos consequentemente você está permitindo que mais pessoas obtenham uma excelênte experiência ao utilizar suas criações. Dessa maneira usuários com monitores FullHD (1080p) e usuários com um monitor HD (720p) terão, por exemplo, a mesma experiência.

A melhor parte é que o CSS Flexbox permite que você, como desenvolvedor, crie um mundo mais responsivo e inclusivo com apenas algumas funcionalidades!

## Conteúdos

### Diferenciando um _flex-container_ de um _flex-items_

A diferença entre um _flex-container_ e um _flex-item_ é bem simples, porém a sua compreensão a respeito disso deverá ser clara, pois caso contrário no futuro você pode acabar aplicando uma propriedade de um _flex-item_ em um _flex-container_ e isso resultará em um resultado indesejado. Basicamente o _flex-container_ é o elemento __PAI__ enquanto os _flex-itens_ são os elementos __FILHOS__. Observe a imagem abaixo:

![](https://i.imgur.com/BukOhUw.png)

A diferença básica entre os dois é essa e hoje veremos as configurações que se aplicam ao _flex-container_.

### Tornando algum elemento _HTML_ flexível

Para tornar algum elemento _HTML_ flexível é necessário mudar sua propriedade __DISPLAY__ atribuindo a ela o valor __FLEX__.

```
.container {
  display: flex;
}
```

Esse valor de __DISPLAY__ permite um comportamento flexível para todos os seus filhos diretos.

### Propriedade ```flex-direction```

Essa configuração só é aplicável ao eixo principal (_main-axis_) e define a direção em que os _flex-itens_ são colocados dentro do _flex-container_. É importante entender que o Flexbox é (exceto algumas configuraçẽos especiais) um conceito de layout de direção única.

#### Sintaxe

```
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
Onde:

- ```row```: Essa propriedade é definida como padrão caso não seja alterada. A palavra __row__ significa __linha__ e define a posição dos elementos da esquerda para a direita, um ao lado do outro (como eu uma fila);
- ```row-reverse```: Define os _flex-itens- também em linha, porém o posicionamento será _'reverso'_, ou seja, da direita para a esquerda;
- ```column```: Define os _flex-itens_ em uma coluna única, um embaixo do outro, começando de cima para baixo;
- ```column-reverse```: Define os _flex-itens_ também em uma coluna única, porém começando de baixo para cima (como se _enter_ do teclado desse um pulo para cima).

Para facilitar o seu entendimento pense nos _flex-itens_ de um _flex-container_ principalmente em linhas horizontais ou colunas verticais. Clique [aqui]() para ver de maneira interativa como cada alteração dessa influencia o posicionamento dos _flex-itens_.

## Vamos fazer juntos!

Agora que você já conhece as especificações do módulo Flexbox e as propriedades que auxiliam na configuração de um _container_, vamos para a aula ao vivo.

O link estará disponível no Slack.

## Exercícios
## Recursos adicionais (opcional)

[No CSS Flexbox, por que não existem propriedades "justify-items" e "justify-self"?
](https://qastack.com.br/programming/32551291/in-css-flexbox-why-are-there-no-justify-items-and-justify-self-properties#:~:text=A%20especifica%C3%A7%C3%A3o%20flexbox%20permite%20o,removidos%20do%20fluxo%20de%20documentos%20.)
