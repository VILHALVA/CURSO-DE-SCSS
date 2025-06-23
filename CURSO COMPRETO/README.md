# INSTRUÇÕES

---
## INDICE:
* [01) INTRODUÇÃO](./README.md#01-introdução)
* [02) PRIMEIRO CONTATO](./README.md#02-primeiro-contato)
* [03) NESTING](./README.md#03-nesting)
* [04) HERANÇA EXTEND](./README.md#04-herança-extend)
* [05) VARIÁVEIS E IMPORT](./README.md#05-variáveis-e-import)
* [06) MIXIN](./README.md#06-mixin)
* [08) FUNÇÕES](./README.md#08-funções)
* [09) MINIFY](./README.md#09-minify)
* [10-14) PROJETO FINAL](./README.md#10-14-projeto-final)
---

## 01) INTRODUÇÃO
### O que é Sass?
Sass (Syntactically Awesome Stylesheets) é uma extensão de CSS que adiciona funcionalidades poderosas e elegantes à linguagem. Foi criado para facilitar a escrita e a manutenção de folhas de estilo, permitindo o uso de variáveis, aninhamento, mixins, herança e outras funcionalidades que não estão presentes no CSS puro.

### História
- **2006**: Criado por Hampton Catlin e inicialmente implementado por Natalie Weizenbaum, o Sass começou como um projeto em Ruby.
- **2010**: O SCSS (Sassy CSS) foi introduzido como uma nova sintaxe, mais próxima da sintaxe do CSS, facilitando a transição para novos usuários.
- **2012**: LibSass foi desenvolvido como uma implementação em C, proporcionando uma alternativa mais rápida e que pudesse ser integrada a mais ferramentas.
- **2019**: Dart Sass se tornou a implementação oficial recomendada, trazendo melhorias significativas em desempenho e compatibilidade.

### Características Principais
#### 1. **Variáveis**
Permitem armazenar valores que podem ser reutilizados ao longo da folha de estilo.

```scss
$primary-color: #3498db;

body {
  color: $primary-color;
}
```

#### 2. **Aninhamento**
Permite escrever seletores de uma forma mais clara e hierárquica.

```scss
nav {
  ul {
    list-style: none;
  }

  li {
    display: inline-block;
  }

  a {
    text-decoration: none;
  }
}
```

#### 3. **Partials e Importações**
Permitem dividir o CSS em múltiplos arquivos menores que podem ser importados para um arquivo principal.

```scss
// _reset.scss
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

// style.scss
@import 'reset';

body {
  font-family: Helvetica, sans-serif;
}
```

#### 4. **Mixins**
Permitem definir estilos reutilizáveis que podem ser incluídos em outros seletores.

```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

button {
  @include border-radius(10px);
}
```

#### 5. **Herança**
Permite que um seletor herde os estilos de outro, evitando duplicação de código.

```scss
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend %message-shared;
  border-color: green;
}

.error {
  @extend %message-shared;
  border-color: red;
}
```

#### 6. **Funções**
Permitem criar funções personalizadas que retornam valores baseados em parâmetros.

```scss
@function calculate-em($pixels, $base-font-size: 16px) {
  @return $pixels / $base-font-size * 1em;
}

.container {
  font-size: calculate-em(24px);
}
```

### Como Configurar e Usar?
1. **Instalar Node.js e npm**: [nodejs.org](https://nodejs.org/)
2. **Instalar Sass**:

   ```sh
   npm install -g sass
   ```

3. **Compilar Arquivos Sass**:

   ```sh
   sass input.scss output.css
   ```

4. **Automatizar a Compilação** (opcional):

   ```sh
   sass --watch input.scss:output.css
   ```

### Conclusão
Sass é uma poderosa ferramenta que expande as capacidades do CSS, tornando o desenvolvimento de estilos mais eficiente, organizado e sustentável. Com suas funcionalidades avançadas, você pode escrever folhas de estilo mais complexas de maneira mais simples e manter o código mais limpo e reutilizável.

## 02) PRIMEIRO CONTATO
Vamos começar com um exemplo básico para entender como o Sass funciona.
### Configurando o Ambiente
#### 1. Instalar Node.js e npm
Se você ainda não tem o Node.js instalado, baixe e instale a versão LTS do [site oficial do Node.js](https://nodejs.org/). O npm será instalado automaticamente com o Node.js.

#### 2. Instalar o Sass
Abra o terminal e execute o seguinte comando para instalar o Sass globalmente:

```sh
npm install -g sass
```

#### 3. Verificar a Instalação do Sass
Verifique se o Sass foi instalado corretamente executando:

```sh
sass --version
```

Você deve ver a versão instalada do Sass, o que confirma que a instalação foi bem-sucedida.

### Escrevendo o Primeiro Código Sass
Vamos criar um projeto simples para ver o Sass em ação.

#### 1. Criar a Estrutura de Pastas
Crie uma estrutura de pastas para o seu projeto:

```sh
mkdir meu-projeto-sass
cd meu-projeto-sass
mkdir scss css
```

#### 2. Criar um Arquivo SCSS
Crie um arquivo chamado `style.scss` dentro da pasta `scss`:

```sh
touch scss/style.scss
```

Abra o arquivo `scss/style.scss` em seu editor de texto preferido e adicione o seguinte código:

```scss
// Variável de cor primária
$primary-color: #3498db;

// Estilos para o corpo
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  color: $primary-color;
}

// Estilos para o cabeçalho
header {
  background-color: darken($primary-color, 10%);
  padding: 20px;
  text-align: center;
  
  h1 {
    margin: 0;
    color: white;
  }
}

// Estilos para links
a {
  color: $primary-color;
  text-decoration: none;
  
  &:hover {
    text-decoration: underline;
  }
}
```

#### 3. Compilar o SCSS para CSS
Use o comando Sass para compilar `style.scss` em `style.css`:

```sh
sass scss/style.scss css/style.css
```

Isso gerará um arquivo `style.css` na pasta `css` com o CSS compilado.

#### 4. Usar o CSS no HTML
Crie um arquivo `index.html` no diretório raiz do seu projeto e adicione o seguinte conteúdo:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="css/style.css">
  <title>Meu Projeto Sass</title>
</head>
<body>
  <header>
    <h1>Bem-vindo ao Meu Projeto Sass</h1>
  </header>
  <main>
    <p>Este é um parágrafo estilizado com Sass.</p>
    <a href="#">Este é um link estilizado com Sass</a>
  </main>
</body>
</html>
```

### Automatizando a Compilação
Para facilitar o desenvolvimento, você pode usar a opção `--watch` do Sass para compilar automaticamente sempre que fizer alterações no seu arquivo SCSS:

```sh
sass --watch scss/style.scss:css/style.css
```

## 03) NESTING:
O aninhamento (nesting) é uma característica importante do Sass que permite escrever CSS de forma mais hierárquica e organizada, seguindo a estrutura do HTML. Com o aninhamento, você pode economizar tempo e tornar seu código mais legível. Vamos explorar como funciona o aninhamento no Sass.

### Sintaxe de Aninhamento
No Sass, você pode aninhar seletores dentro de outros seletores para representar a estrutura HTML de forma mais clara. Por exemplo:

```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
    
    li {
      display: inline-block;
    }

    a {
      text-decoration: none;
    }
  }
}
```

Este código Sass é compilado para o seguinte CSS:

```css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav ul li {
  display: inline-block;
}

nav ul li a {
  text-decoration: none;
}
```

### Vantagens do Aninhamento
- **Legibilidade**: O aninhamento torna o código mais fácil de entender, refletindo a estrutura do HTML.
- **Organização**: Ajuda a manter o código organizado, especialmente para seletores aninhados.
- **Redução de Repetição**: Evita a repetição de seletores, economizando tempo e esforço na escrita do código.

### Considerações ao Usar Aninhamento
- **Não exagere**: Aninhar profundamente seletores pode levar a especificidade excessiva e dificultar a manutenção do código.
- **Mantenha-se Plano**: Evite aninhar muitos níveis de seletores. Se o aninhamento se tornar muito profundo, considere dividir o código em partes menores.

### Exemplo Prático
Vamos criar um exemplo prático de aninhamento para estilizar um menu de navegação simples:

```scss
nav {
  background-color: #333;
  padding: 10px;

  ul {
    margin: 0;
    padding: 0;
    list-style: none;

    li {
      display: inline-block;
      margin-right: 10px;

      a {
        color: #fff;
        text-decoration: none;
        padding: 5px;

        &:hover {
          background-color: #555;
        }
      }
    }
  }
}
```

Este código Sass cria estilos para um menu de navegação, onde os itens de menu são listados horizontalmente e mudam de cor ao passar o mouse sobre eles.

## 04) HERANÇA EXTEND
A herança através da diretiva `@extend` é uma poderosa característica do Sass que permite que um seletor herde os estilos de outro seletor. Isso evita a duplicação de código e promove a reutilização de estilos de uma maneira muito eficiente.

### Exemplo de Herança com `@extend`
Considere o seguinte exemplo em CSS:

```css
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}
```

Com o Sass, você pode usar a diretiva `@extend` para alcançar o mesmo resultado de uma maneira mais concisa e sem repetição de código:

```scss
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}
```

Neste exemplo:

- `.message` é definido com estilos comuns a todos os tipos de mensagens.
- `.success` e `.error` estendem (herdam) os estilos de `.message` e aplicam estilos adicionais específicos para cada tipo de mensagem.

### Considerações sobre Herança com `@extend`
- **Evitar Aninhamento Excessivo**: Assim como o aninhamento, evite estender seletor em profundidade excessiva para evitar aumento na especificidade e problemas de manutenção.
- **Cuidado com a Ordem**: A ordem das regras `@extend` é importante. A regra que estende deve aparecer após a regra que está sendo estendida.
- **Evitar Estilos Conflitantes**: Tome cuidado ao estender seletor com estilos muito genéricos, pois isso pode levar a estilos inesperados e conflitantes.

## 05) VARIÁVEIS E IMPORT
Variáveis e importações são recursos fundamentais do Sass que ajudam a organizar e reutilizar estilos de maneira eficiente.

### Variáveis
As variáveis no Sass permitem atribuir valores a nomes que podem ser reutilizados em todo o código. Isso é útil para armazenar cores, tamanhos de fonte, espaçamentos e outros valores que são usados repetidamente.

#### Exemplo de Variáveis:
```scss
$primary-color: #3498db;
$font-size: 16px;

