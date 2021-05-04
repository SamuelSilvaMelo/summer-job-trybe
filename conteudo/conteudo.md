# CSS Flexbox
## O que vamos aprender?

Olá Tryber! Hoje vamos aprender um dos recursos mais sensacionais do CSS. O Flexbox!

Sabe aquela luta que todo desenvolvedor iniciante enfrenta para conseguir organizar o conteúdo corretamente dentro do seu site? Aquela tristeza em redimensionar a tela e quebrar totalmente o design da sua aplicação? Todos (ou quase :stuck_out_tongue_closed_eyes:) todos os seus problemas estarão solucionados ao final desse conteúdo.

O Flexbox (_Flexible Box Module_) é uma funcionalidade nativa presente no __CSS__ que permite estruturar o seu layout de maneira __responsiva e flexível__ sem a necessidade da utilização de elementos do tipo __block__, __inline__ ou __inline-block__. Você também não irá se preocupar mais com as aberrações que podem surgir ao se criar um elemento flutuante (_float_) ou então com a falta de flexibilidade ao se utilizar um posicionamento específico para uma parte do seu site (__static__, __relative__, __fixed__ ou __abolute__).

Com o uso do Flexbox você atribui aos elementos um comportamento dinâmico baseado em proporções, o que significa que os elementos podem "flexionar" seus tamanhos, tanto crescendo para preencher o espaço não utilizado ou encolhendo para evitar a quebra dos limites do elemento pai. Na prática você irá observar que trabalhar com Flexbox é como organizar uma grande fila, sendo que você como desenvolvedor irá definir a direção e prioridade do posicionamento dos itens dessa grande "fila" de elementos _HTML_.

Hoje serão apresentadas as especificações Flexbox relativas ao elemento _container_ pai, que atribuem a ele um comportamento flexível: 

- ```display: flex;```;
- ```flex-direction```;
- ```flex-wrap```;
- ```flex-flow```;
- ```justify-content```;
- ```align-itens```;
- ```align-content```.

## Você será capaz de:

- Tornar qualquer elemento do seu _HTML_ flexível;
- Utilizar corretamente os eixos do Flexbox;
- Aplicar as configurações corretas ao elemento _flex-container_;
- Alinhar os conteúdos verticalmente e horizontalmente;

## Por que isso é importante

Você irá perceber que o grande diferencial da utilização do Flexbox é a sua capacidade de inclusão devido à suas propriedades de dimensionamento dos elementos. Isso quer dizer que ao estilizar seu site utilizando propriedades flexíveis em seus elementos consequentemente você está permitindo que mais pessoas obtenham uma excelênte experiência ao utilizar suas criações. Dessa maneira usuários com monitores FullHD (1080p) e usuários com um monitor HD (720p) terão, por exemplo, a mesma experiência.

A melhor parte é que o CSS Flexbox permite que você, como desenvolvedor, crie um mundo mais responsivo e inclusivo com apenas algumas funcionalidades!

## Conteúdos

### Diferenciando um _flex-container_ de um _flex-item_

A diferença entre um _flex-container_ e um _flex-item_ é bem simples, porém a compreensão a respeito disso deverá ser nítida, pois caso contrário no futuro você pode acabar aplicando uma propriedade de um _flex-item_ em um _flex-container_ e isso resultará em um resultado indesejado. Basicamente o _flex-container_ é o elemento __PAI__ enquanto os _flex-itens_ são os elementos __FILHOS__. Observe a imagem abaixo:

