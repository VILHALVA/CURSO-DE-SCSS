# SINTAXE:
## GERAL
1. **Variáveis**:
   Permitem armazenar valores (cores, fontes, tamanhos, etc.) para reutilização.

   ```scss
   $primary-color: #3498db;
   $font-stack: Helvetica, sans-serif;
   ```

2. **Aninhamento**:
   Facilita a organização dos estilos refletindo a estrutura HTML.

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

3. **Partials e Importações**:
   Permitem dividir o CSS em arquivos menores e importá-los.

   ```scss
   @import 'reset';
   @import 'typography';
   ```

4. **Mixins**:
   São blocos de código reutilizáveis que aceitam parâmetros.

   ```scss
   @mixin border-radius($radius) {
     -webkit-border-radius: $radius;
        -moz-border-radius: $radius;
             border-radius: $radius;
   }
   
   .box { 
     @include border-radius(10px); 
   }
   ```

5. **Extends (Herança)**:
   Permite compartilhar um conjunto de propriedades entre seletores.

   ```scss
   .message {
     border: 1px solid #ccc;
     padding: 10px;
   }

   .success {
     @extend .message;
     border-color: green;
   }
   ```

6. **Funções**:
   O Sass inclui funções internas para manipulação de cores, strings, números, etc., e permite a criação de funções personalizadas.

   ```scss
   @function calculate-rem($px-value) {
     @return $px-value / 16px * 1rem;
   }

   body {
     font-size: calculate-rem(18px);
   }
   ```

7. **Controle de Fluxo**:
   Como condicionais (`@if`, `@else if`, `@else`) e loops (`@for`, `@each`, `@while`) para criar estilos dinâmicos e repetitivos.

   ```scss
   $theme: dark;

   body {
     @if $theme == light {
       background: white;
       color: black;
     } @else if $theme == dark {
       background: black;
       color: white;
     }
   }
   ```

## EXEMPLO COMPLETO
Aqui está um exemplo que combina várias dessas funcionalidades:

```scss
$primary-color: #3498db;
$secondary-color: #2ecc71;

@mixin button($color) {
  background-color: $color;
  border: none;
  padding: 10px 20px;
  color: white;
  cursor: pointer;
  font-size: 16px;

  &:hover {
    background-color: darken($color, 10%);
  }
}

.button-primary {
  @include button($primary-color);
}

.button-secondary {
  @include button($secondary-color);
}

@for $i from 1 through 3 {
  .col-#{$i} {
    width: 100% / 3 * $i;
  }
}
```

Neste exemplo, usamos variáveis, mixins, aninhamento e loops para criar um conjunto de botões estilizados e colunas flexíveis.