body {
  font-family: Arial, sans-serif;
  font-size: $font-size;
  color: $primary-color;
}

button {
  background-color: $primary-color;
  color: white;
}
```

### Importações
As importações no Sass permitem dividir o código em arquivos menores e mais gerenciáveis, e depois importá-los para um arquivo principal. Isso é útil para separar estilos por componente, layout, ou qualquer outra organização que faça sentido para o seu projeto.

#### Exemplo de Importações:
Suponha que temos dois arquivos Sass, `base.scss` e `components.scss`, localizados em uma pasta chamada `scss`:

```scss
// base.scss
$primary-color: #3498db;

body {
  font-family: Arial, sans-serif;
  color: $primary-color;
}

// components.scss
@import 'base';

button {
  background-color: $primary-color;
  color: white;
}
```

Neste exemplo, o arquivo `components.scss` importa as variáveis definidas no arquivo `base.scss`, permitindo o uso dessas variáveis em todo o arquivo `components.scss`.

### Compilando Arquivos Sass
Para compilar os arquivos Sass em CSS, você pode usar a linha de comando com o comando `sass`. Por exemplo:

```sh
sass scss/style.scss css/style.css
```

Isso compilará o arquivo `style.scss` em CSS e o salvará como `style.css` na pasta `css`.

## 06) MIXIN
Os mixins são uma funcionalidade poderosa do Sass que permitem definir blocos de estilos reutilizáveis que podem ser incluídos em outros seletores. Eles são úteis para evitar a repetição de código e para criar abstrações que podem ser aplicadas em diferentes partes do seu estilo.

### Exemplo de Mixin:
```scss
// Definindo um mixin para estilos de borda arredondada
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

