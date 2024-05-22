# CURSO DE SCSS
👨‍⚖️SCSS, CONHECIDO COMO SASS (SYNTACTICALLY AWESOME STYLESHEETS), É UMA LINGUAGEM DE FOLHA DE ESTILOS QUE FACILITA A ESCRITA E A MANUTENÇÃO DE CSS. COM O SASS, É POSSÍVEL UTILIZAR VARIÁVEIS, ANINHAR REGRAS, CRIAR MIXINS, FUNÇÕES E IMPORTAR ARQUIVOS, TORNANDO O PROCESSO DE ESTILIZAÇÃO MAIS EFICIENTE E ORGANIZADO. ELE É PROCESSADO EM UM ARQUIVO .SCSS PARA GERAR UM ARQUIVO .CSS QUE SERÁ UTILIZADO NO DESENVOLVIMENTO WEB.

<img src="FOTO.png" align="center" width="400"> <br>

## CONCEITO:
**Sass (Syntactically Awesome Stylesheets)** é uma linguagem de extensão do CSS que introduz funcionalidades avançadas para tornar a escrita de CSS mais eficiente, organizada e potente. O Sass é pré-processado, o que significa que é convertido para CSS antes de ser interpretado pelo navegador. Ele oferece duas sintaxes: Sass (indentada) e SCSS (Sassy CSS), sendo SCSS mais popular por sua similaridade com o CSS tradicional.

## SUA HISTÓRIA:
- **2006**:
  - O Sass foi criado por **Hampton Catlin**, um desenvolvedor web e engenheiro de software. Hampton buscava uma maneira mais eficiente de escrever e gerenciar CSS. Ele se inspirou nas limitações do CSS puro e desenvolveu o Sass como uma solução para essas limitações.
  - A primeira versão do Sass foi lançada em 2006. Nesta época, a sintaxe do Sass era indentada, o que significava que não usava chaves `{}` ou ponto e vírgula `;`. Isso proporcionava uma sintaxe mais limpa e legível, mas era bastante diferente do CSS tradicional.

- **2007**:
  - **Natalie Weizenbaum** juntou-se ao projeto e fez contribuições significativas, incluindo a introdução de muitas funcionalidades avançadas e a estabilização do código. Ela também é creditada por ter transformado o Sass em uma ferramenta poderosa e extensível.

- **2010**:
  - Em 2010, foi introduzida a sintaxe SCSS (Sassy CSS) com o lançamento do Sass 3. A sintaxe SCSS foi criada para ser uma superset do CSS, o que significa que todo CSS válido também é válido como SCSS. A adição do SCSS ajudou a aumentar a adoção do Sass, pois os desenvolvedores não precisavam aprender uma nova sintaxe completamente diferente.
  - A nova sintaxe permitiu o uso de chaves `{}` e ponto e vírgula `;`, tornando a transição do CSS para SCSS mais fácil e intuitiva para os desenvolvedores.

- **2012**:
  - O Sass começou a ganhar popularidade significativa na comunidade de desenvolvimento web. Foi adotado por muitos frameworks e ferramentas de desenvolvimento, como o Ruby on Rails.
  - A introdução de mixins, herança, variáveis, e outras funcionalidades poderosas solidificou a posição do Sass como um pré-processador CSS líder.

- **2013**:
  - **LibSass**, uma implementação em C/C++ do Sass, foi lançada. Isso permitiu que o Sass fosse usado em ambientes onde o Ruby não era uma opção viável, aumentando ainda mais sua popularidade.

- **2014 e Além**:
  - A comunidade continuou a crescer e contribuiu com plugins, extensões e melhorias contínuas. Ferramentas de construção como Grunt, Gulp e Webpack começaram a integrar suporte ao Sass, facilitando o uso em diferentes fluxos de trabalho de desenvolvimento.
  - Muitos frameworks CSS, como Bootstrap, começaram a adotar o Sass, permitindo uma personalização mais fácil e eficiente dos estilos.

- **2020 e 2021**:
  - Em 2020, o Sass completou 14 anos e continuou a ser uma ferramenta essencial para desenvolvedores front-end. A sintaxe SCSS é amplamente utilizada e continua a ser a escolha preferida para muitos projetos.
  - A manutenção e o desenvolvimento do Sass foram transferidos para a comunidade, com a equipe principal do projeto continuando a guiar seu desenvolvimento e evolução.

