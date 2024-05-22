# MANUAL
Para rodar um código SCSS e compilá-lo para CSS, você precisa instalar algumas ferramentas e configurar seu ambiente de desenvolvimento. Abaixo estão os passos detalhados para configurar e executar um projeto com SCSS.

## PASSO 1: INSTALAR NODE.JS E NPM
Se você ainda não tem Node.js e npm instalados, você precisa instalá-los. O Node.js vem com o npm (Node Package Manager), que você usará para instalar o Sass.

- **Windows/Mac**: Baixe e instale o Node.js do site oficial: [nodejs.org](https://nodejs.org/).
- **Linux**: Use o gerenciador de pacotes da sua distribuição. Por exemplo, no Ubuntu:

  ```sh
  sudo apt update
  sudo apt install nodejs npm
  ```

## PASSO 2: INSTALAR O SASS
Com o npm instalado, você pode instalar o Dart Sass, que é a implementação oficial e recomendada do Sass.

```sh
npm install -g sass
```

O comando `-g` (global) instala o Sass globalmente no seu sistema, tornando-o disponível em qualquer diretório.

## PASSO 3: CRIAR O PROJETO E ESTRUTURA DE DIRETÓRIOS
Crie um diretório para o seu projeto e uma estrutura básica de pastas.

```sh
mkdir meu-projeto
cd meu-projeto
mkdir scss css
```

Dentro da pasta `meu-projeto`, você terá duas subpastas: `scss` para seus arquivos SCSS e `css` para os arquivos CSS compilados.

## PASSO 4: ESCREVER O CÓDIGO SCSS
Crie um arquivo SCSS na pasta `scss`. Por exemplo:

```sh
touch scss/style.scss
```

Abra o arquivo `scss/style.scss` em seu editor de texto preferido e adicione algum código SCSS:

```scss
$primary-color: #3498db;

body {
  font-family: Helvetica, sans-serif;
  color: $primary-color;
}

nav {
  background: darken($primary-color, 10%);

  ul {
    list-style: none;
  }

  li {
    display: inline-block;
  }

  a {
    text-decoration: none;
    color: white;

    &:hover {
      color: yellow;
    }
  }
}
```

### PASSO 5: COMPILAR O SCSS PARA CSS
Use o comando `sass` para compilar seu arquivo SCSS para CSS. Navegue até o diretório do projeto e execute:

```sh
sass scss/style.scss css/style.css
```

Este comando compila `scss/style.scss` para `css/style.css`. 

## PASSO 6: AUTOMATIZAR A COMPILAÇÃO (OPCIONAL)
Para automatizar o processo de compilação sempre que você fizer alterações no seu arquivo SCSS, você pode usar a opção `--watch`:

```sh
sass --watch scss/style.scss:css/style.css
```

Isso fará com que o Sass observe o arquivo `style.scss` e compile automaticamente para `style.css` sempre que houver uma alteração.

## PASSO 7: INCLUIR O CSS NO HTML
Por fim, inclua o arquivo CSS gerado em seu arquivo HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="css/style.css">
  <title>Meu Projeto SCSS</title>
</head>
<body>
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</body>
</html>
```