// Usando o mixin para aplicar borda arredondada em um botão
button {
  @include border-radius(5px);
}
```

Neste exemplo, o mixin `border-radius` define estilos para borda arredondada com base em um parâmetro `$radius`. Em seguida, o mixin é incluído no seletor `button` usando a diretiva `@include`, aplicando assim a borda arredondada a todos os botões.

### Benefícios dos Mixins:
- **Reutilização de Código**: Você pode definir estilos uma vez e reutilizá-los em vários lugares em seu código.
- **Abstração de Estilos**: Mixins permitem abstrair estilos complexos em unidades mais simples e compreensíveis.
- **Facilidade de Manutenção**: Se você precisar fazer alterações nos estilos, pode fazer isso em um único lugar (no mixin) e essas alterações serão refletidas em todos os lugares onde o mixin é incluído.

### Mixins com Parâmetros:
Os mixins podem aceitar parâmetros, o que os torna ainda mais flexíveis e poderosos. Por exemplo:

```scss
@mixin box-shadow($x, $y, $blur, $color) {
  -webkit-box-shadow: $x $y $blur $color;
     -moz-box-shadow: $x $y $blur $color;
          box-shadow: $x $y $blur $color;
}

// Uso do mixin com parâmetros
.box {
  @include box-shadow(5px, 5px, 10px, rgba(0, 0, 0, 0.5));
}
```

Neste exemplo, o mixin `box-shadow` aceita quatro parâmetros (`$x`, `$y`, `$blur` e `$color`) que são usados para definir a sombra da caixa. Quando o mixin é incluído no seletor `.box`, você pode passar valores específicos para esses parâmetros.

## 08) FUNÇÕES
As funções no Sass permitem criar blocos de código reutilizáveis que aceitam argumentos e retornam um valor. Elas são muito úteis para realizar cálculos, manipular valores e criar lógica dinâmica dentro de suas folhas de estilo.

### Exemplo de Função:
```scss
// Definindo uma função para calcular a largura de um elemento em porcentagem
@function calcular-largura-em-percentagem($largura, $largura-total) {
  @return percentage($largura / $largura-total);
}