## CARACTERISTICAS:
### POSITIVAS:
- **Reutilização**: Com variáveis, mixins e herança, você pode evitar repetição de código.
- **Organização**: Aninhamento e importações ajudam a manter o código organizado e legível.
- **Manutenção**: Alterações são mais fáceis de fazer, já que você pode modificar uma variável ou mixin e essas mudanças se propagam por todo o CSS.
- **Produtividade**: Funções e controle de fluxo permitem criar estilos complexos de forma mais rápida e eficiente.

### NEGATIVAS:
1. **Complexidade Adicional**:
   - **Curva de Aprendizado**: Embora o Sass possa simplificar a escrita de CSS a longo prazo, ele adiciona uma camada de complexidade inicial que pode ser desafiadora para desenvolvedores novatos.
   - **Sintaxe Extra**: Os novos conceitos como mixins, funções, loops e heranças requerem tempo e prática para serem dominados.

2. **Dependência de Ferramentas**:
   - **Pré-processamento**: O Sass precisa ser compilado para CSS antes que possa ser interpretado pelo navegador. Isso requer ferramentas adicionais, como Node.js, npm, e um compilador de Sass, o que pode complicar o setup do projeto.
   - **Build Step**: A necessidade de um passo de build para compilar o Sass para CSS pode aumentar o tempo de desenvolvimento e a complexidade da configuração do projeto.

3. **Desempenho**:
   - **Tempo de Compilação**: Projetos grandes com muitos arquivos Sass podem ter tempos de compilação longos, o que pode afetar a produtividade e a experiência de desenvolvimento.
   - **Recursos do Sistema**: A compilação frequente de arquivos Sass pode consumir recursos significativos do sistema, especialmente em máquinas mais lentas.

4. **Manutenção**:
   - **Código Espaguete**: Com a capacidade de aninhar seletores e criar mixins complexos, há o risco de criar código CSS complicado e difícil de manter. O abuso de aninhamento pode resultar em seletores CSS profundamente aninhados, que são difíceis de entender e depurar.
   - **Dependências Complexas**: O uso excessivo de variáveis, mixins e heranças pode levar a um código CSS altamente interdependente. Modificações em uma parte do código podem ter efeitos inesperados em outras partes, tornando a manutenção desafiadora.

5. **Compatibilidade**:
   - **Diferenças entre Implementações**: Existem diferentes implementações do Sass (Ruby Sass, LibSass, Dart Sass), e nem todas as funcionalidades estão presentes ou funcionam da mesma forma em todas as implementações. Isso pode causar problemas de compatibilidade.
   - **Depreciação**: Algumas funcionalidades do Sass foram depreciadas ao longo do tempo, o que pode exigir a refatoração de código existente para garantir a compatibilidade com versões mais recentes.

6. **Colaboração em Equipe**:
   - **Consistência**: Em equipes grandes, garantir a consistência no uso de variáveis, mixins e outros recursos do Sass pode ser difícil. Diferentes estilos de codificação e práticas podem levar a um código desorganizado.
   - **Onboarding**: Novos membros da equipe podem encontrar desafios ao se familiarizar com um projeto existente que usa Sass extensivamente, especialmente se não houver uma documentação adequada.

## SUBSIDIOS:
- [CURSO CRIADO PELO "VIDA FULLSTACK"](https://youtube.com/playlist?list=PLMy95_4XE08OmaSd_GOLKNkqhoJFvg7w7&si=KwiMQ6JfcNeGX-KY)
- [CURSO FEITO PELO VILHALVA](https://github.com/VILHALVA)
- [VEJA A DOCUMENTAÇÃO](https://sass-lang.com/documentation/)
- [TECNOLOGIA](https://github.com/VILHALVA/CURSO-DE-NODEJS)
- [VEJA O MANUAL](./MANUAL.md)
- [VEJA A SINTAXE](./SINTAXE.md)
- [VEJA OS PROJETOS](https://github.com/VILHALVA?tab=repositories&q=topic:SCSS)