# O que é?
---

Antigamente ao utilizar uma biblioteca ou framework, era possível que estes pacotes dependessem de outras bibliotecas ou frameworks. Logo, para baixar, também era necessário instalar as dependências de cada um e caso algum atualizasse, era preciso atualizar todos os outros manualmente, o que tornava um processo bem massivo. 

Para resolver isso, vieram os Gerenciadores de Dependências (ou Gerenciadores de Pacotes). A ideia dele é resolver todos os problemas que poderiam acontecer caso tentasse baixar tudo manualmente.

# Como funciona?
---

Escrevemos e declaramos num arquivo quais são as dependências do projeto e sua versão (pode ser utilizada uma regra para definir a versão, como, `">=1.0.0,<2.0.0"`).

Após declarar todas as dependências, rodamos o gerenciador de dependências e com base neste arquivo ele vai instala-las respeitando as versões declaradas.

# Onde o gerenciador busca as Bibliotecas ou Frameworks?
---

Também depende de qual gerenciador está sendo utilizado, mas a maioria tem um site próprio que funciona como um índice. Dessa forma o gerenciador após ler o arquivo, busca as dependências no site índice para entender onde está o código que irá ser baixado.

---

Com a maioria dos gerenciadores, quando baixadas, as dependências ficam em uma pasta específica. Importante não comitar esta pasta durante versionamento do projeto, porque irá ocupar espaço, queremos somente o nosso código e o arquivo declarativo, pois desta forma qualquer um poderá rodar o gerenciador e terá as mesmas versões, ou quase, porque como também é possível definir um intervalo de versões não sabemos qual versão irá ser escolhida.

Quando rodamos o programa, geralmente é gerado um arquivo chamado de "lock". Neste arquivo contém a informação da versão específica que o gerenciador baixou. Sendo assim, pode ser importante comitar este arquivo, visto que, qualquer pessoa no qual não contenha as dependências irá rodar o gerenciador e baixar exatamente a mesma versão.

Após rodarmos o gerenciador ele procura primeiro pelo arquivo ".lock", porque a partir dele que será baixada as dependências. Caso for a primeira vez, em seguida da tentativa de achar o arquivo ".lock", ele irá cria-lo.

# Bibliografia
---

[O que é um gerenciador de dependências?](https://www.youtube.com/watch?v=8XOkbHeFsv4)

[O que é gerenciador de dependências?](https://www.treinaweb.com.br/blog/o-que-e-gerenciador-de-dependencias)

---