![](https://i.imgur.com/BukOhUw.png)

A diferença básica entre os dois é essa e hoje veremos as configurações que se aplicam ao _flex-container_.

### Tornando algum elemento _HTML_ flexível

Para tornar algum elemento _HTML_ flexível é necessário mudar a propriedade __display__ atribuindo a ela o valor __flex__.

```
.container {
  display: flex;
}
```

Esse valor de __display__ permite um comportamento flexível para todos os seus filhos diretos.

### Conhecendo os eixos do _flex-container_

O _layout_ flexível apresentado pelo Flexbox tras consigo um novo conceito de "_flex-flow directions_"(direções flexíveis). Esse conceito aborda dois eixos básicos (_main axis_ e o _cross axis_) que possuem um ponto de início (_main-start_ / _cross-start_) e um ponto final (_main-end_ / _cross-end_).
Os _flex-itens_ serão dispostos seguindo o _main axis_ (do início ao fim, ou seja, do _main start_ até o _main end_) ou então o _cross axis_ (também do início ao fim, ou seja, do _cross-start_ até o _cross-end_).

O eixo principal (_main axis_) pode ser tanto horizontal (sua posição por padrão) ou então vertical e isso irá depender unicamente do valor definido pela propriedade ```flex-direction``` (você irá aprender a usar ela logo abaixo). Vamos observar agora alguns exemplos:

- Quando o eixo principal for horizontal os eixos se organizarão da seguinte maneira:

![](https://i.imgur.com/VAoNq13.png)

- Quando o eixo principal for verical os eixos se organizarão da seguinte maneira:

![](https://i.imgur.com/JgoWsmM.png)

Não se preocupe que mais abaixo você aprenderá a mudar a direção do eixo principal através da propriedade ```flex-direction```.

Importante observar que o eixo cruzado (_cross axis_) será sempre perpendicular ao eixo principal (_main axis_) e a sua direção sempre dependerá da direção do eixo principal.

### Propriedade ```flex-direction```

Essa configuração só é aplicável ao eixo principal (_main-axis_) e define a direção em que os _flex-itens_ são colocados dentro do _flex-container_. É importante entender que o Flexbox é (exceto algumas configurações especiais) um conceito de layout de direção única.

#### Sintaxe

```
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
Onde:

- ```row```: essa propriedade é definida como padrão caso não seja alterada. A palavra __row__ significa __linha__ e define a posição dos elementos da esquerda para a direita, um ao lado do outro (como eu uma fila);
- ```row-reverse```: define os _flex-itens_ também em linha, porém o posicionamento será _'reverso'_, ou seja, da direita para a esquerda;
- ```column```: define os _flex-itens_ em uma coluna única, um embaixo do outro, começando de cima para baixo;
- ```column-reverse```: define os _flex-itens_ também em uma coluna única, porém começando de baixo para cima (como se _enter_ do teclado desse um pulo para cima).

Para facilitar o seu entendimento pense nos _flex-itens_ de um _flex-container_ principalmente em linhas horizontais ou colunas verticais. Clique [aqui](https://samuelsilvamelo.github.io/summer-job/flex-direction/) para ver de maneira interativa como cada alteração dessa influencia o posicionamento dos _flex-itens_.

### Propriedade ```flex-wrap```

Sempre que você definir um _flex-container_ com ```display: flex;``` por pardão os _flex-itens_ tentarão todos se ajuntar em uma única linha, mesmo que seja necessário "espremer" os itens. Esse comportamento pode ser alterado (sem a utilização de nenhum tipo de magia, apenas com tecnologia :zany_face: :joy:) fazendo com que ao chegar ao final da linha o próximo _flex-item_ desça automaticamente para a linha de baixo!

#### Sintaxe

```
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```
Onde:

- ```nowrap```: essa propriedade é definida como padrão caso não seja alterada: Define todos os _flex-itens_ em uma única linha (não ocorre a "quebra" de linha);
- ```wrap```: define os _flex-itens_ para sofrerem uma quebra de linha, de cima para baixo, de acordo com a necessidade do tamanho de cada item;
- ```wrap-reverse```: se comporta de maneira similar ao ```wrap```, porém os itens serão posicionados na ordem "reversa", ou seja, de baixo para cima.

Clique [aqui](https://samuelsilvamelo.github.io/summer-job/flex-wrap/) para ver de maneira interativa como os _flex-itens_ se comportam quando alteramos os valores do ```flex-wrap```.

### Propriedade ```flex-flow```

É uma abreviação, um atalho para as propriedades ```flex-direction``` e ```flex-wrap```, respectivamente, que juntas definem os eixos principal e cruzados do _flex-container_. O valor parão caso não seja alterado é ```row nowrap```. Importante reforçar que o ```flex-flow``` recebe duas propriedades, respeitando essa ordem: ```flex-direction``` e depois ```flex-wrap```. Sempre que possível utilize a forma abreviada para deixar seu código mais limpo e de fácil leitura.

#### Sintaxe

```
.container {
  flex-flow: column wrap;
}

/* Nesse caso a propriedade flex-direction ficou selecionada como column e a 
propriedade flex-wrap como wrap */
```

### Propriedade ```justify-content```

Essa propriedade define o alinhamento ao longo do eixo principal (_main-axis_). Com ela fica mais fácil distribuir o espaço restante entre os _flex-itens_.

#### Sintaxe

```
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```
Onde:

- ```flex-start```: é a propriedade padrão, onde os _flex-itens_ são agrupados (alinhados) no __início__ do _flex-direction_ (a referência aqui é o início do _flex-direction_ pois a propriedade ```justify-content: flex-start;``` pode alinhar os _flex-itens_ tando à direita quanto à esquerda dependendo da direção do ```flex-direction```);
- ```flex-end```: agrupa (alinha) os _flex-itens_ no __final__ do _flex-direction_;
- ```center```: os _flex-itens_ são centralizados ao longo da linha;
- ```space-between```: os espaços entre os _flex-itens_ são distribuídos igualmente, porém o primeiro item fica colado no início da linha e o último item fica colado no final da linha;
- ```space-around```: o primeiro _flex-item_ recebe o mesmo espaçamento da borda que o último _flex-item_, porém os espaçamentos __entre__ os _flex-itens_ vão possuir duas vezes o valor que o primeiro e o último _flex-itens_ possuem da borda;
- ```space-evenly```: os _flex-itens_ são distribuídos de forma que o espaçamento seja igual entre todos os itens e entre os itens e as bordas.

Clique [aqui](https://samuelsilvamelo.github.io/summer-job/justify-content/) para ver de maneira interativa como os _flex-itens_ se comportam quando alteramos os valores do ```justify-content```.

### Propriedade ```align-items```

Essa propriedade define o comportamento padrão de como os _flex-itens_ são dispostos ao longo do __cross-axis__ na linha atual. Para ficar mais fácil a sua compreensão pense no ```align-items``` como um ```justify-content``` em sua versão para o _cross-axis_ (eixo transversal, perpendicular ao eixo principal).

#### Sintaxe

```
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```
Onde:

- ```stretch```: é a propriedade padrão caso não seja alterada. Define que os _flex-itens_ devem esticar e preencher 100% do espaço disponível no _flex-container_ (mas ainda assim essa "esticada" vai respeitar a altura máxima/mínima estipulada para o _flex-container_);
- ```flex-start```: os _flex-itens_ são colocados no topo do eixo transversal;
- ```flex-end```: os _flex-itens_ são colocados na base do eixo transversal;
- ```center```: os _flex-itens_ são centralizados no _cross-axis_;
- ```baseline```: os _flex-itens_ são alinhados tomando como referência a linha base de seus conteúdos.

Clique [aqui](https://samuelsilvamelo.github.io/summer-job/align-items/) para ver de maneira interativa como os _flex-itens_ se comportam quando alteramos os valores do ```align-items```.

### Propriedade ```align-content```

Essa propriedade ajuda a alinhar as __linhas__ de um _flex-container_ quando há espaço extra no _cross-axis_, funcionando de maneira similar ao ```justify-content``` que alinha cada _flex-item_ no _main-axis_, porém o ```align-content``` alinha cada __linha__ no _cross-axis_.
__Observação__: Esta propriedade só tem efeitos em _flex-containers_ multilinhas, onde o ```flex-flow``` é definido como ```wrap``` ou ```wrap-reverse```. Um _flex-container_ de linha única ou que possua o ```flex-flow``` definido como ```nowrap``` não irá refletir nenhuma mudança com o ```align-content```.

#### Sintaxe

```
.container {
  align-content: normal | flex-start | flex-end | center | space-between | space-around | space-evenly | stretch;
}
```
Onde:

- ```normal```: propriedade definida como padrão caso não seja alterado. Os _flex-itens_ são agrupados (alinhados) em sua posição padrão, como se nenhum valor tivesse sido definido;
- ```flex-start```: os _flex-itens_ são agrupados (alinhados) no início do _flex-container_;
- ```flex-end```: os _flex-itens_ são agrupados (alinhados) no final do _flex-container_;
- ```center```: os _flex-itens_ são centralizados no _flex-container_;
- ```space-between```: os espaços entre os _flex-itens_ são distribuidos uniformemente, sendo que a primeira linha fica colada no início do _flex-container_ e a última linha fica colada no final do _flex-container_;
- ```space-around```: a primeira e última linha recebem o mesmo espaçamento do topo e fundo do _flex-container_, porém o espaçamento __entre as linhas__ possui duas vezes o tamanho que a primeira e última linha possuem do topo e fundo do _flex-container_, respectivamente.
- ```space-evenly```: os _flex-itens_ se distribuem uniformemente, de maneira que o espaço entre as linhas seja igual entre todos eles (também é igual com relação às bordas superiores e inferiores);
- ```stretch```: os _flex-itens_ expandem as linhas para ocuparem o espaço disponível.

Clique [aqui](https://samuelsilvamelo.github.io/summer-job/align-content/) para ver de maneira interativa como os _flex-itens_ se comportam quando alteramos os valores do ```align-content```.

## Vamos fazer juntos!

Agora que você já conhece as especificações do módulo Flexbox e as propriedades que auxiliam na configuração de um _container_, vamos para a aula ao vivo.

O link estará disponível no Slack.

## Exercícios

### Parte - I

Após conhecer as funções do Flexbox que nos permitem organizar de maneira dinâmica os _flex-itens_ através das configurações aplicadas no _flex-container_ vamos praticar com uma sequência simples de exercícios. A estrutura _HTML_ será a mesma para todas as questões, você só precisará alterar o conteúdo do seu arquivo _CSS_ conforme for avançando.

#### Estrutura _HTML_:

```
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>Exercícios CSS Flexbox</title>
</head>
<body>
  <main>
    <div class="airplanes-div answers">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/vgq9WYwL0HqN-gGDR8zwhggyAOXvy_oTJIOKAjMuTZxNrVIuQSi2nySrZE_lLAP7Q63TcRXBe0UmXFPsSHlhDA4j-LKwZggv-ZrbJ8Z2Gp36GxQoeG_0FN62TWFgKbnhofEjvL5p3tXf-77l5TarxX7kzL0RN4uLpnaCFEGgYIJ0fKUkm-3Mi-W_WOgh_UhtfTDFPTggQQ2YNqMYqDhQnyRJUHvxAutvuODMwVrIf7maTiIawnlLwy15ih5x5zpY8GuwXy-6JAotH7Scsm5BaUmv6fn4VLWnRlWciJIbxZTCNzXIN9-aPNZfpaYjrlhtkJkioMazRbfab7XgE4Hul0zDEcDigDZ31x1yntOykyZxjyknYNB013zWqQac8nrDPPvJuV4Q26GlcNA_qiWK5FtwN3yb9baE5iEOf4b3Do132InMG2dBrnNGPY0GcCphTPP2sfogc4U7kbK-xULMenVfspJOR4gP6V8-6B_Z6mfFrx0fJ8tIWAHoZ-bCXyp8d-eq948mh6WdMfWXaR1Ve0atPxRnaPQq3Cq9_8ZwqsdmSOBlTgE2x49wjp0pNmUlZMcE2TSez3lNipPs_B8TUdhe5HCNyuTGzF3H21lC0Uog9MNeax6090d4bcahoRri236ORB2I-W5RNnqWVRLd80VsSyvHO2Idljc_vbAu6DyeH1ZSc3Vg6T1ump0NyZno6Irs-DeY4kJlYkupE23_N84=s646-no?authuser=0" alt="orange-airplane">
      <img src="https://lh3.googleusercontent.com/1FUW5Xfjtb_FXEk4xJ7Z5lEMemp5jn0ec7tMaElJni0Q8ly6yTUQALCCBlf4Nh7VOn5P6b7WDSlrPBEnWRKgjLGlYJwR7XoOA1780n-87YLXCNFaLjrj2iy9844EFRC2Bms4qc_CUiuDX7mDxO3YSqLiqaAxgw9sBmm3GwSk8EG85_87FkHtk-prEAdS87ZXBg2DSeaYxU4So-Ozl7gCURMsDgFBmg8X1dJMqW3zNyWn0WcQ-fzzj8KUT3I8oj87_MOrt837bqQpgYOF-CfMq2nDjEF2-EDqdnDqaChCGwhE8NPUSJUauQiCVGoynQz7U_634C_mNdAuK0JOgUYzrh9PAxDkeFQ3nh5yr6LonlRWpXoOOcCkmOnOzXr27BXgdOmtFyNYqpjwqm-twcsPUt3_GCZfB56zaiUZu48oY-L0M_Mk_Y78U4n2DltEvXeSvWc8vIpVRY4mG2ovtwu-_kjeA0QFnLfYuFW63hHWwFSzJkhK3K9frokSM7u_PmVUZIkSA9L_m1Zkmu5tc0Xc23OsgKwWQja-H0wiwiJSejLs1EMNeiRyERPOoe6nD4vOk7D51CJ72mKGRl0jjwfdDq8ZOiwX4tWcJbPjul-oSraEqF74rrVM62o9eOrmp9_UYb4LO9VPFGSzv8yJeFWjGLF_aqT63RnIFAjIrA3evEAYwRzDIy0KvHmHJazVTDbCmO4v2FK4Q5Pa5PluYjmhtc8=s646-no?authuser=0" alt="red-airplane">
    </div>
    <div class="runway-div">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/97JVZ7aceza_nzrBo8bOCccOlAbK9-YN2_z9Ei5H4hjAqEBiURCBggwnB7_R318zXUkPuVLkgZnFul88KlAQlubF7zqVfiegE9T7JMjLfEtwippON8LoElRJIBvk6Y97tgwnvLJuSQZWi68TsluRc7KfhFeddxvJclacahdO3QZY7RnJftH3HKCrhYAea6jvKNSvkyjfWD8ELtWAq0hwKGfT4Y37tofh_981M8Ym84wSpmZJjINiuqfxnY7dxVctLra-l_zAdh9FpqcpotvSrAQD-qOoZLDQ3hOrxs-8DuhvUlSlhzbyPmsmkn1tD1ksnK0Oz2Udy5b_IbsSW83djNp3x5uh90BjxxkuAQf9HzylVeNemhPLVhSLQCOXg5qXooTPLQgpQm_Q7mGJpTzFHlnpuqZQr9zQloap8_93pF1yT9e1N549mWtwe3ZwNU0cCivj05Vy7um-dNHTH-cWgFi0c_OuOd-xMw2TqwDZsdkrMWj6uM3zeY1N0nbWc_2VhEiI1iSv0xRKXrd9ngu5SlZTQ5pTzwDadmbPGV26A-s1N-v9ddDpH3o5oYrCJG9kc3am8atUoFfQhMjcGuvL3iZpTGf1HedDI79D4G47180iN6Ox4TDRYK0_6n-rOoWBqa9BAH3RFxChfCSvGUprmXguXRdnC1IfjulBXsq7G412VhKLPp8pf4O73oL-cjD_FmIEYyg1rreA317HARJlpDo=w374-h646-no?authuser=0" alt="orange-runway">
      <img src="https://lh3.googleusercontent.com/shaML0wHWqjCTeEsueQIMDcHG8i_gsx88vjqfUo252r-PGsFNuSLGSci518biDcc35gFOXbVIJ6UsOzAtlP8zMXZJ5draXobJG1pGHAhljTT1KL4lJtegUMIdL8rYYQmz1jrflolHmUss8nhJbZJQT_ashek5Ouy4bX0laZRYauCT0MLTCMiVuYJoASoblp5niz2-_BOdB3nbkre1jB66dl44I1kAhBwKrdZdfBRM0Uu46BP1vhkFD4A48dfv6vTThRS0wsoUW2tz-4prIsmMN7J8psryl3KIqVFz48UK5BOiSse0Mn77OSzNzkML_kp7PzS3fQ0xd5lRGoQ0Z2PERMUhykYOIypB26HYZknmnB65iC-IxYoXeUzHioQz7nM8PBle2N8goTRbyYfDyzGp2GrQkPdO8OJHGYMY9j9RJWqiSpW9GLlPNZTSYuuy_GXJN3vIBb4iAs3k0-TDoXKA1RH5zH8LH9ctKghET7FAfEtNclM2DGdba9mskTZvAp3oyvd67ccIjlvz_TRyXClzoaJ25bwAi_I2WNTgqOoQw8f91-1320Gq3CfQH4osFgbBwtwrVKNoMdvQ_8ZqNDifnHp430PNdPNbbCxsCC6GsW0Yh0SIqY-hUsDnZf5uF2DEi8EvWgVmZxJ3woGBXB53fPvsR4R-l_LtApp9cOtPe_th9mBIeBe0lZDfarO7dUd3kltVm2npZAh02rk2E10Xpg=w374-h646-no?authuser=0" alt="red-runway">
    </div>
  </main>
</body>
</html>
```

O objetivo de todos os exercícios abaixo é colocar os aviões azul, laranja e vermelho em suas respectivas pistas (azul, laranja e vermelho). Para fazer isso você deve alterar somente as especificações _CSS_, não é necessário alterar o arquivo _HTML_. A alteração deverá ser feita na classe _CSS_  ```answers```. 

### Exercício 1.1:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 180px;
  width: 180px;
}

.runway-div {
  display: flex;
  justify-content: flex-end;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 160px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 1.2:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 180px;
  width: 180px;
}

.runway-div {
  display: flex;
  flex-direction: row-reverse;
  justify-content: center;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 160px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 1.3:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 180px;
  width: 180px;
}

.runway-div {
  display: flex;
  flex-direction: column;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 160px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 1.4:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 180px;
  width: 180px;
}

.runway-div {
  display: flex;
  flex-direction: column-reverse;
  justify-content: space-between;
  align-items: center;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 160px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 1.5:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 180px;
  width: 180px;
}

.runway-div {
  display: flex;
  justify-content: space-around;
  align-items: flex-end;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 160px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 1.6:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 180px;
  width: 180px;
}

.runway-div {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 160px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Parte - II

Vamos explorar mais recursos do Flexbox! Mas agora você precisa pegar esse novo _HTML_ que será, novamente, o mesmo para todas as questões, você só precisará alterar o conteúdo do seu arquivo _CSS_ conforme for avançando.

#### Estrutura _HTML_:

```
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- <link rel="stylesheet" href="style1.css"> -->
  <!-- <link rel="stylesheet" href="style2.css"> -->
  <!-- <link rel="stylesheet" href="style3.css"> -->
  <!-- <link rel="stylesheet" href="style4.css"> -->
  <link rel="stylesheet" href="style5.css">
  <title>Exercícios CSS Flexbox - II</title>
</head>
<body>
  <main>
    <div class="airplanes-div answers">
      <img src="https://lh3.googleusercontent.com/vgq9WYwL0HqN-gGDR8zwhggyAOXvy_oTJIOKAjMuTZxNrVIuQSi2nySrZE_lLAP7Q63TcRXBe0UmXFPsSHlhDA4j-LKwZggv-ZrbJ8Z2Gp36GxQoeG_0FN62TWFgKbnhofEjvL5p3tXf-77l5TarxX7kzL0RN4uLpnaCFEGgYIJ0fKUkm-3Mi-W_WOgh_UhtfTDFPTggQQ2YNqMYqDhQnyRJUHvxAutvuODMwVrIf7maTiIawnlLwy15ih5x5zpY8GuwXy-6JAotH7Scsm5BaUmv6fn4VLWnRlWciJIbxZTCNzXIN9-aPNZfpaYjrlhtkJkioMazRbfab7XgE4Hul0zDEcDigDZ31x1yntOykyZxjyknYNB013zWqQac8nrDPPvJuV4Q26GlcNA_qiWK5FtwN3yb9baE5iEOf4b3Do132InMG2dBrnNGPY0GcCphTPP2sfogc4U7kbK-xULMenVfspJOR4gP6V8-6B_Z6mfFrx0fJ8tIWAHoZ-bCXyp8d-eq948mh6WdMfWXaR1Ve0atPxRnaPQq3Cq9_8ZwqsdmSOBlTgE2x49wjp0pNmUlZMcE2TSez3lNipPs_B8TUdhe5HCNyuTGzF3H21lC0Uog9MNeax6090d4bcahoRri236ORB2I-W5RNnqWVRLd80VsSyvHO2Idljc_vbAu6DyeH1ZSc3Vg6T1ump0NyZno6Irs-DeY4kJlYkupE23_N84=s646-no?authuser=0" alt="orange-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/1FUW5Xfjtb_FXEk4xJ7Z5lEMemp5jn0ec7tMaElJni0Q8ly6yTUQALCCBlf4Nh7VOn5P6b7WDSlrPBEnWRKgjLGlYJwR7XoOA1780n-87YLXCNFaLjrj2iy9844EFRC2Bms4qc_CUiuDX7mDxO3YSqLiqaAxgw9sBmm3GwSk8EG85_87FkHtk-prEAdS87ZXBg2DSeaYxU4So-Ozl7gCURMsDgFBmg8X1dJMqW3zNyWn0WcQ-fzzj8KUT3I8oj87_MOrt837bqQpgYOF-CfMq2nDjEF2-EDqdnDqaChCGwhE8NPUSJUauQiCVGoynQz7U_634C_mNdAuK0JOgUYzrh9PAxDkeFQ3nh5yr6LonlRWpXoOOcCkmOnOzXr27BXgdOmtFyNYqpjwqm-twcsPUt3_GCZfB56zaiUZu48oY-L0M_Mk_Y78U4n2DltEvXeSvWc8vIpVRY4mG2ovtwu-_kjeA0QFnLfYuFW63hHWwFSzJkhK3K9frokSM7u_PmVUZIkSA9L_m1Zkmu5tc0Xc23OsgKwWQja-H0wiwiJSejLs1EMNeiRyERPOoe6nD4vOk7D51CJ72mKGRl0jjwfdDq8ZOiwX4tWcJbPjul-oSraEqF74rrVM62o9eOrmp9_UYb4LO9VPFGSzv8yJeFWjGLF_aqT63RnIFAjIrA3evEAYwRzDIy0KvHmHJazVTDbCmO4v2FK4Q5Pa5PluYjmhtc8=s646-no?authuser=0" alt="red-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/vgq9WYwL0HqN-gGDR8zwhggyAOXvy_oTJIOKAjMuTZxNrVIuQSi2nySrZE_lLAP7Q63TcRXBe0UmXFPsSHlhDA4j-LKwZggv-ZrbJ8Z2Gp36GxQoeG_0FN62TWFgKbnhofEjvL5p3tXf-77l5TarxX7kzL0RN4uLpnaCFEGgYIJ0fKUkm-3Mi-W_WOgh_UhtfTDFPTggQQ2YNqMYqDhQnyRJUHvxAutvuODMwVrIf7maTiIawnlLwy15ih5x5zpY8GuwXy-6JAotH7Scsm5BaUmv6fn4VLWnRlWciJIbxZTCNzXIN9-aPNZfpaYjrlhtkJkioMazRbfab7XgE4Hul0zDEcDigDZ31x1yntOykyZxjyknYNB013zWqQac8nrDPPvJuV4Q26GlcNA_qiWK5FtwN3yb9baE5iEOf4b3Do132InMG2dBrnNGPY0GcCphTPP2sfogc4U7kbK-xULMenVfspJOR4gP6V8-6B_Z6mfFrx0fJ8tIWAHoZ-bCXyp8d-eq948mh6WdMfWXaR1Ve0atPxRnaPQq3Cq9_8ZwqsdmSOBlTgE2x49wjp0pNmUlZMcE2TSez3lNipPs_B8TUdhe5HCNyuTGzF3H21lC0Uog9MNeax6090d4bcahoRri236ORB2I-W5RNnqWVRLd80VsSyvHO2Idljc_vbAu6DyeH1ZSc3Vg6T1ump0NyZno6Irs-DeY4kJlYkupE23_N84=s646-no?authuser=0" alt="orange-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/1FUW5Xfjtb_FXEk4xJ7Z5lEMemp5jn0ec7tMaElJni0Q8ly6yTUQALCCBlf4Nh7VOn5P6b7WDSlrPBEnWRKgjLGlYJwR7XoOA1780n-87YLXCNFaLjrj2iy9844EFRC2Bms4qc_CUiuDX7mDxO3YSqLiqaAxgw9sBmm3GwSk8EG85_87FkHtk-prEAdS87ZXBg2DSeaYxU4So-Ozl7gCURMsDgFBmg8X1dJMqW3zNyWn0WcQ-fzzj8KUT3I8oj87_MOrt837bqQpgYOF-CfMq2nDjEF2-EDqdnDqaChCGwhE8NPUSJUauQiCVGoynQz7U_634C_mNdAuK0JOgUYzrh9PAxDkeFQ3nh5yr6LonlRWpXoOOcCkmOnOzXr27BXgdOmtFyNYqpjwqm-twcsPUt3_GCZfB56zaiUZu48oY-L0M_Mk_Y78U4n2DltEvXeSvWc8vIpVRY4mG2ovtwu-_kjeA0QFnLfYuFW63hHWwFSzJkhK3K9frokSM7u_PmVUZIkSA9L_m1Zkmu5tc0Xc23OsgKwWQja-H0wiwiJSejLs1EMNeiRyERPOoe6nD4vOk7D51CJ72mKGRl0jjwfdDq8ZOiwX4tWcJbPjul-oSraEqF74rrVM62o9eOrmp9_UYb4LO9VPFGSzv8yJeFWjGLF_aqT63RnIFAjIrA3evEAYwRzDIy0KvHmHJazVTDbCmO4v2FK4Q5Pa5PluYjmhtc8=s646-no?authuser=0" alt="red-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/vgq9WYwL0HqN-gGDR8zwhggyAOXvy_oTJIOKAjMuTZxNrVIuQSi2nySrZE_lLAP7Q63TcRXBe0UmXFPsSHlhDA4j-LKwZggv-ZrbJ8Z2Gp36GxQoeG_0FN62TWFgKbnhofEjvL5p3tXf-77l5TarxX7kzL0RN4uLpnaCFEGgYIJ0fKUkm-3Mi-W_WOgh_UhtfTDFPTggQQ2YNqMYqDhQnyRJUHvxAutvuODMwVrIf7maTiIawnlLwy15ih5x5zpY8GuwXy-6JAotH7Scsm5BaUmv6fn4VLWnRlWciJIbxZTCNzXIN9-aPNZfpaYjrlhtkJkioMazRbfab7XgE4Hul0zDEcDigDZ31x1yntOykyZxjyknYNB013zWqQac8nrDPPvJuV4Q26GlcNA_qiWK5FtwN3yb9baE5iEOf4b3Do132InMG2dBrnNGPY0GcCphTPP2sfogc4U7kbK-xULMenVfspJOR4gP6V8-6B_Z6mfFrx0fJ8tIWAHoZ-bCXyp8d-eq948mh6WdMfWXaR1Ve0atPxRnaPQq3Cq9_8ZwqsdmSOBlTgE2x49wjp0pNmUlZMcE2TSez3lNipPs_B8TUdhe5HCNyuTGzF3H21lC0Uog9MNeax6090d4bcahoRri236ORB2I-W5RNnqWVRLd80VsSyvHO2Idljc_vbAu6DyeH1ZSc3Vg6T1ump0NyZno6Irs-DeY4kJlYkupE23_N84=s646-no?authuser=0" alt="orange-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/1FUW5Xfjtb_FXEk4xJ7Z5lEMemp5jn0ec7tMaElJni0Q8ly6yTUQALCCBlf4Nh7VOn5P6b7WDSlrPBEnWRKgjLGlYJwR7XoOA1780n-87YLXCNFaLjrj2iy9844EFRC2Bms4qc_CUiuDX7mDxO3YSqLiqaAxgw9sBmm3GwSk8EG85_87FkHtk-prEAdS87ZXBg2DSeaYxU4So-Ozl7gCURMsDgFBmg8X1dJMqW3zNyWn0WcQ-fzzj8KUT3I8oj87_MOrt837bqQpgYOF-CfMq2nDjEF2-EDqdnDqaChCGwhE8NPUSJUauQiCVGoynQz7U_634C_mNdAuK0JOgUYzrh9PAxDkeFQ3nh5yr6LonlRWpXoOOcCkmOnOzXr27BXgdOmtFyNYqpjwqm-twcsPUt3_GCZfB56zaiUZu48oY-L0M_Mk_Y78U4n2DltEvXeSvWc8vIpVRY4mG2ovtwu-_kjeA0QFnLfYuFW63hHWwFSzJkhK3K9frokSM7u_PmVUZIkSA9L_m1Zkmu5tc0Xc23OsgKwWQja-H0wiwiJSejLs1EMNeiRyERPOoe6nD4vOk7D51CJ72mKGRl0jjwfdDq8ZOiwX4tWcJbPjul-oSraEqF74rrVM62o9eOrmp9_UYb4LO9VPFGSzv8yJeFWjGLF_aqT63RnIFAjIrA3evEAYwRzDIy0KvHmHJazVTDbCmO4v2FK4Q5Pa5PluYjmhtc8=s646-no?authuser=0" alt="red-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/vgq9WYwL0HqN-gGDR8zwhggyAOXvy_oTJIOKAjMuTZxNrVIuQSi2nySrZE_lLAP7Q63TcRXBe0UmXFPsSHlhDA4j-LKwZggv-ZrbJ8Z2Gp36GxQoeG_0FN62TWFgKbnhofEjvL5p3tXf-77l5TarxX7kzL0RN4uLpnaCFEGgYIJ0fKUkm-3Mi-W_WOgh_UhtfTDFPTggQQ2YNqMYqDhQnyRJUHvxAutvuODMwVrIf7maTiIawnlLwy15ih5x5zpY8GuwXy-6JAotH7Scsm5BaUmv6fn4VLWnRlWciJIbxZTCNzXIN9-aPNZfpaYjrlhtkJkioMazRbfab7XgE4Hul0zDEcDigDZ31x1yntOykyZxjyknYNB013zWqQac8nrDPPvJuV4Q26GlcNA_qiWK5FtwN3yb9baE5iEOf4b3Do132InMG2dBrnNGPY0GcCphTPP2sfogc4U7kbK-xULMenVfspJOR4gP6V8-6B_Z6mfFrx0fJ8tIWAHoZ-bCXyp8d-eq948mh6WdMfWXaR1Ve0atPxRnaPQq3Cq9_8ZwqsdmSOBlTgE2x49wjp0pNmUlZMcE2TSez3lNipPs_B8TUdhe5HCNyuTGzF3H21lC0Uog9MNeax6090d4bcahoRri236ORB2I-W5RNnqWVRLd80VsSyvHO2Idljc_vbAu6DyeH1ZSc3Vg6T1ump0NyZno6Irs-DeY4kJlYkupE23_N84=s646-no?authuser=0" alt="orange-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/1FUW5Xfjtb_FXEk4xJ7Z5lEMemp5jn0ec7tMaElJni0Q8ly6yTUQALCCBlf4Nh7VOn5P6b7WDSlrPBEnWRKgjLGlYJwR7XoOA1780n-87YLXCNFaLjrj2iy9844EFRC2Bms4qc_CUiuDX7mDxO3YSqLiqaAxgw9sBmm3GwSk8EG85_87FkHtk-prEAdS87ZXBg2DSeaYxU4So-Ozl7gCURMsDgFBmg8X1dJMqW3zNyWn0WcQ-fzzj8KUT3I8oj87_MOrt837bqQpgYOF-CfMq2nDjEF2-EDqdnDqaChCGwhE8NPUSJUauQiCVGoynQz7U_634C_mNdAuK0JOgUYzrh9PAxDkeFQ3nh5yr6LonlRWpXoOOcCkmOnOzXr27BXgdOmtFyNYqpjwqm-twcsPUt3_GCZfB56zaiUZu48oY-L0M_Mk_Y78U4n2DltEvXeSvWc8vIpVRY4mG2ovtwu-_kjeA0QFnLfYuFW63hHWwFSzJkhK3K9frokSM7u_PmVUZIkSA9L_m1Zkmu5tc0Xc23OsgKwWQja-H0wiwiJSejLs1EMNeiRyERPOoe6nD4vOk7D51CJ72mKGRl0jjwfdDq8ZOiwX4tWcJbPjul-oSraEqF74rrVM62o9eOrmp9_UYb4LO9VPFGSzv8yJeFWjGLF_aqT63RnIFAjIrA3evEAYwRzDIy0KvHmHJazVTDbCmO4v2FK4Q5Pa5PluYjmhtc8=s646-no?authuser=0" alt="red-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/1FUW5Xfjtb_FXEk4xJ7Z5lEMemp5jn0ec7tMaElJni0Q8ly6yTUQALCCBlf4Nh7VOn5P6b7WDSlrPBEnWRKgjLGlYJwR7XoOA1780n-87YLXCNFaLjrj2iy9844EFRC2Bms4qc_CUiuDX7mDxO3YSqLiqaAxgw9sBmm3GwSk8EG85_87FkHtk-prEAdS87ZXBg2DSeaYxU4So-Ozl7gCURMsDgFBmg8X1dJMqW3zNyWn0WcQ-fzzj8KUT3I8oj87_MOrt837bqQpgYOF-CfMq2nDjEF2-EDqdnDqaChCGwhE8NPUSJUauQiCVGoynQz7U_634C_mNdAuK0JOgUYzrh9PAxDkeFQ3nh5yr6LonlRWpXoOOcCkmOnOzXr27BXgdOmtFyNYqpjwqm-twcsPUt3_GCZfB56zaiUZu48oY-L0M_Mk_Y78U4n2DltEvXeSvWc8vIpVRY4mG2ovtwu-_kjeA0QFnLfYuFW63hHWwFSzJkhK3K9frokSM7u_PmVUZIkSA9L_m1Zkmu5tc0Xc23OsgKwWQja-H0wiwiJSejLs1EMNeiRyERPOoe6nD4vOk7D51CJ72mKGRl0jjwfdDq8ZOiwX4tWcJbPjul-oSraEqF74rrVM62o9eOrmp9_UYb4LO9VPFGSzv8yJeFWjGLF_aqT63RnIFAjIrA3evEAYwRzDIy0KvHmHJazVTDbCmO4v2FK4Q5Pa5PluYjmhtc8=s646-no?authuser=0" alt="red-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
      <img src="https://lh3.googleusercontent.com/vgq9WYwL0HqN-gGDR8zwhggyAOXvy_oTJIOKAjMuTZxNrVIuQSi2nySrZE_lLAP7Q63TcRXBe0UmXFPsSHlhDA4j-LKwZggv-ZrbJ8Z2Gp36GxQoeG_0FN62TWFgKbnhofEjvL5p3tXf-77l5TarxX7kzL0RN4uLpnaCFEGgYIJ0fKUkm-3Mi-W_WOgh_UhtfTDFPTggQQ2YNqMYqDhQnyRJUHvxAutvuODMwVrIf7maTiIawnlLwy15ih5x5zpY8GuwXy-6JAotH7Scsm5BaUmv6fn4VLWnRlWciJIbxZTCNzXIN9-aPNZfpaYjrlhtkJkioMazRbfab7XgE4Hul0zDEcDigDZ31x1yntOykyZxjyknYNB013zWqQac8nrDPPvJuV4Q26GlcNA_qiWK5FtwN3yb9baE5iEOf4b3Do132InMG2dBrnNGPY0GcCphTPP2sfogc4U7kbK-xULMenVfspJOR4gP6V8-6B_Z6mfFrx0fJ8tIWAHoZ-bCXyp8d-eq948mh6WdMfWXaR1Ve0atPxRnaPQq3Cq9_8ZwqsdmSOBlTgE2x49wjp0pNmUlZMcE2TSez3lNipPs_B8TUdhe5HCNyuTGzF3H21lC0Uog9MNeax6090d4bcahoRri236ORB2I-W5RNnqWVRLd80VsSyvHO2Idljc_vbAu6DyeH1ZSc3Vg6T1ump0NyZno6Irs-DeY4kJlYkupE23_N84=s646-no?authuser=0" alt="orange-airplane">
      <img src="https://lh3.googleusercontent.com/-T5NsZlC9q1LdyO75PMX1sgodzXf7x6wfuuuJLXaLRVDb61QAjsUZ8sQ6YaVu4JeCnnAN7rXN1jF87Kaqf1lFqIIuXLD1J52AWV85ulpHb4vGTpyNyvY2H_VKZSVEw1oo0wWE3sdc8qUZL14GwzFU-lmTG3p3MwpU3TFqbkIN75fFetYWrMyw8qqOK8UhsMhLezx8OK-ZcQ7QGkN5KRJo83I4HKwLNP8G9mTeiWhFnP9CPm4TeUHb54uRDw1kPVsfFOusd1Fh5hjSZf6Ohl35rpgtz7pDOOUg2r3tzYNmMB9uCf4hZQEUQRFYkLeJhMNi0rSdWauR2TSCPGTiMGuv_DD43T3MVc0X_bmgG3a19KOt3cQI9xJc9rHoyCdd9O_2yWx9ehUxZ-6NAHNsdjStMNP3JxDN-yczLaUDvGBuiEYxAk9JmZUX1VS3ANLiYkPqmuusB5NDC2b7wrx-LWWRi4nQxIclaoudciZxlWj25Knt-UqNx195AnZD9dLN86_JUhe1pDSccXutVLH893v6HOhZYMJagkYwsU0mtY9rHJZ3oVi4mOSYm_zu_BKkQuUZVf8i8i09kUjxnvKle5MOd_ZNsHShSLQRZSysTNL-C51Zr6-BPMX_NBfVec4fOjCn2PygE3WfHb36geqpUxznpwscQYiMa2jYfpTCck0TbdcmdgLB3aqXxFdGk7APvUyxzBCQJO8DLnnk-tjwVt-w9g=s646-no?authuser=0" alt="blue-airplane">
    </div>
    <div class="runway-div">
      <img src="https://lh3.googleusercontent.com/97JVZ7aceza_nzrBo8bOCccOlAbK9-YN2_z9Ei5H4hjAqEBiURCBggwnB7_R318zXUkPuVLkgZnFul88KlAQlubF7zqVfiegE9T7JMjLfEtwippON8LoElRJIBvk6Y97tgwnvLJuSQZWi68TsluRc7KfhFeddxvJclacahdO3QZY7RnJftH3HKCrhYAea6jvKNSvkyjfWD8ELtWAq0hwKGfT4Y37tofh_981M8Ym84wSpmZJjINiuqfxnY7dxVctLra-l_zAdh9FpqcpotvSrAQD-qOoZLDQ3hOrxs-8DuhvUlSlhzbyPmsmkn1tD1ksnK0Oz2Udy5b_IbsSW83djNp3x5uh90BjxxkuAQf9HzylVeNemhPLVhSLQCOXg5qXooTPLQgpQm_Q7mGJpTzFHlnpuqZQr9zQloap8_93pF1yT9e1N549mWtwe3ZwNU0cCivj05Vy7um-dNHTH-cWgFi0c_OuOd-xMw2TqwDZsdkrMWj6uM3zeY1N0nbWc_2VhEiI1iSv0xRKXrd9ngu5SlZTQ5pTzwDadmbPGV26A-s1N-v9ddDpH3o5oYrCJG9kc3am8atUoFfQhMjcGuvL3iZpTGf1HedDI79D4G47180iN6Ox4TDRYK0_6n-rOoWBqa9BAH3RFxChfCSvGUprmXguXRdnC1IfjulBXsq7G412VhKLPp8pf4O73oL-cjD_FmIEYyg1rreA317HARJlpDo=w374-h646-no?authuser=0" alt="orange-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/shaML0wHWqjCTeEsueQIMDcHG8i_gsx88vjqfUo252r-PGsFNuSLGSci518biDcc35gFOXbVIJ6UsOzAtlP8zMXZJ5draXobJG1pGHAhljTT1KL4lJtegUMIdL8rYYQmz1jrflolHmUss8nhJbZJQT_ashek5Ouy4bX0laZRYauCT0MLTCMiVuYJoASoblp5niz2-_BOdB3nbkre1jB66dl44I1kAhBwKrdZdfBRM0Uu46BP1vhkFD4A48dfv6vTThRS0wsoUW2tz-4prIsmMN7J8psryl3KIqVFz48UK5BOiSse0Mn77OSzNzkML_kp7PzS3fQ0xd5lRGoQ0Z2PERMUhykYOIypB26HYZknmnB65iC-IxYoXeUzHioQz7nM8PBle2N8goTRbyYfDyzGp2GrQkPdO8OJHGYMY9j9RJWqiSpW9GLlPNZTSYuuy_GXJN3vIBb4iAs3k0-TDoXKA1RH5zH8LH9ctKghET7FAfEtNclM2DGdba9mskTZvAp3oyvd67ccIjlvz_TRyXClzoaJ25bwAi_I2WNTgqOoQw8f91-1320Gq3CfQH4osFgbBwtwrVKNoMdvQ_8ZqNDifnHp430PNdPNbbCxsCC6GsW0Yh0SIqY-hUsDnZf5uF2DEi8EvWgVmZxJ3woGBXB53fPvsR4R-l_LtApp9cOtPe_th9mBIeBe0lZDfarO7dUd3kltVm2npZAh02rk2E10Xpg=w374-h646-no?authuser=0" alt="red-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/97JVZ7aceza_nzrBo8bOCccOlAbK9-YN2_z9Ei5H4hjAqEBiURCBggwnB7_R318zXUkPuVLkgZnFul88KlAQlubF7zqVfiegE9T7JMjLfEtwippON8LoElRJIBvk6Y97tgwnvLJuSQZWi68TsluRc7KfhFeddxvJclacahdO3QZY7RnJftH3HKCrhYAea6jvKNSvkyjfWD8ELtWAq0hwKGfT4Y37tofh_981M8Ym84wSpmZJjINiuqfxnY7dxVctLra-l_zAdh9FpqcpotvSrAQD-qOoZLDQ3hOrxs-8DuhvUlSlhzbyPmsmkn1tD1ksnK0Oz2Udy5b_IbsSW83djNp3x5uh90BjxxkuAQf9HzylVeNemhPLVhSLQCOXg5qXooTPLQgpQm_Q7mGJpTzFHlnpuqZQr9zQloap8_93pF1yT9e1N549mWtwe3ZwNU0cCivj05Vy7um-dNHTH-cWgFi0c_OuOd-xMw2TqwDZsdkrMWj6uM3zeY1N0nbWc_2VhEiI1iSv0xRKXrd9ngu5SlZTQ5pTzwDadmbPGV26A-s1N-v9ddDpH3o5oYrCJG9kc3am8atUoFfQhMjcGuvL3iZpTGf1HedDI79D4G47180iN6Ox4TDRYK0_6n-rOoWBqa9BAH3RFxChfCSvGUprmXguXRdnC1IfjulBXsq7G412VhKLPp8pf4O73oL-cjD_FmIEYyg1rreA317HARJlpDo=w374-h646-no?authuser=0" alt="orange-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/shaML0wHWqjCTeEsueQIMDcHG8i_gsx88vjqfUo252r-PGsFNuSLGSci518biDcc35gFOXbVIJ6UsOzAtlP8zMXZJ5draXobJG1pGHAhljTT1KL4lJtegUMIdL8rYYQmz1jrflolHmUss8nhJbZJQT_ashek5Ouy4bX0laZRYauCT0MLTCMiVuYJoASoblp5niz2-_BOdB3nbkre1jB66dl44I1kAhBwKrdZdfBRM0Uu46BP1vhkFD4A48dfv6vTThRS0wsoUW2tz-4prIsmMN7J8psryl3KIqVFz48UK5BOiSse0Mn77OSzNzkML_kp7PzS3fQ0xd5lRGoQ0Z2PERMUhykYOIypB26HYZknmnB65iC-IxYoXeUzHioQz7nM8PBle2N8goTRbyYfDyzGp2GrQkPdO8OJHGYMY9j9RJWqiSpW9GLlPNZTSYuuy_GXJN3vIBb4iAs3k0-TDoXKA1RH5zH8LH9ctKghET7FAfEtNclM2DGdba9mskTZvAp3oyvd67ccIjlvz_TRyXClzoaJ25bwAi_I2WNTgqOoQw8f91-1320Gq3CfQH4osFgbBwtwrVKNoMdvQ_8ZqNDifnHp430PNdPNbbCxsCC6GsW0Yh0SIqY-hUsDnZf5uF2DEi8EvWgVmZxJ3woGBXB53fPvsR4R-l_LtApp9cOtPe_th9mBIeBe0lZDfarO7dUd3kltVm2npZAh02rk2E10Xpg=w374-h646-no?authuser=0" alt="red-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/97JVZ7aceza_nzrBo8bOCccOlAbK9-YN2_z9Ei5H4hjAqEBiURCBggwnB7_R318zXUkPuVLkgZnFul88KlAQlubF7zqVfiegE9T7JMjLfEtwippON8LoElRJIBvk6Y97tgwnvLJuSQZWi68TsluRc7KfhFeddxvJclacahdO3QZY7RnJftH3HKCrhYAea6jvKNSvkyjfWD8ELtWAq0hwKGfT4Y37tofh_981M8Ym84wSpmZJjINiuqfxnY7dxVctLra-l_zAdh9FpqcpotvSrAQD-qOoZLDQ3hOrxs-8DuhvUlSlhzbyPmsmkn1tD1ksnK0Oz2Udy5b_IbsSW83djNp3x5uh90BjxxkuAQf9HzylVeNemhPLVhSLQCOXg5qXooTPLQgpQm_Q7mGJpTzFHlnpuqZQr9zQloap8_93pF1yT9e1N549mWtwe3ZwNU0cCivj05Vy7um-dNHTH-cWgFi0c_OuOd-xMw2TqwDZsdkrMWj6uM3zeY1N0nbWc_2VhEiI1iSv0xRKXrd9ngu5SlZTQ5pTzwDadmbPGV26A-s1N-v9ddDpH3o5oYrCJG9kc3am8atUoFfQhMjcGuvL3iZpTGf1HedDI79D4G47180iN6Ox4TDRYK0_6n-rOoWBqa9BAH3RFxChfCSvGUprmXguXRdnC1IfjulBXsq7G412VhKLPp8pf4O73oL-cjD_FmIEYyg1rreA317HARJlpDo=w374-h646-no?authuser=0" alt="orange-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/shaML0wHWqjCTeEsueQIMDcHG8i_gsx88vjqfUo252r-PGsFNuSLGSci518biDcc35gFOXbVIJ6UsOzAtlP8zMXZJ5draXobJG1pGHAhljTT1KL4lJtegUMIdL8rYYQmz1jrflolHmUss8nhJbZJQT_ashek5Ouy4bX0laZRYauCT0MLTCMiVuYJoASoblp5niz2-_BOdB3nbkre1jB66dl44I1kAhBwKrdZdfBRM0Uu46BP1vhkFD4A48dfv6vTThRS0wsoUW2tz-4prIsmMN7J8psryl3KIqVFz48UK5BOiSse0Mn77OSzNzkML_kp7PzS3fQ0xd5lRGoQ0Z2PERMUhykYOIypB26HYZknmnB65iC-IxYoXeUzHioQz7nM8PBle2N8goTRbyYfDyzGp2GrQkPdO8OJHGYMY9j9RJWqiSpW9GLlPNZTSYuuy_GXJN3vIBb4iAs3k0-TDoXKA1RH5zH8LH9ctKghET7FAfEtNclM2DGdba9mskTZvAp3oyvd67ccIjlvz_TRyXClzoaJ25bwAi_I2WNTgqOoQw8f91-1320Gq3CfQH4osFgbBwtwrVKNoMdvQ_8ZqNDifnHp430PNdPNbbCxsCC6GsW0Yh0SIqY-hUsDnZf5uF2DEi8EvWgVmZxJ3woGBXB53fPvsR4R-l_LtApp9cOtPe_th9mBIeBe0lZDfarO7dUd3kltVm2npZAh02rk2E10Xpg=w374-h646-no?authuser=0" alt="red-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/97JVZ7aceza_nzrBo8bOCccOlAbK9-YN2_z9Ei5H4hjAqEBiURCBggwnB7_R318zXUkPuVLkgZnFul88KlAQlubF7zqVfiegE9T7JMjLfEtwippON8LoElRJIBvk6Y97tgwnvLJuSQZWi68TsluRc7KfhFeddxvJclacahdO3QZY7RnJftH3HKCrhYAea6jvKNSvkyjfWD8ELtWAq0hwKGfT4Y37tofh_981M8Ym84wSpmZJjINiuqfxnY7dxVctLra-l_zAdh9FpqcpotvSrAQD-qOoZLDQ3hOrxs-8DuhvUlSlhzbyPmsmkn1tD1ksnK0Oz2Udy5b_IbsSW83djNp3x5uh90BjxxkuAQf9HzylVeNemhPLVhSLQCOXg5qXooTPLQgpQm_Q7mGJpTzFHlnpuqZQr9zQloap8_93pF1yT9e1N549mWtwe3ZwNU0cCivj05Vy7um-dNHTH-cWgFi0c_OuOd-xMw2TqwDZsdkrMWj6uM3zeY1N0nbWc_2VhEiI1iSv0xRKXrd9ngu5SlZTQ5pTzwDadmbPGV26A-s1N-v9ddDpH3o5oYrCJG9kc3am8atUoFfQhMjcGuvL3iZpTGf1HedDI79D4G47180iN6Ox4TDRYK0_6n-rOoWBqa9BAH3RFxChfCSvGUprmXguXRdnC1IfjulBXsq7G412VhKLPp8pf4O73oL-cjD_FmIEYyg1rreA317HARJlpDo=w374-h646-no?authuser=0" alt="orange-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/shaML0wHWqjCTeEsueQIMDcHG8i_gsx88vjqfUo252r-PGsFNuSLGSci518biDcc35gFOXbVIJ6UsOzAtlP8zMXZJ5draXobJG1pGHAhljTT1KL4lJtegUMIdL8rYYQmz1jrflolHmUss8nhJbZJQT_ashek5Ouy4bX0laZRYauCT0MLTCMiVuYJoASoblp5niz2-_BOdB3nbkre1jB66dl44I1kAhBwKrdZdfBRM0Uu46BP1vhkFD4A48dfv6vTThRS0wsoUW2tz-4prIsmMN7J8psryl3KIqVFz48UK5BOiSse0Mn77OSzNzkML_kp7PzS3fQ0xd5lRGoQ0Z2PERMUhykYOIypB26HYZknmnB65iC-IxYoXeUzHioQz7nM8PBle2N8goTRbyYfDyzGp2GrQkPdO8OJHGYMY9j9RJWqiSpW9GLlPNZTSYuuy_GXJN3vIBb4iAs3k0-TDoXKA1RH5zH8LH9ctKghET7FAfEtNclM2DGdba9mskTZvAp3oyvd67ccIjlvz_TRyXClzoaJ25bwAi_I2WNTgqOoQw8f91-1320Gq3CfQH4osFgbBwtwrVKNoMdvQ_8ZqNDifnHp430PNdPNbbCxsCC6GsW0Yh0SIqY-hUsDnZf5uF2DEi8EvWgVmZxJ3woGBXB53fPvsR4R-l_LtApp9cOtPe_th9mBIeBe0lZDfarO7dUd3kltVm2npZAh02rk2E10Xpg=w374-h646-no?authuser=0" alt="red-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/shaML0wHWqjCTeEsueQIMDcHG8i_gsx88vjqfUo252r-PGsFNuSLGSci518biDcc35gFOXbVIJ6UsOzAtlP8zMXZJ5draXobJG1pGHAhljTT1KL4lJtegUMIdL8rYYQmz1jrflolHmUss8nhJbZJQT_ashek5Ouy4bX0laZRYauCT0MLTCMiVuYJoASoblp5niz2-_BOdB3nbkre1jB66dl44I1kAhBwKrdZdfBRM0Uu46BP1vhkFD4A48dfv6vTThRS0wsoUW2tz-4prIsmMN7J8psryl3KIqVFz48UK5BOiSse0Mn77OSzNzkML_kp7PzS3fQ0xd5lRGoQ0Z2PERMUhykYOIypB26HYZknmnB65iC-IxYoXeUzHioQz7nM8PBle2N8goTRbyYfDyzGp2GrQkPdO8OJHGYMY9j9RJWqiSpW9GLlPNZTSYuuy_GXJN3vIBb4iAs3k0-TDoXKA1RH5zH8LH9ctKghET7FAfEtNclM2DGdba9mskTZvAp3oyvd67ccIjlvz_TRyXClzoaJ25bwAi_I2WNTgqOoQw8f91-1320Gq3CfQH4osFgbBwtwrVKNoMdvQ_8ZqNDifnHp430PNdPNbbCxsCC6GsW0Yh0SIqY-hUsDnZf5uF2DEi8EvWgVmZxJ3woGBXB53fPvsR4R-l_LtApp9cOtPe_th9mBIeBe0lZDfarO7dUd3kltVm2npZAh02rk2E10Xpg=w374-h646-no?authuser=0" alt="red-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
      <img src="https://lh3.googleusercontent.com/97JVZ7aceza_nzrBo8bOCccOlAbK9-YN2_z9Ei5H4hjAqEBiURCBggwnB7_R318zXUkPuVLkgZnFul88KlAQlubF7zqVfiegE9T7JMjLfEtwippON8LoElRJIBvk6Y97tgwnvLJuSQZWi68TsluRc7KfhFeddxvJclacahdO3QZY7RnJftH3HKCrhYAea6jvKNSvkyjfWD8ELtWAq0hwKGfT4Y37tofh_981M8Ym84wSpmZJjINiuqfxnY7dxVctLra-l_zAdh9FpqcpotvSrAQD-qOoZLDQ3hOrxs-8DuhvUlSlhzbyPmsmkn1tD1ksnK0Oz2Udy5b_IbsSW83djNp3x5uh90BjxxkuAQf9HzylVeNemhPLVhSLQCOXg5qXooTPLQgpQm_Q7mGJpTzFHlnpuqZQr9zQloap8_93pF1yT9e1N549mWtwe3ZwNU0cCivj05Vy7um-dNHTH-cWgFi0c_OuOd-xMw2TqwDZsdkrMWj6uM3zeY1N0nbWc_2VhEiI1iSv0xRKXrd9ngu5SlZTQ5pTzwDadmbPGV26A-s1N-v9ddDpH3o5oYrCJG9kc3am8atUoFfQhMjcGuvL3iZpTGf1HedDI79D4G47180iN6Ox4TDRYK0_6n-rOoWBqa9BAH3RFxChfCSvGUprmXguXRdnC1IfjulBXsq7G412VhKLPp8pf4O73oL-cjD_FmIEYyg1rreA317HARJlpDo=w374-h646-no?authuser=0" alt="orange-runway">
      <img src="https://lh3.googleusercontent.com/MizIxFYEnIXwY2S9gvmuCA01G0J1zLr1I_SJnoStVIbFBBLwE98Y1eEaOgu9JOjGCWCJTqMxz5BztnSJ1n5Jf49ihVcyXz1lZwRA1K06BRLUl6TxhcUU-ETSGySJKg7YTO6pSQtY6VUr1D6LHlUFf8FqhyLx66Pw3Vq2BcuIFsRaWgGTEUxRdfuY2SXyZbhdvrH2s__uIYKQHtblYAE5L-95idAI601QxclNXnqM1ra4y0azImHSKsLZkMn5gsK4rPy2-Pi6NcB7f3K2ngHKJiapcu2_hWLBIm3ceAjQtu5GeM48CtOA4DZM-UCZoDQApm_ceiH5Bzk_6sVAgNcPkeizd7lrd-PB0EBTU4z0-w8YCFWo9J7fnVpKqf8e2_4KlmZWvwxZ6HxW8d0eYWqJw2rov4EGRlwKzQqYth00bf8hkBA2q5fOgzPdmavN7V0X_w-oxq3SjTKOppUKgVxbLJrw0jA0zUvEIZq2x34_TbyIAIiteGNlI5nqlxPaZhmGxlBJVl21RTtRbMj61d6CcijzHfXNsJTXigOU_jdi6_HMdQ5KrFIq0uj2Z2fFIR3LSV2HXtf_Srr5Dmeg1OSV7xLbmzADYUHd4CM3pd9NyQCWJgYzfcup_NFMpbMwPXNsW5f-u6htCePLb-ztdtR8rxSfrBSK-TcTw9hoECh0rCumV7xxnvW7jwuflDXsmGs6FEkwW6gmTG8rFg_6acTpZDc=w374-h646-no?authuser=0" alt="blue-runway">
    </div>
  </main>
</body>
</html>
```
O objetivo de todos os exercícios abaixo é colocar os aviões azul, laranja e vermelho em suas respectivas pistas (azul, laranja e vermelho). Para fazer isso você deve alterar somente as especificações _CSS_, não é necessário alterar o arquivo _HTML_. A alteração deverá ser feita na classe _CSS_  ```answers```. 

### Exercício 2.1:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 130px;
  width: 130px;
}

.runway-div {
  display: flex;
  flex-wrap: wrap;
  align-content: space-around;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 110px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 2.2:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 130px;
  width: 130px;
}

.runway-div {
  display: flex;
  flex-wrap: wrap-reverse;
  align-content: flex-start;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 110px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 2.3:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 130px;
  width: 130px;
}

.runway-div {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-content: space-between;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 110px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 2.4:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 130px;
  width: 130px;
}

.runway-div {
  display: flex;
  flex-direction: row-reverse;
  flex-wrap: wrap;
  align-content: center;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 110px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Exercício 2.5:

#### Estrutura _CSS_

```
body {
  background-color: whitesmoke;
}

main {
  display: flex;
}

img {
  height: 130px;
  width: 130px;
}

.runway-div {
  display: flex;
  flex-wrap: wrap;
  align-content: space-evenly;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.airplanes-div {
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 2;
}

.runway-div img {
  width: 110px;
  margin: 0 10px;
}

.answers {
  /* Coloque sua resposta aqui */
}
```

### Bônus

### Clone Trybe Course

As instruções para a realização desse exercício bônus estão [nesse]() repositório, no arquivo __README.md__. Não queremos dar muitos spoilers, mas você encontrará o clone do course da Trybe assim:

![]()

E após aplicar seus conhecimentos de CSS Flexbox ele ficarará assim:

![Imgur](https://i.imgur.com/ED59Rvr.png)

Importante ressaltar que esse repositório possuí apenas um clone visual do Course, o que significa que ele não funciona como o original.

## Recursos adicionais (opcional)

[No CSS Flexbox, por que não existem propriedades "justify-items" e "justify-self"?](https://qastack.com.br/programming/32551291/in-css-flexbox-why-are-there-no-justify-items-and-justify-self-properties#:~:text=A%20especifica%C3%A7%C3%A3o%20flexbox%20permite%20o,removidos%20do%20fluxo%20de%20documentos%20.)

[Conceitos básicos de flexbox](https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#propriedade_align-items)

[CSS Flex Container](https://www.w3schools.com/css/css3_flexbox_container.asp)

[A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#background)

[Flexbox playground](https://codepen.io/enxaneta/full/adLPwv)

[Guia completo de Flexbox](https://origamid.com/projetos/flexbox-guia-completo/)
