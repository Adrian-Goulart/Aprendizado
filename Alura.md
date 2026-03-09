# Curso 
# Java: aplicando a Orientação a Objetos

---
## 04. Aplicando comportamentos em comum
#### 02. Incluindo comportamentos adicionais -

O uso do `extends` nos códigos deixavam-o muito confusos caso utilizado em excesso, para isso surge a `Interface`. Ele funciona como uma espécie de "contrato" para outras classes, logo cada classe que implementa dela tem de utilizar o método que nela possui. Exemplo:

Criar uma interface:

```Java
public interface Classificavel {
	int getClassificacao();
}
```

Implementar uma interface:

```Java
public class Episodio implements Classificavel{
	// Código
}
```

---

### 03. Classificando episódios e filmes

A interface não pode ser criada como um objeto e sim apenas referenciada.

---

# Curso 
# Java: trabalhando com listas e coleções de dados

---
# 01. Coleção de Filmes
### 03 Lista de Filmes com ArrayList

O ArrayList é uma lista, sua sintaxe é:

```Java
ArrayList<x> lista = new ArrayList();
```

Onde ***x*** é o tipo da lista.

Para chamar seu tamanho utiliza-se `.size()` e para pegar o valor de um index, utilizamos `.get().metodo()`.

---
### 05 Para saber mais: arrays no Java

O array (não ArrayList) possuem algumas desvantagens, sendo:

* Tamanho fixo: seu tamanho é fixo, ou seja, não pode ser alterado;
* Ausência de Métodos: os arrays não possuem métodos como os de inserção, remoção ou pesquisa de elementos de forma eficiente.

---
### 06 Entendendo a hierarquia de classes e métodos

Todas as classes são "filhas" de uma outra chamada `objects`, nesta aula foi reforçada o método `.toString` e como altera-lo, uma vez que todas as classes herdam de `objects` basta substituir o método `toString`.

---

# 02. Construindo Objetos
## 05 Definindo outras formas de construir filmes e séries

Não há herança de construtores, para isso é necessário reescrever o construtor nas classes "filhas". Os construtores trazem informações "vitais" para o objeto

---

# 03. Lista de Objetos distintos

## 04 Identificando o Objeto

Variáveis de referência é algo que se utiliza para "chegar" a um objeto, por exemplo:

```Java
Objeto pessoa = new Objeto();

Objeto ps = pessoa;
```

O que acontece neste caso é como se as duas variáveis estivessem apontando para onde é o objeto e não criando um objeto em si no caso da terceira linha, com isso, o que é alterado é somente a forma de como se referencia ao objeto. A criação de um objeto só se deve a partir do `new`.

---

[[README]]