// Usando a função para calcular a largura de um elemento em uma grade de 12 colunas
.container {
  width: calcular-largura-em-percentagem(4, 12); // 4 colunas de 12
}
```

Neste exemplo, a função `calcular-largura-em-percentagem` aceita dois argumentos: `$largura` (a largura do elemento) e `$largura-total` (a largura total da grade). A função calcula a largura do elemento como uma porcentagem da largura total da grade e retorna esse valor.

### Benefícios das Funções:
- **Reutilização de Código**: Você pode definir cálculos complexos ou lógica em uma função e reutilizá-la em vários lugares em seu código.
- **Abstração de Lógica**: Funções permitem abstrair lógica complexa em unidades mais simples e compreensíveis.
- **Flexibilidade**: As funções podem aceitar argumentos, permitindo que você personalize seu comportamento com base em valores específicos.

### Funções Integradas do Sass:
O Sass também fornece várias funções integradas que podem ser úteis para realizar operações comuns, como manipulação de cores, matemática, manipulação de strings, etc. Por exemplo:

```scss
// Manipulação de Cores
$cor: #3498db;
$cor-mais-clara: lighten($cor, 20%);
$cor-mais-escura: darken($cor, 20%);

// Operações Matemáticas
$resultado: 10px + 20px;

// Manipulação de Strings
$texto: to-upper-case("hello world");
```

## 09) MINIFY
Minificar (ou minify) é o processo de remover espaços em branco, quebras de linha, comentários e outras informações desnecessárias de um arquivo CSS ou JavaScript, reduzindo assim seu tamanho. Isso é feito para otimizar o desempenho do carregamento da página, reduzindo o tamanho dos arquivos transferidos pela rede.

No caso do Sass, após escrever e compilar seus arquivos `.scss` em arquivos `.css`, você pode aplicar a minificação para reduzir o tamanho dos arquivos de saída. Existem várias ferramentas e técnicas para fazer isso:

### Usando Ferramentas de Minificação:
Existem várias ferramentas de linha de comando e online que podem minificar arquivos CSS, como:

- **cssnano**: Uma ferramenta de minificação de CSS altamente configurável que pode ser usada como parte de uma tarefa de compilação ou como uma etapa pós-processamento.
- **UglifyCSS**: Outra ferramenta de minificação de CSS que pode ser usada para reduzir o tamanho dos arquivos CSS.
- **Online Minifiers**: Existem vários sites online que oferecem serviços de minificação de CSS gratuitos, onde você pode colar seu código CSS e obter o código minificado de volta.

### Automatizando a Minificação com Ferramentas de Build:
Se você estiver usando um sistema de build como Gulp, Grunt ou Webpack, é possível configurar tarefas para minificar automaticamente seus arquivos CSS como parte do processo de build. Existem plugins disponíveis para essas ferramentas que facilitam a minificação de arquivos CSS.

### Manualmente:
Você também pode minificar manualmente seus arquivos CSS removendo manualmente espaços em branco, comentários e quebras de linha. No entanto, isso pode ser tedioso e propenso a erros, especialmente em projetos maiores.

### Exemplo de Minificação de CSS com cssnano (Gulp):
Se você estiver usando Gulp como seu sistema de build, aqui está um exemplo de como você pode configurar uma tarefa para minificar seus arquivos CSS usando o pacote `gulp-cssnano`:

```javascript
const gulp = require('gulp');
const cssnano = require('gulp-cssnano');

gulp.task('minify-css', function() {
  return gulp.src('src/*.css')
    .pipe(cssnano())
    .pipe(gulp.dest('dist'));
});
```

Este é apenas um exemplo básico. Dependendo das suas necessidades específicas e da configuração do seu projeto, você pode precisar de uma configuração mais detalhada.

## 10-14) PROJETO FINAL
- [ABRA O `index.html` EM `./CODIGO` EM SEU NAVEGADOR](./CODIGO/index.html) 

