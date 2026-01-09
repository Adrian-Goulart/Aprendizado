
Todo conteúdo baseado em:

[O QUE É GIT E GITHUB? - definição e conceitos importantes 1/2 ](https://www.youtube.com/watch?v=DqTITcMq68k&list=PL4jIL8-j0etB740IrpXzCg3R2UX0pHCcB&pp=gAQBa) por [Rafaella Ballerini](https://www.youtube.com/@rafaellaballerini)

[COMO USAR GIT E GITHUB NA PRÁTICA! - desde o primeiro commit até o pull request! 2/2](https://www.youtube.com/watch?v=UBAX-13g8OM&list=PL4jIL8-j0etB740IrpXzCg3R2UX0pHCcB&index=3) por [Rafaella Ballerini](https://www.youtube.com/@rafaellaballerini)

## O que é Git?
---

O git é um sistema de versionamento de arquivo, ou seja, é uma maneira de  controlar tudo que já escrevemos e apagamos, sendo muito necessário, pois assim pode-se mudar o código caso queira voltar atrás.

Com o Git, também é possível duas pessoas alterarem a mesma pasta de código sem gerar conflito, mas apenas se a modificação for em linhas diferentes. Isto ocorre de modo em que acontece um `merge` entre as alterações.

## Github
---

O Github é uma plataforma para hospedar o arquivos, dessa forma, podemos criar repositórios, nos quais são onde ficam os nossos projetos.

* ### Fork

 O **Fork**, ele puxa o código para um repositório no seu perfil e a partir disso você pode desenvolver por cima.

* ### Branch

A **Branch** é uma ramificação do projeto em que é possível desenvolver algo que está "por fora" do projeto, como por exemplo, adicionar funcionalidades extras.

* ### Commit

O **Commit** é a forma em que se posta/salva as mudanças que foi feita no código.

* ### Merge

O **Merge**, é o meio em que se funde uma branch com a branch principal, ou outra branch.

* ### Remote

O **Remote**, faz com que o repositório local se conecte com o repositório online

* ### Push

O **Push**, faz com que o commit seja enviado para o repositório remoto

* ### Pull

O **Pull**,  puxa o que está no repositório remoto para o local


# Comandos do git

---
### Init
---

 O `git init` vai inicializar um repositório git vazio na pasta, sendo onde for criada, o Branch master (main), ou seja, o principal.

Uso:

```
git init
```

### Add
---

O `git add` adiciona a ou as pastas para a área de *staging*, que é o que prepara para o commit.

Uso:

```
git add endereco
```

Para adicionar todas as alterações:

```
git add .
```

### Status
---

O `git status` permite ao usuário ver as mudanças a serem "commitadas"

Uso:

```
git status
```

### Commit
---

Para "commitar" uma mudança, basta fazer:

```
git commit -m "texto"
```

### Renomeação
---

Há um tempo o Git está mudando a Branch master para main, para renomear é necessário executar este código:

```
git branch -m "main"
```


# Conectar e enviar ao Github
---

Para se conectar a um repositório no github, além de se usar os comandos citados anteriormente, utilizaremos o `git remote`, desta forma:

```
git remote add origin <endereco.git>
```

Sem `<>`.

Desta forma, falamos para o git conectar o repositório local com o remoto, cujo nome é *origin*. Vale ressaltar que o  `origin` é uma nomenclatura padrão, mas que pode ser alterada.

Para enviar uma alteração para o repositório remoto utiliza-se o `git push`.

```
git push -U origin main
```

# Comparação de commits
---

Quando se altera, remove ou adiciona algo de algum arquivo, é possível verificar estas mudanças no github. As linhas vermelhas seguidas por linhas verdes, são alterações, linhas vermelhas isoladas, são linhas apagadas e linhas verdes isoladas, são linhas adicionadas. Sempre em relação ao commit anterior.

# Criando uma Branch
---

Para criar uma nova Branch utiliza-se o comando:

```
git checkout -b "nome"
```

Quando se cria uma branch ela não necessita de nenhum arquivo para ser "commitada".

Importante destacar que ao ser executado, além de se criar a nova branch, também muda a sua posição de branch anterior para a nova branch. Com isso em mente quando é importante tomar cuidado na hora do push, para não escrever a branch errada.

# Alterando de branches
---

Para alterar entre branches, utilizaremos o seguinte código:

```
git checkout <branch>
```

Sem `<>`.

# Junção de branches (merge)
---

Quando se deseja juntar duas branches, é possível fazer isto com o código:

```
git merge <branch>
```

Sem `<>`.

Com isto, a branch descrita no código, irá se juntar com a branch no local em que o código foi executado.

# Clone
---

Para trazer projetos de outras pessoas para seu computador, utiliza-se o git clone

```
git clone
```

Para trazer atualizações do repositório remoto, é preciso utilizar o `git pull`, desta forma *puxando* para o repositório local.

# Fork
---

Caso deseje clonar o repositório para o seu perfil do Github, é possível fazer isto com o *Fork*. O Fork é uma opção em que está localizada no próprio Github no repositório.

# Pull request
---

O *pull request* serve para um usuário no qual quer lançar algo dentro de um projeto no qual não faz parte consiga por meio dele. Antes disso, é necessário que usuário tenha feito um fork no repositório desejado, e logo após a alteração, fazer um *pull request* explicando o que foi alterado e assim o dono pode dar uma olhada para aceitar ou não.