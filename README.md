# Aprendendo-Java

[***Curso Maratona Virado no Jiraya***](https://www.youtube.com/playlist?list=PL62G310vn6nFIsOCC0H-C2infYgwm8SWW)

Estou escrevendo o que estou aprendendo nas aulas do [DevDojo](https://www.youtube.com/@DevDojoBrasil). Aulas não citadas significam que já tenho conhecimento do conteúdo apresentado.

---
#### 02 - Como Java Funciona

O Java possui a vantagem de escrever apenas uma vez e rodar em qualquer lugar, o arquivo em que escrevemos é um arquivo *.java*, para rodar em outros sistemas o arquivo passa por uma compilação (javac) onde passa a ser um arquivo *.class* (Bytecode), no qual a partir do JVM (Java Virtual Machine) consegue se comunicar com os outros sistemas, sendo que cada Sistema Operacional tem sua JVM. Para desenvolver aplicações em Java é utilizado o JDK (Java Development Kit) em que possui uma JVM, compilador e ferramentas que servem de ajuda ao desenvolvedor.

---
#### 15 - Operadores pt 01 - Relacionais

Não é possível executar uma operação após concatenar a expressão com uma String.

---
### 16 - Operadores pt 02 - Relacionais

Símbolos de operações básicas como adição, subtração, divisão, multiplicação e resto recebem o nome de **Operações Aritméticas**, enquanto as **Operações Relacionais** são comparações de valores (retornam *true* ou *false*). Padrão de nomenclatura para tipos booleanos começam com **is**.

---
### 19 - Operadores pt 05 - Atribuição

Os operadores (++) e (--) são chamados de operadores unários, por exemplo:

```Java
int contador = 0;
contador++;
```

A ordem de colocação dos sinais tem interferência no modo como é executado, enquanto for posicionado depois, será adicionado um valor somente se algo for feito em relação a variável, já quando posicionado antes será adicionado um valor sem a necessidade da variável passar por uma ação.

---
### 20 - Estruturas Condicionais pt 01 - IF

O operador de negação (!), tem a mesma função que a comparação para um valor false, exemplo:

```java
boolean bool = true;  
if (bool == false) {  
    System.out.println("Não executado");  
}
```

É a mesma coisa que:

```java
boolean bool = true;  
if (!bool) {  
    System.out.println("Não executado");  
}
```

---
### 25 - Estruturas Condicionais pt 06 - Switch

O Switch suporta somente os tipos char, int, byte, short, enum e String.

---
### 26 - Estruturas Condicionais pt 07 - Switch exercício

Por meio dos comentários aprendi que a partir do Java 14 tem o switch expression, uma maneira mais fácil e bonita da antiga maneira de tirar vantagem de uma funcionalidade do switch no qual na ausência de um ```break;``` ele continua executando. 

---
### 27 - Estruturas de Repetição pt 01 - Laços de repetição while, do while, for

O ```do while``` mesmo se a condição for falsa ela é executada ao menos uma vez , caso verdadeira continuará a ser executada até cumprir sua condição.

---
### 31 - Estruturas de Repetição pt 05 - Continue

O `continue` é o contrário do `break`, ele volta ao início da repetição e continua executando dentro do loop, quando condição estiver satisfeita, executa o resto do loop.

---
### 32 - Arrays pt 01

Arrays são sempre do tipo *reference* (e somente tipos de referência podem ser inicializados com valor nulo). Por terem mais de um valor sua nomenclatura é sempre no plural. Arrays são declaradas da seguinte forma:

```java
int[] numbers = new int [x];
```

O ***x*** representa o número de itens comportados pela lista. (Não é possível utilizar o `new` diretamente em tipos primitivos).

---
### 33 - Arrays pt 02

Valores padrões do tipos:
* byte, short, long, double, int, float = 0
* char = '\u0000' --> (Espaço em branco no Unicode)
* boolean = false
* String = null

---
### 34 - Arrays pt 03

O tamanho do array não pode ser alterado dinamicamente, contudo ele é um *objeto* e logo possui métodos.

Caso eu chame novamente uma lista, o espaço da referência antiga é perdida.

---

### 35 - Arrays pt 04 - Foreach

Um array também pode ser inicializado desta forma:

```Java
char[] letters = {'A', 'D', 'R', 'I', 'A', 'N'};
```

Ou

```Java
char[] letters = new char[]{'A', 'D', 'R', 'I', 'A', 'N'};
```

Dessa maneira já informando os valores e tamanho da lista.

O `foreach` funciona do seguinte modo para percorrer uma lista:

```Java
for (char character : letters) {
	System.out.println(character);
}
```

---

### 36 - Arrays Multidimensionais pt 01

Os arrays multidimensionais são como arrays de arrays. Para criar arrays multidimensionais basta adicionar mais colchetes (pode-se ter várias):

```Java
int[][] num = new int[3][3];
```

O primeiro valor nos colchetes a direita equivale ao tamanho do array **base**, os demais são as posições dentro deste array base e assim por diante.

Logo para percorrer esta lista fazemos:

```Java
for (int i = 0; i < num.length; i++) {
	for (int x = 0; x < num[0].length; x++) {
		System.out.println(num[i][x]);
	}
}
```

---

### 38 - Arrays Multidimensionais pt 03 - Inicialização

Para inicializar um array multidimensional precisamos fazer:

```Java
int[][] arrayInt = new int[3][];

arrayInt[0] = new int[3];
arrayInt[1] = new int[6];
arrayInt[2] = new int[9];
```

E para entender ficar melhor visualizando, o que pode-se ser feito com o seguinte código:

```Java
for (int[] arrayBase : arrayInt) {
	System.out.println("\n------");
	for (int num : arrayBase){
		System.out.print(num + " ");
	}
}
```

Também pode-se ser inicializada desta forma, já informando os valores:

```Java
arrayInt[0] = new int[]{1, 2, 3};
arrayInt[1] = new int[]{1, 2, 3, 4, 5, 6};

// Ou assim

int array = {1, 2, 3, 4, 5, 6, 7, 8, 9}

arrayInt[2] = array;
```

E para inicializar de maneira direta, faremos:

```Java
int[][] arrayInt2 = {{1, 2, 3}, {1, 2, 3, 4, 5, 6}}
```

---
# 47 - Orientação Objetos - Métodos pt 04 - Retorno pt 02

O `return` pode-se ser utilizado como um `break` para métodos do tipo void.

---
# 48 - Orientação Objetos - Métodos pt 05 - Parâmetros tipo primitivo

Quando se passa variáveis de tipo primitivo dentro de classes, a variável original nunca será alterada, independentemente do que aconteça dentro do método. O que acontece é que cria-se uma cópia e passa para uma nova variável de referência que está sendo criada dentro do método.

---

# 52 - Orientação Objetos - Métodos pt 09 - Varargs

O VarArgs é indicado com `int...`, ele funciona de maneira similar a um array, sua diferença está na hora da chamada, por exemplo em uma função de somar os números de uma lista:

Com array:
```Java
public class Calculator {  
    public void SumList(int[] list) {  
        int sum = 0;  
        for ( int num : list) {  
            sum += num;  
        }  
        System.out.println(sum);  
    }  
}
```

Chamada:
```Java
public class Main {  
    public static void main(String[] args) {  
        Calculator calculadora = new Calculadora();  
        calculator.SumList(new int[] {1, 2, 3, 4, 5, 6});  
    }  
}

// Resultado 21
```

Já com VarArgs:
```Java
public class Calculadora {  
    public void SumList(int... list) {  
        int sum = 0;  
        for ( int num : list) {  
            sum += num;  
        }  
        System.out.println(sum);  
    }  
}
```

Chamada:
```Java
public class Main {  
    public static void main(String[] args) {  
        Calculadora calculadora = new Calculadora();  
        calculadora.SumList(1,2,3,4,5,6);
    }
}

// Resultado 21
```

Vale ressaltar que nada pode-se ser colocado após o VarArgs, porque ele não identifica aonde seria o fim da lista, contudo é possível coloca-lo antes.

---

# 56 - Orientação Objetos - Modificador de acesso private, get e set pt 03

Não é recomendado a chamadas dos métodos `get` dentro do próprio atributo e sim usar o `this.`, afinal ele retornará o valor em memória.

---

# 57 - Orientação Objetos - Sobrecarga de métodos

A sobrecarga de métodos são métodos com o mesmo nome e a quantidade **OU** o tipo dos parâmetros diferentes. Também é demonstrada a utilização de um método que funciona de maneira similar (para não falar idêntico) a um construtor.

---

# 59 - Orientação Objetos - Construtores pt 02 - Sobrecarga

É possível também utilizar a sobrecarga em construtores, mas para se referir a um outro construtor é utilizado o `this();` e se necessário, argumentos. Vale ressaltar que isto funciona somente para construtores.

---

# 60 - Orientação Objetos - Blocos de inicialização

A execução dos objetos começam antes mesmo da execução dos construtores e os blocos de inicialização também. Os blocos de inicialização também são chamados de instância e são executados sempre na criação de um objeto, Também aprendi que há diferentes usos dos construtores, ou seja, posso ter duas maneiras ou mais de "inicializar" com construtores.

---

# 61 - Orientação Objetos - Modificador static

O modificador de acesso `static` vai fazer com que o atributo pertença a classe, logo todos os objetos iram compartilhar seu valor. Importante citar que não é recomendado o uso do `this` para acessar um atributo estático e sim a utilização do próprio objeto, exemplo:

```Java
public class Episodio {
	private String nome;
	private int episodios;
	public static int epLimite = 24;
	private int temporadas;
	
	public void imprime() {
		System.out.println("Episódios: " + this.episodios);
		System.out.println("Temporadas: " + this.temporadas);
		System.out.println("Episódios Limite: " + Episodio.epLimite);
	}
	
	// Outros códigos
}
```

---

# 62 - Orientação Objetos - Métodos estáticos

	Não pode-se adicionar nenhuma variável estática a um método não estático, mas o contrário é possível. É recomendado utilizar métodos estáticos quando o método não acessa uma variável.

---

# 63 - Orientação Objetos - Bloco de inicialização estático

Blocos de inicialização podem ser estáticas, com isso ela é executada apenas uma vez quando a classe é executada pela JVM, dessa forma economizando processamento. Caso haja mais de um bloco de inicialização estático eles são executados em ordem.

Os blocos não estáticos são executados a cada criação de objeto.

Acho importante trazer uma anotação da aula:

0. Bloco de inicialização é executado quando a JVM carrega a classe
1. Alocado espaço em memória pro objeto
2. Cada atributo da classe é criado e inicializado com valores default ou que for atribuído
3. Bloco de inicialização é executado
4. Construtor é executado

Nota: a posição 0 na lista, diz respeito a blocos de inicialização estáticos.

Métodos e variáveis estáticas tem prioridade no carregamento.

---

# 65 - Orientação Objetos - Associação pt 02 - Associação unidirecional um para muitos

A associação unidirecional é algo que referencia a outro em que este outro não referencia ao algo, simplificando, um objeto chamado *Integrante* referencia a outro objeto chamado *Guilda*, mas *Guilda* não referencia a *Integrante*.

---

# 66 - Orientação Objetos - Associação pt 03 - Associação unidirecional muitos para um

Segue a lógica do item anterior, mas desta vez *Integrantes* seria uma lista de integrantes na Guilda.

---

# 67 - Orientação Objetos - Associação pt 04 - Associação bidirecional

Ambos objetos se associam.

---

# 72 - Orientação Objetos - Herança pt 02 - Super

Em heranças se utiliza-se a palavra `super` para se referir a classe **superior**.

---

# 73 - Orientação Objetos - Herança pt 03 - protected

O `protected` é um modificador de acesso em que está disponível para uso em um escopo da classe, subclasse e pacote, mas não o escopo global.

---

# 75 - Orientação Objetos - Herança pt 05 - Sequência de inicialização

Atualização da ordem de inicialização:

0. Bloco de inicialização estático da superclasse é executado quando JVM carregar a classe pai.
1. Bloco de inicialização estático da sub classe é executado quando JVM carregar a classe filha.
2. Alocado espaço em memória pro objeto da superclasse.
3. Cada atributo da superclasse é criado e inicializado com os valores padrões ou os valores passados.
4. Blocos de inicialização da superclasse é executado em ordem.
5. Construtor da superclasse executado.
6. Alocado espaço em memória pro objeto da subclasse.
7. Cada atributo da subclasse é criado e inicializado com os valores padrões ou os valores passados.
8. Blocos de inicialização da subclasse é executado em ordem.
9. Construtor da subclasse executado.

---

# 76 - Orientação Objetos - Sobrescrita do método toString

O toString é uma maneira de imprimir informações da classe.

Algumas regras de sobrescrita, o nome e parâmetros têm de ser iguais, e o modificador de acesso não pode ser mais restritivo, ou seja, se for um private, a sobrescrita pode ser pública, mas não o contrário.   

---

# 77 - Orientação Objetos - Modificador final pt 01 - Tipo primitivo

Para criar uma constante no Java utilizamos o modificador `final` e tem que ser obrigatoriamente inicializado (construtores, inicializadores e atribuição direta por exemplo), além de que, geralmente por seu valor não mudar, associamos ela juntamente com o modificador `static`. Vale lembrar que para constantes sua nomenclatura é diferente, sendo ela toda em *UPCASE* e espaços separados por *underline* ( _ ), como pode-se observar:

```Java
public class NaveEspacial {
	public TipoNave;
	public static final double VELOCIDADE_LIMITE = 300000;
	
	// Resto do código
}
```

---

# 78 - Orientação Objetos - Modificador final pt 02 - Tipo referência

Em um caso de um objeto constante dentro de outro objeto, este não poderá ser alterado, pois a referência a ele é imutável, mas seus valores sim podem ser alterados. Também foi dito nesta aula que normalmente constantes seguem o padrão ***singleton pattern***.

---

# 79 - Orientação Objetos - Modificador final pt 03 - Classes e métodos

O modificador `final` utilizado em uma classe está diretamente ligado a herança, a  classe com este modificador não poderá ser estendida (*extends*), o mesmo vale para métodos, o método que tiver o modificador `final` não poderá ser sobrescrito.

---

# 80 - Orientação Objetos - Enumeração pt 01 - Introdução

A classe `enum` (enumerable) é utilizada quando se tem uma escolha em uma quantidade limitada de opções, na qual se deseja forçar o uso do tipo. Ele é uma classe onde seus atributos são constantes, logo basta somente escrever o nome da
constante, por exemplo:

```Java
public enum TipoClasse {
	MAGO,
	GUERREIRO,
	PALADINO,
	ASSASINO,
	ARQUEIRO,
	BARDO
}
```

Para comparação de Strings, é recomendado o uso de `.equals` e não o comparador `==`. 

---

# 81 - Orientação Objetos - Enumeração pt 02 - Construtores e atributos

O `enum` também pode ser feito dentro da classe, mas por questões de organização não é recomendado e para referencia-lo é necessário passar a *classe, enum, tipo*. Caso tiver um *import*, não é necessário passar a classe. 

Atributos também podem ser criados dentro de enumerables, para passar um valor é necessário criar um construtor (enumerables ainda são classes), o seu valor não pode vir antes das enumerações.

```Java
public enum TipoClasse {
	MAGO(1),
	CURANDEIRO(2),
	GUERREIRO(3),
	PALADINO(4),
	ASSASINO(5),
	ARQUEIRO(6),
	BARDO(7)
	
	public final int VALOR;
	
	TipoClasse(int valor) {
		this.VALOR = valor;
	}
}
```

ou

```Java
public enum TipoClasse {
	MAGO(1),
	CURANDEIRO(2),
	GUERREIRO(3),
	PALADINO(4),
	ASSASINO(5),
	ARQUEIRO(6),
	BARDO(7)
	
	private int valor;
	
	TipoClasse(int valor) {
		this.valor = valor;
	}
	
	public int getValor{
		return valor;
	}
}
```

Dessa forma se trabalha de forma mais intuitiva para as pessoas desenvolvendo.

Vale lembrar que também podemos fazer isso com mais de um tipo para enumeração.

---

# 82 - Orientação Objetos - Enumeração pt 03 - Sobrescrita de métodos

O construtor de um enum é privado, pois quem chama o construtor é a enumeração.

Podemos também utilizar métodos em enumerações, como no exemplo apresentado na aula para calcular o desconto sobre o tipo de pagamento. Para isso será necessário criar um método dentro do enum e sobrescrevê-los nas enumerações. O método não necessita de um corpo, logo será abstrato.

```java
public enum TipoPagamento {
	DEBITO {
		@Override
		public double calcularDesconto(double valor) {
			return valor * 0.1;
		}
	}, CREDITO {
		@Override
		public double calcularDesconto(double valor) {
			return valor * 0.05;
		}
	}
	
	public static double calcularDesconto(double valor);
}
```

Desta forma evitando utilizar if.

---

# 83 - Orientação Objetos - Enumeração pt 04 - Busca por atributos

Para retornar uma enumerable a partir de uma string (no qual ambas se baseiam), podemos utilizar o `.valueOf`, mas ele não retorna baseado no tipo e sim no nome da enumeração, então pode-se criar um  método para iterar sobre todos os tipos das enumerações utilizando o `values()`.

```Java
public enum TipoClasse {  
    MAGO(1, "Mago"),  
    CURANDEIRO(2, "Curandeiro"),  
    GUERREIRO(3, "Guerreiro"),  
    PALADINO(4, "Paladino"),  
    ASSASINO(5, "Assasino"),  
    ARQUEIRO(6, "Arqueiro"),  
    BARDO(7, "Bardo");  
    
    public final int VALOR;  
    public final String NOME_CLASSE;  
    
    TipoClasse(int valor, String nomeClasse) {  
        this.VALOR = valor;  
        this.NOME_CLASSE = nomeClasse;  
    }  
    
    public static TipoClasse classePorNomeClasse(String nomeClasse){ 
        for (TipoClasse tipoClasse : values()) {  
            if (tipoClasse.NOME_CLASSE.equals(nomeClasse)) {  
                return tipoClasse;
            }
        }
        return null;  
    }  
}
```

Execução:

```Java
TipoClasse tipoClasse2 = TipoClasse.classePorNomeClasse("Assasino"); 
System.out.println(tipoClasse2);

// Saída: ASSASINO
```

---

# 84 - Orientação Objetos - Classes abstratas pt 01

Classes abstratas basicamente servem para serem superclasses para suas implementações.  Ela em si não existe e sim suas extensões.

---

# 85 - Orientação Objetos - Classes abstratas pt 02 - Métodos abstratos

Métodos abstratos servem para forçar o uso dela em classes estendidas.

Classes abstratas podem ter variáveis e métodos abstratos ou não abstratos, mas classes concretas não podem ter métodos ou variáveis abstratas.

---

# 86 - Orientação Objetos - Classes abstratas pt 03 - Métodos abstratos regras

Classes abstratas que estendem de classes abstratas não precisam implementar o método abstrato, mas a primeira classe que estende dessa classe abstrata precisa implementar seu método abstrato. Caso o método for implementado dentro da classe abstrata, as demais classes concretas estendidas não precisaram mais implementá-la.

---

# 87 - Orientação Objetos - Interfaces pt 01 - Introdução

A *interface* funciona de forma parecida com classes abstratas. Seus métodos por padrão são `public abstract`, logo não é necessário passar esta informação, ficando desta forma:

```Java
public interface DataLoader {
	void load();
}
```

Por serem abstratos, não pode-se criar um corpo.

Para implementa-lá em outra classe, utilizamos o `implements` invés do `extends`.

```Java
public class DatabaseLoader implements DataLoader {
	@Override
	public void load() {
		// Código
	}
}
```

---

# 88 - Orientação Objetos - Interfaces pt 02 - Implementando múltiplas interfaces

Uma vantagem da interface, é que não há limite para a quantidade de implementação dela na classe.

Outra diferença da interface é que se é possível criar métodos concretos nela, a partir do modificador `default`.

```Java
public interface DataLoader {
	void load();
	
	default void checkPermission() {
		// Código
	}
}
```

Por padrão ele já vem público.

Se não sobrescrito ela é executada no nível da interface.

---

# 89 - Orientação Objetos - Interfaces pt 03 - Atributos e métodos estáticos

Não é possível criar um objeto através de uma interface, mas podemos decorar o tipo dela.

O modificador de acesso nunca poder ser mais restritivo do que a superclasse, ordem:

`private -> default -> protected -> public`

Por padrão todas as vaiáveis da interface são constantes.

Nela também é possível criar métodos estáticos 

---

# 91 - Orientação Objetos - Polimorfismo pt 02 - Funcionamento

O polimorfismo significa múltiplas formas, isto significa, trocar o tipo da variável de referência e continuar utilizando em outros objetos, somente aplicado na herança.

---

# 92 - Orientação Objetos - Polimorfismo pt 03 - Parâmetros polimórficos

Nesta aula é apresentada a ideia de que ao invés de se criar um método para cada classe, pode-se criar um método genérico, assim sendo um código mais limpo e estendendo-se mais facilmente.

---

# 93 - Orientação Objetos - Polimorfismo pt 04 - Cast e instanceof

Sobre o instanceOf, ele analisa se um objeto é uma instância de outro objeto, assim retornando *true* ou *false*. Também é necessário ficar de olho se o tipo da variável que está sendo feita o cast é uma instância dela.

---

# 94 - Orientação Objetos - Polimorfismo pt 05 - Programação orientada a interface

A programação orientada a interface permite utilizar o tipo mais genérico para poder implementar em qualquer classe que implemente-a. Por exemplo:

Pasta 1: Repositorio (Interface)

```Java
public interface Repositorio{
	void salvar();
}
```

Pasta 2: RepositorioBancoDeDados

```Java
public class RepositorioBancoDeDados implements Repositorio {
	@Override
	public void salvar() {
		System.out.println("Salvando em Banco de Dados");
	}
}
```

Pasta 3: RepositorioArquivo

```Java
public class RepositorioArquivo implements Repositorio {
	@Override
	public void salvar() {
		System.out.println("Salvando em Arquivo");
	}
}
```

Pasta 4: RepositorioMemoria

```Java
public class RepositorioMemoria implements Repositorio {
	@Override
	public void salvar() {
		System.out.println("Salvando na Memoria");
	}
}
```

Executável: RepositorioTeste

```Java
public class RepositorioTeste {  
    public static void main(String[] args) {  
	    
        Repositorio repo1 = new RepositorioBancoDeDados();
        Repositorio repo2 = new RepositorioArquivo();
        Repositorio repo3 = new RepositorioMemoria();
        
        repo1.salvar();
        repo2.salvar();
        repo3.salvar();
        
        // Saída:
        // Salvando em Banco de dados
        // Salvando em Arquivo
        // Salvando na Memoria
    }  
}
```

---

# 95 - Exceções pt 01 - Errors
O Erro e a Exceção são filhas da classe **Throwable**.

Os erros são coisas que acontecem na JVM e que provavelmente não será possível resolver com o código em execução. Podemos simular isto com erro StackOverflowError:

```Java
public class StackOverflowError {  
    public static void main(String[] args) {  
        Error();  
    }  
	 
    public static void Error() {  
        Error();  
    }  
}

// Saída: Exception in thread "main" java.lang.StackOverflowError
```

---

# 96 - Exceções pt 02 - RuntimeException

É muito importante saber a diferença entre ***Erro*** e ***Exceção***. O erro *lançado* (Throwable) é uma subclasse de *Error*, e quando a exceção é *lançada*, significa que são filhas de *Exception*.

Existem dois tipos de exceções, *Checked* e *Unchecked*. As exceções *checked* são diretamente filhas da classe Exception, se não tratadas, é lançado um erro em tempo de execução, assim nem conseguindo compilar o código. As unchecked (RuntimeException), quando lançadas, na maioria dos casos é erro de desenvolvimento.

[Aqui podemos verificar as subclasses da RuntimeException](https://docs.oracle.com/javase/8/docs/api/java/lang/RuntimeException.html)

---

# 97 - Exceções pt 03 - Exception

Nesta foi feito um teste de exceção *IOException*, para isso é necessário criar um arquivo. Para criar um arquivo criaremos um objeto da classe *File* informando o caminho do arquivo (pode mudar dependendo do Sistema Operacional) e logo após um de seus métodos.

**Teoricamente** ficaria assim:
```Java
public class IoExceptionTest {  
    public static void main(String[] args) {  
          
    }  
	
    public static void criarArquivo() {  
        File file = new File("arquivo/Novo-Aquivo.txt");  
        file.createNewFile();  
    }  
}
```

Este código apresenta uma exceção do tipo *Checked*, que não está sendo tratada, nos forçando a fazer uma tratativa. Precisamos falar para o Java que ele tente fazer algo, caso não der, pegar uma exceção. Podemos fazer isto com o `try {} catch() {}`.

Ficando desta forma:
```Java
public class IoExceptionTest {
    public static void main(String[] args) {
        createArchive();
    }
	
    public static void createArchive() {
        File file = new File("arquivo/Novo-Aquivo.txt");
        try {
            file.createNewFile();
        } catch (IOException e) {
            e.printStackTrace();
        }
		
    }
}
```

Desta maneira, será executada o método `createArchive`, no qual criará um objeto arquivo e em seguida **tentará** criar o arquivo em si, caso possível, o arquivo será criado, se não for possível,  ele mostrará o log do erro no console. (Para testar isso é necessário alterar a permissão da pasta).

**Adendos**:

 * No ``try`` e ``catch`` caso a exceção não for *Runtime*, a exceção no bloco do `catch` tem que ser uma no qual o código o bloco do `try` seja possível de ser lançada. Podemos verificar isto dentro do método `createNewFile` na parte ***throws IOException***. Também é possível utilizar a classe `Exception` pois ela é genérica, assim tratando de tudo, o que **NÃO É RECOMENDADO**, isto porque, no bloco do `try`, não se utiliza várias regras de negócios e se utilizado o `Exception`, será difícil saber de qual exceção se trata.
 
 * EVITAR utilizar lógica de negócio no `catch`, pois ele é utilizado somente para se lidar com exceções.
 
 * **NUNCA DEIXE O BLOCO** `catch` **EM BRANCO**, pois assim você não avisa que está havendo uma exceção.
 
 * Sempre leia a StackTrace.

Outros:

* É possível modificar o tipo do arquivo.

* Para utilizar barra invertida na string basta adicionar duas barras invertidas:
```Java
File file = new File("arquivo\\Novo-Aquivo.txt");
```

---

# 98 - Exceções pt 04 - Lançando exceção unchecked

Exceções uncheckeds são exceções Runtime. 

Para lançar uma exceção Runtime, foi utilizado de exemplo a divisão por 0.

```Java
public class ArithmeticExeptionTest {
    public static void main(String[] args) {
        System.out.println(division(10, 0));
    }
	
    public static int division(int x, int y) {
        return x / y;
    }
}

// Saída: Exception in thread "main" java.lang.ArithmeticException: / by zero
```

Quando acessamos a classe *ArithmeticException*, podemos ver que ela é Runtime e exceções Runtime, não é obrigatório o tratamento, somente caso queira. Para isso, utilizaremos o `try` e `catch`.

```Java
public class ArithmeticExeptionTest {  
    public static void main(String[] args) {  
        System.out.println(division(10, 0));  
    }  
	
    public static int division(int x, int y) {  
        try {  
            return x/y;  
        } catch (RuntimeException e){  
            e.printStackTrace();  
        }  
        return 0;  
    }  
}
```

Assim, tentará retornar a divisão, se não for possível, é mostrado o log de erro, mas por se tratar de um método com retorno obrigatório, é possível utilizar o `return` após o `try` e `catch`, porque o código ainda continua carregando. 

Por se tratar de uma divisão, sabe-se que não é possível dividir por 0, logo podemos adicionar uma condição no início da execução, e caso verdadeira, podemos lançar uma exceção com `throw new`.

```java
public class ArithmeticExeptionTest {  
    public static void main(String[] args) {  
        System.out.println(division(10, 0));  
    }  
    
    public static int division(int x, int y) {  
        if (y == 0) {  
            throw new IllegalArgumentException("Argumento ilegal, não pode ser 0");  
        }  
        return x/y;  
    }  
}
```

Desta maneira, se for divisão por 0, lançará uma exceção argumentando que não é possível a divisão por 0. É muito importante que a exceção seja a mais específica possível para ajudar no entendimento do código.


Pode-se informar a quem for utilizar o método que existe a possibilidade de `IllegalArgumentException`, utilizando-se do `throws` ficando da seguinte forma:

```Java
public class ArithmeticExeptionTest {  
    public static void main(String[] args) {  
        System.out.println(division(10, 0));  
    }  
	
    public static int division (int x, int y) throws IllegalArgumentException {  
        if (y == 0) {  
            throw new IllegalArgumentException("Argumento ilegal, não pode ser 0");  
        }  
        return x/y;  
    }  
}
```

E também por meio dos comentários:

```Java
public class ArithmeticExeptionTest {
    public static void main(String[] args) {
        System.out.println(division(10, 0));
    }
	
    /**
     *     * @param x
     * @param y não pode ser 0
     * @return
     * @throws IllegalArgumentException caso y for 0
     */
	
    public static int division (int x, int y) throws IllegalArgumentException {
        if (y == 0) {
            throw new IllegalArgumentException("Argumento ilegal, não pode ser 0");
        }
        return x/y;
    }
}
```

Com o atalho *CTRL + Q* é possível verificarmos estas informações.


---

# 99 - Exceções pt 05 - Lançando exceção checked

Não há a necessidade de colocar a assinatura no método quando a exceção for do tipo Runtime, **MAS** é obrigatório quando é uma exceção checked (diretamente filhas de Exception).

Geralmente o ```try``` e ```catch``` é utilizado dentro de métodos privados.

---

# 100 - Exceções pt 06 - Bloco Finally

Finally faz parte do `try` e `catch`. Ele serve como 'fechamento' do bloco de código, isto pois ele **SEMPRE** será executado, independentemente se ocorreu um erro ou o código funcionou como esperado.

```Java
public static void main(String[] args) {
    try {  
	    System.out.println("Iniciando..");
	    throw new RuntimeException();
	    
	} catch (Exception e) {  
	    e.printStackTrace();
	    
	} finally {  
		System.out.println("Finalizado");
		
	}  
	return null;
}
```

O `try` pode ser utilizado diretamente com o `finally`, ou seja, sem o `catch`, mas geralmente não se é utilizado.

```Java
public static void main(String[] args) {
	try {  
	    System.out.println("Iniciando..");
		
	} finally {
	    System.out.println("Finalizado");
	    
	}  
	return null;
}
```

 Importante falar que se não houver algum tratamento superior, o código será quebrado.

---

# 101 - Exceções pt 07 - Capturando múltiplas exceções

É possível utilizar vários `catch` em  junção ao `try`, logo sendo para tratar de múltiplas exceções que podem acontecer. Para isso, é importante que as exceções mais genéricas fiquem no final.

```Java
public static void ExceptionTesting() {
    try {
        throw new ArithmeticException();
        
    } catch (IllegalArgumentException e) {
        System.out.println("--> IllegalArgumentException");
        
    } catch (ArrayIndexOutOfBoundsException e) {
        System.out.println("--> ArrayIndexOutOfBoundsException");
        
    } catch (ArithmeticException e) {
        System.out.println("--> ArithmeticException");
	    
    } catch (RuntimeException e) {
        System.out.println("--> RuntimeException");
	    
    }
}

// Saída: --> ArithmeticException
```

---

# 102 - Exceções pt 08 - Multi catch em linha

É possível reduzir o `catch` a uma linhas, mas com isso as exceções **NÃO PODEM** estar na mesma linha de herança.

```Java
public static void ExceptionTesting() {
    try {
        ExceptionTest();
    } catch (SQLException | ArithmeticException e) {
        e.printStackTrace();
    }
    
    public static void ExceptionTest() throws ArithmeticException,     SQLException {}
}
```

Isso é utilizado para quando várias exceções podem  ser lidadas da mesma forma.

---

# 103 - Exceções pt 09 - Try with resources

Com o *Try with resources* você declara a variável e instância o objeto logo no `try`, para isso só podem ser utilizadas classes que implementam das classes ***Closeable*** e ***AutoCloseable***, porque o *Try with resources* ele se encarrega de fechar (finally) a variável de referência. O Java também sempre irá fechar na ordem **inversa** do que foi aberta

Com o *Try with resources*, pode-se utiliza-lo sem a necessidade de um `catch` ou `finally`, contudo você é obrigado a informar que o método lança (throws) a exceção lançada.

---

# 104 - Exceções pt 10 - Exceção customizada

Criar uma Exceção pode-se ser necessário as vezes e para isto basta criar uma classe no qual estenda do tipo de exceção desejada. Em sua nomenclatura é importante que contenha  "Exception" no final.

Exemplo:

```Java
public class LoginInvalidoException extends Exception {
    public LoginInvalidoException() {
        super("Login inválido");
    }
	
    public LoginInvalidoException(String message) {
        super(message);
    }
}
```

---

# 105 - Exceções pt 11 - Exceção e regras de sobrescrita

Sobre a sobrescrita de métodos que lançam exceções temos as seguintes regras:

-  Não é necessário que o método sobrescrito tenha exceções;
-  O método sobrescrito pode conter conter apenas uma exceção;
-  Qualquer exceção do tipo Runtime (unchecked) podem ser lançadas;
-  Não é possível declarar uma exceção superior (mais genéricas) as que pertencem  ao método super;
-  Não pode-se declarar nenhuma exceção do tipo checked além das que estão presentes no método super.

---

# 106 - Classes Utilitárias - Wrappers pt 01

Os wrapper's são **objetos** que vão encapsular os tipos primitivos, são os tipos primitivos:

```Java
byte byteP = 1;
short shortP = 10;
int intP = 100;
long longP = 1000L;
float floatP = 10F;
double doubleP = 10D;
char charP = 'A';
boolean booleanP = true;
```

Os wrapper's começam com o seu tipo com letra maiúscula, com exceção do `int` e o `char`, que ficam como, `Integer` e `Character` respectivamente.

```Java
Byte byteW = 1;
Short shortW = 10;
Integer intW = 100;
Long longW = 1000L;
Float floatW = 10F;
Double doubleW = 10D;
Character charW = 'A';
Boolean booleanW = true;
```

Os valores dos Wrapper's, estão relacionados com o polimorfismo, e não relacionado ao tamanho como são os tipos primitivos, ou seja, não é possível alocar o valor de um em outro.

---

# 107 - Classes Utilitárias - Wrappers pt 02

Existem dois conceitos em wrapper's, os autoboxing e unboxing.

O autoboxing é quando deixamos o Java transformar o tipo primitivo em wrapper.

```Java
Integer intW = 100;
```

O unboxing já é o contrário, ou seja, o Java transforma o wrapper em tipo primitivo.

```Java
int i = intW;
```

Os wrapper's por serem objetos possuem vários métodos, como por exemplos o parse, no qual transforma uma String no valor desejado.

```Java
Integer integer = Integer.parseInt("234");
System.out.println(integer);
```

---

# 108 - Classes Utilitárias - Strings pt 01

Toda String é criada no que chamamos de String Constant Pool (que está dentro do Heap).

```Java
public class StringTest {
    public static void main(String[] args) {
        String nome1 = "Adrian";
    }
}
```

Quando criamos uma variável de mesmo nome a String não será duplicada e sim reutilizada, ou seja, irá ser feita duas referência a mesma String, isto é o que chamamos de ***String Interning.***

```Java
public class StringTest {
    public static void main(String[] args) {
        String nome1 = "Adrian";
        String nome2 = "Adrian";
		
        // Utilização do == para comparar referências e não valores
        System.out.println(nome1 == nome2);
	}
}

// Saída: true
```

Contudo se tentarmos concatenar mais uma String ao nome, não iremos obter resultado.

```Java
public class StringTest {
    public static void main(String[] args) {
        String nome1 = "Adrian";
        String nome2 = "Adrian";
		
        nome1.concat(" Goulart");
		
		System.out.println(nome1);
        System.out.println(nome1 == nome2);
    }
}

// Saída: Adrian
//        true
```

Desta maneira na String Pool é criada uma String " Goulart" e também "Adrian Goulart", mas não há nenhuma variável de referência para estar Strings, então para obter o resultado concatenado, precisamos referenciá-la.

```Java
public class StringTest {
    public static void main(String[] args) {
        String nome1 = "Adrian";
        String nome2 = "Adrian";
        
        nome1 = nome1.concat(" Goulart");
		
        System.out.println(nome1);
        System.out.println(nome1 == nome2);
    }
}

// Saída: Adrian Goulart
//        false
```

Também podemos criar Strings de valores iguais mas com referências diferentes, mas não é muito utilizada.

```Java
public class StringTest {
    public static void main(String[] args) {
        String nome1 = "Adrian";
        String nome2 = new String("Adrian");
		
        System.out.println(nome1 == nome2);
    }
}
```

Com isto é criada uma String fora do Pool de Strings (o Heap), então o ***nome2*** está fazendo referência ao objeto ***Adrian*** dentro do Heap no qual encapsula o ***Adrian*** dentro da Pool de String. E para obter este valor encapsulado podemos utilizar o `nome1.intern()`. 

---

# 109 - Classes Utilitárias - Strings pt 02

Alguns métodos da String:

 `.charAt(index)`: Retorna o caractere da posição solicitada:

```Java
public class StringTest02 {
    public static void main(String[] args) {
        String nome1 = "Killua";
        System.out.println(nome1.charAt(0));
    }
}

// Saída: K
```

 `.length()`: Retorna o tamanho da String, length também é utilizado em arrays mas como atributo, já em string é como método.

```Java
public class StringTest02 {
    public static void main(String[] args) {
        String nome1 = "Killua";
        System.out.println(nome1.length());
    }
}

// Saída: 6
```

`.replace(x, y)`: Substitui o caractere de posição *x* pela *y*.

```Java
public class StringTest02 {
    public static void main(String[] args) {
        String nome1 = "Killua";
        System.out.println(nome1.replace("l", "u"));
	}
}

// Saída: Kiuuua
```

`.toLowerCase()` e `.toUpperCase()`: Deixam a String em minúscula  e maiúscula respectivamente.

```Java
public class StringTest02 {
    public static void main(String[] args) {
        String nome1 = "Killua";
        System.out.println(nome1.toLowerCase());
        System.out.println(nome1.toUpperCase());
    }
}

// Saída: killua
//        KILLUA
```

`.substring(beginning, end)`: Retorna os valores da String a partir do index de um ponto (beginning) até o index -1 do outro (end). Quando não informado o index final ele naturalmente vai até o final.

```Java
public class StringTest02 {
    public static void main(String[] args) {
        String nums = "0123456789";
		
        System.out.println(nums.substring(2, 7));
    }
}

// Saída: 23456
```

`.trim()`: Remove os espaços em branco do começo e final da String.

```Java
public class StringTest02 {
    public static void main(String[] args) {
        String nome1 = "      Killua              ";
		
        System.out.println(nome1.trim());
    }
}

// Saída: Killua
```

---

# 110 - Classes Utilitárias - Strings pt 03 - Desempenho

A String é uma classe que se for MUITO usada no código apresentará perda de desempenho, observável por meio deste código:

```Java
public class StringPerformanceTest {
    public static void main(String[] args) {
        long inicio = System.currentTimeMillis();
        concatString(100000);
        long fim = System.currentTimeMillis();
        System.out.println("Processo finalizado em " + (fim - inicio) + "ms");
    }
	
    private static void concatString(int tamanho) {
        String texto = "";
        for (int i = 0; i < tamanho; i++) {
            texto += i;
        }
    }
}
```

Para resolver isto foi criado o StringBuilder e o StringBuffer. Os dois são basicamente a mesma cosia, mas o StringBuffer ele foi criado para ambientes de acesso de múltiplas threads, quando se tem múltiplas threads acessando mesmo recurso.

Teste de comparação com cada um:

```Java
public class StringPerformanceTest {
    public static void main(String[] args) {
        long inicio = System.currentTimeMillis();
        concatString(10000);
        long fim = System.currentTimeMillis();
        System.out.println("String finalizado em " + (fim - inicio) + "ms");
		
        inicio = System.currentTimeMillis();
        concatStringBuilder(10000);
        fim = System.currentTimeMillis();
        System.out.println("StringBuilder finalizado em " + (fim - inicio) + "ms");
		
        inicio = System.currentTimeMillis();
        concatStringBuffer(100000);
        fim = System.currentTimeMillis();
        System.out.println("StringBuffer finalizado em " + (fim - inicio) + "ms");
    }
    
    private static void concatString(int tamanho) {
        String texto = "";
        for (int i = 0; i < tamanho; i++) {
            texto += i;
        }
    }
	
    private static void concatStringBuilder(int tamanho) {
        StringBuilder sb = new StringBuilder(tamanho);
        for (int i = 0; i < tamanho; i++) {
            sb.append(i);
        }
    }
	
    private static void concatStringBuffer(int tamanho) {
        StringBuffer sbf = new StringBuffer(tamanho);
        for (int i = 0; i < tamanho; i++) {
            sbf.append(i);
        }
    }
}
```

O recomendado é somente usar a StringBuilder ou a StringBuffer quando você sente que o sistema está pesando / lento.

---

# 111 - Classes Utilitárias - Strings pt 04 - StringBuilder

StringBuilder NÃO é uma String, ou seja não é imutável.

No StringBuilder podemos colocar dentro de sua estrutura, sua capacidade, uma String ou uma sequência de caracteres, caso não passado nada, será aplicado um valor de capacidade 16 caracteres, caso o valor seja ultrapassado quando em execução, o 16 será duplicado e assim segue adiante.

Para adicionar uma String a StringBuilder, somente com o método `.append()`

Conseguimos ver o resultado da StringBuilder (já que ela não e uma String) pois nela há um método `.toString()`.

O `.append()` também funciona como concatenação, por isto a StringBuilder apresenta um bom desempenho, pois ela é capaz de mudar a String sem ficar alocando espaço na Pool de String.

Para saber se a StringBuilder está de fato manipulando a String dentro do objeto, é necessário saber qual o retorno ela está oferecendo se é a String ou StringBuilder.

---

# 112 - Classes Utilitárias - Date

Importante falar que existem dois pacotes Date no java, o java `java.util` e o `java.sql`, um para trabalhar com aplicação do Java e outro com Banco de Dados respectivamente.

O date é representado por um *long* em milisegundos, a partir de 31/12/1969 

```Java
public class DateTeste01 {
    public static void main(String[] args) {
        Date date = new Date(1000000);
        System.out.println(date);
    }
}

// Saída: Wed Dec 31 21:00:00 BRT 1969

```

O resultado sai desta forma pois é convertido para String com o `toString()`.

Com o `date.getTime()` recebemos o long.

```Java
public class DateTeste01 {
    public static void main(String[] args) {
        Date date = new Date();
        System.out.println(date.getTime());
		 
    }
}

// Momento exato que executei: 1768948448364 
```

---

# 113 - Classes Utilitárias - Calendar

Também do `java.util`. Por ser uma classe abstrata, não se dá ao uso de `new`, então podemos chamar assim:

```Java
public class CalendarTest {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();
    }
}
```

Com ele há alguns métodos como:

Verificar se o primeiro dia da semana é domingo (ou algum outro dia);

```Java
public class CalendarTest {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();
          
        if (calendar.getFirstDayOfWeek() == Calendar.SUNDAY) {
            System.out.println("Domingo é o primeiro dia da semana");
        }
    }
}
```

Ver o dia da semana, do mês, do ano e o dia da semana no mês:

```Java
public class CalendarTest {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();
        
        System.out.println(calendar.get(Calendar.DAY_OF_WEEK));
		System.out.println(calendar.get(Calendar.DAY_OF_MONTH));
		System.out.println(calendar.get(Calendar.DAY_OF_YEAR));
		System.out.println(calendar.get(Calendar.DAY_OF_WEEK_IN_MONTH));
    }
}
```

Adicionar tempo:

```Java
public class CalendarTest {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();
        calendar.add(Calendar.DAY_OF_WEEK, 3);
        calendar.add(Calendar.HOUR, 2);
        
		
        Date date = calendar.getTime();
        System.out.println(date);
    }
}

// Saída: Sat Jan 24 20:31:50 BRT 2026
```

Quando se adiciona uma hora maior que o dia ele passará para o próximo dia e assim se segue, caso queira que o tempo excedente continue no mesmo dia usa-se o `.roll`:

```Java
public class CalendarTest {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();
        calendar.roll(Calendar.HOUR, 20);
		
        Date date = calendar.getTime();
        System.out.println(date);
    }
}

// Saída: Wed Jan 21 14:32:18 BRT 2026
```

---

# 114 - Classes Utilitárias - DateFormat

DateFormat também é uma classe estática, logo não é possível utilizar o `new`, mas neste caso por ser uma lista foi possível. Como o próprio nome já diz, com ele podemos formatar as datas das seguintes maneiras:

```Java
public class DateFotmatTeste01 {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();
        
        DateFormat[] df = new DateFormat[7];
        df[0] = DateFormat.getInstance();
        df[1] = DateFormat.getDateInstance();
        df[2] = DateFormat.getDateTimeInstance();
        df[3] = DateFormat.getDateInstance(DateFormat.SHORT);
        df[4] = DateFormat.getDateInstance(DateFormat.MEDIUM);
        df[5] = DateFormat.getDateInstance(DateFormat.LONG);
        df[6] = DateFormat.getDateInstance(DateFormat.FULL);
        
        for (DateFormat dateFormat : df) {
            System.out.println(dateFormat.format(calendar.getTime())); 
        }
    }
}

// Saída: 21/01/2026 18:51
// 21 de jan. de 2026
// 21 de jan. de 2026 18:51:42
// 21/01/2026
// 21 de jan. de 2026
// 21 de janeiro de 2026
// quarta-feira, 21 de janeiro de 2026 

```

---

# 115 - Classes Utilitárias - Internacionalização Datas com Locale

A classe Locale tem o intuito de regionalizar, com isso, dar suporte a várias línguas, como seu uso com Datas por exemplo:

```Java
public class LocaleTeste01 {
    public static void main(String[] args) {
        Locale localeBrazil = new Locale("pt", "br");
        Locale localeJapan = new Locale("ja", "jp");
		
        Calendar calendar = Calendar.getInstance();
        DateFormat dfBrazil = DateFormat.getDateInstance(DateFormat.FULL, localeBrazil);
        DateFormat dfJapan = DateFormat.getDateInstance(DateFormat.FULL, localeJapan);
        System.out.println("Brasil: " + dfBrazil.format(calendar.getTime()));
        System.out.println("Japão: " + dfJapan.format(calendar.getTime()));
    }
}

// Saída: Brasil: quinta-feira, 22 de janeiro de 2026
//        Japão: 2026年1月22日木曜日
```

Com o Locale nós criamos uma região e inserimos dentro do método `.getDateInstance(style, Locale)` que precisa ser informado o tipo da data e a região.

---

# 116 - Classes Utilitárias - Internacionalização Números com Locale

O `NumberFormat` sendo também uma classe abstrata, não pode ser instanciada. Ela serve para a formatação regional de números.

```Java
public class NumberFormatTest01 {
    public static void main(String[] args) {
        Locale localeBrazil = new Locale("pt", "br");
        Locale localeJapan = Locale.JAPAN;
        
        NumberFormat[] nf = new NumberFormat[3];
        nf[0] = NumberFormat.getInstance(localeBrazil);
        nf[1] = NumberFormat.getInstance(localeJapan);
        
        // Fazendo diretamente
        nf[2] = NumberFormat.getInstance(Locale.KOREA);
		
        float value = 3421831.54F;
        for (NumberFormat numberFormat : nf) {
            System.out.println(numberFormat.format(value));
        }
    }
}

// Saída: 3.421.831,5
//        3,421,831.5
//        3,421,831.5

```

---

# 117 - Classes Utilitárias - Internacionalização de moeda com Locale

Para moedas, ao invés de utilizar o `.getInstance()`, usaremos o `.getCurrencyInstance()`.

```Java
public class NumberFormatTest02 {
    public static void main(String[] args) {
        Locale localeBrazil = new Locale("pt", "br");
        Locale localeJapan = Locale.JAPAN;
        // Locale localeKorean = Locale.KOREA;
		
        NumberFormat[] nf = new NumberFormat[3];
		
        nf[0] = NumberFormat.getCurrencyInstance(localeBrazil);
        nf[1] = NumberFormat.getCurrencyInstance(localeJapan);
        nf[2] = NumberFormat.getCurrencyInstance(Locale.KOREA);
		
        float value = 3421831.54F;
        for (NumberFormat numberFormat : nf) {
            System.out.println(numberFormat.format(value));
        }
    }
}

// Saída: R$ 3.421.831,50
//        ￥3,421,832
//        ₩3,421,832
```

Também podemos pegar o números de casas depois da vírgula com o `.getMaximumFraction`:

```Java
public class NumberFormatTest02 {
    public static void main(String[] args) {
        Locale localeBrazil = new Locale("pt", "br");
        Locale localeJapan = Locale.JAPAN;
		
        NumberFormat[] nf = new NumberFormat[3];
		
        nf[0] = NumberFormat.getCurrencyInstance(localeBrazil);
        nf[1] = NumberFormat.getCurrencyInstance(localeJapan);
        nf[2] = NumberFormat.getCurrencyInstance(Locale.KOREA);
		
        float value = 3421831.54F;
        for (NumberFormat numberFormat : nf) {
            System.out.println(numberFormat.format(value));
            System.out.println("Casas: "+numberFormat.getMaximumFractionDigits());
        }
	}
}

// Saída: R$ 3.421.831,50
//        Casas: 2
//        ￥3,421,832
//        Casas: 0
//        ₩3,421,832
//        Casas: 0
```

Também podemos permitir um número máximo de casas

```Java
public class NumberFormatTest02 {
    public static void main(String[] args) {
        Locale localeBrazil = new Locale("pt", "br");
        Locale localeJapan = Locale.JAPAN;
        NumberFormat[] nf = new NumberFormat[3];
        
        nf[0] = NumberFormat.getCurrencyInstance(localeBrazil);
        nf[1] = NumberFormat.getCurrencyInstance(localeJapan);
        nf[2] = NumberFormat.getCurrencyInstance(Locale.KOREA);
        
        float value = 3421831.54F;
        for (NumberFormat numberFormat : nf) {  
            numberFormat.setMaximumFractionDigits(2);
            System.out.println(numberFormat.format(value));
            System.out.println("Casas: "+numberFormat.getMaximumFractionDigits());
        }
    }
}
// Saída: R$ 3.421.831,50
//        Casas: 2
//        ￥3,421,831.5
//        Casas: 2
//        ₩3,421,831.5
//        Casas: 2
```

Também podemos fazer o *parse* **para números**:

```Java
public class NumberFormatTest02 {
    public static void main(String[] args) {
        Locale localeBrazil = new Locale("pt", "br");
        Locale localeJapan = Locale.JAPAN;
        NumberFormat[] nf = new NumberFormat[4];
        
        nf[0] = NumberFormat.getInstance();
        nf[1] = NumberFormat.getInstance(localeJapan);
        nf[2] = NumberFormat.getInstance(Locale.KOREA);
        nf[3] = NumberFormat.getInstance(localeBrazil);
        
        String stringValue = "1000.2130";
        try {  
            System.out.println(nf[0].parse(stringValue));
        } catch (ParseException e) {  
            e.printStackTrace();
        }
    }
}

// Saída: 10002130
```

É possível utilizar o *underscore* para separar números no Java, mas neste caso não, por ser uma String. O *parse* ele TALVEZ retorne todo o número mas se tivesse um *underscore* ele iria considerar o número até lá.

Para o *parse* com moedas, precisamos informar no número o tipo da moeda:

```Java
public class NumberFormatTest02 {
    public static void main(String[] args) {
        Locale localeBrazil = new Locale("pt", "br");
        Locale localeJapan = Locale.JAPAN;
        NumberFormat[] nf = new NumberFormat[1];
		
        nf[0] = NumberFormat.getCurrencyInstance(localeJapan);
        
        double value = 1_000.2130;  
        for (NumberFormat numberFormat : nf) {  
            numberFormat.setMaximumFractionDigits(2);
            System.out.println(numberFormat.format(value));
        }
        
        String stringValue = "￥1000.2130";
        try {
            System.out.println(nf[0].parse(stringValue));
        } catch (ParseException e) {
            e.printStackTrace();
        }
    }
}

// Saída: ￥1,000.21
//         1000.213
```

Caso não informado, será lançado um Erro de Unparseable.

---

# 118 - Classes Utilitárias - SimpleDateFormat

O SimpleDateFormat permite que usemos as datas de uma forma mais flexível por meio de caracteres.

```Java
public class SimpleDateFormatTest01 {
    public static void main(String[] args) {
        String pattern = "dd 'de' MMMM 'de' YYYY";
        SimpleDateFormat sdf = new SimpleDateFormat(pattern);
        System.out.println(sdf.format(new Date()));
    }
}
```

Neste exemplo ele mostrará o dia/mês/ano. O que está entre aspas simples, é ignorado do pattern para mostrar  a data.

[Para verificar os caracteres](https://docs.oracle.com/javase/8/docs/api/java/text/SimpleDateFormat.html)

---

# 119 - Classes Utilitárias - LocalDate

A partir da versão 8 o Java implementou versões mais potentes de datas inspiradas pelo ***Joda Time***. Com isso veio várias métodos novos para facilitar o trabalho, como a `LocalDate`, que pode ser inicializada com `of` ou `now`.

```Java
public class LocalDatesTest01 {
    public static void main(String[] args) {
        LocalDate date = LocalDate.of(2026, Month.NOVEMBER, 13);
        System.out.println("Dia semana: " + date.getDayOfWeek());
        System.out.println("Dia mês: " + date.getDayOfMonth());
        System.out.println("Mês: " + date.getMonth());
        System.out.println("Ano: " + date.getYear());
        System.out.println("Tamanho mês: " + date.lengthOfMonth());
        System.out.println("Bissexto: " + date.isLeapYear());
    }
}

// Saída: Dia semana: FRIDAY
//        Dia mês: 13
//        Mês: NOVEMBER
//        Ano: 2026
//        Tamanho mês: 30
//        Bissexto: false
```

 Para algo mais específico podemos utilizar a Temporal Field.

```Java
public class LocalDatesTest01 {
    public static void main(String[] args) {
        LocalDate date = LocalDate.of(2026, Month.NOVEMBER, 13);
		
        System.out.println(date.get(ChronoField.YEAR));
        System.out.println(date.get(ChronoField.MONTH_OF_YEAR));
    }
}
```

A classe LocalDate é imutável, ou seja, não muda e sim é criando um outro objeto no qual precisaríamos associa-lo. Recomenda-se mais o uso de LocalDate.

---

# 120 - Classes Utilitárias - LocalTime

o LocalTime é muito importante quando se trabalha com coleta de dados baseado em datas.

```Java
public class LocalDatesTest01 {
    public static void main(String[] args) {
        LocalTime time = LocalTime.of(16, 5, 30);
        System.out.println("Segundos: " + time.getSecond());
        System.out.println("Minuto: " + time.getMinute());
        System.out.println("Hora: " + time.getHour());
        System.out.println("Tempo: " + time);
    }
}
```

Também é possível utilizar o *ChronicalField*:

```Java
public class LocalDatesTest01 {
    public static void main(String[] args) {
        LocalTime time = LocalTime.of(16, 5, 30);
		
        System.out.println("Segundos dia: " + time.get(ChronoField.SECOND_OF_DAY));
        System.out.println("Minuto dia: " + time.get(ChronoField.MINUTE_OF_DAY));
        System.out.println("Horas dia: " + time.get(ChronoField.HOUR_OF_DAY));
    }
}
```

---
	
# 121 - Classes Utilitárias - LocalDateTime

*LocalDateTime* também tem métodos iguais ao *LocalTime*. Ele mistura algumas coisas do *LocalDate* com o *LocalTime*.

Sobre LocalDate e LocalTime, caso não se queira pegar o valor diretamente do `.of`, é possível utilizar com uma String e até juntá-los:

```Java
public class LocalDateTimeTest01 {
    public static void main(String[] args) {
        LocalDate date = LocalDate.parse("2025-07-05");
        LocalTime time = LocalTime.parse("14:52:33");
        LocalDateTime dateTime = date.atTime(time);
        LocalDateTime timeDate = time.atDate(date);
        
        System.out.println(timeDate);
        System.out.println(dateTime);
    }
}

// Saída: 2025-07-05T14:52:33
//        2025-07-05T14:52:33
```

---

# 122 - Classes Utilitárias - Instant

A classes *Instant* é bem parecida com a *Date*, enquanto a *Date* conta em milisegundos a partir de  1° de Janeiro de 1970, a instant trabalha com nanosegundos.

Ela é uma classe imutável, ou seja, toda alteração gera uma nova instância.

O interessante da classe instante é que ela não conta o horário localmente e sim em *Zulu Time* que é exatamente a mesma coisa que *UTC*, ou seja, neutro, com isso é possível pegar horários mais precisos para um determinado evento.

```Java
public class InstantTest01 {
    public static void main(String[] args) {
        Instant now = Instant.now();
        System.out.println("Instant: " + now);
        System.out.println("LocalDT: " + LocalDateTime.now());
    }
}

// Saída: Instant: 2026-01-25T13:36:59.297998913Z
//        LocalDT: 2026-01-25T10:36:59.339373821
```

A partir do 'T' é possível verificar a hora e com isso percebe-se que o Zulu Time ou então o UTC é igual a 13h enquanto o localmente é 10h (UTC-3).

Por ser em nanosegundos seu valor não cabe em um long então desta forma foram criadas duas variáveis, a dos segundos e a dos nanosegundos dos segundos.

```Java
public class InstantTest01 {
    public static void main(String[] args) {
        Instant now = Instant.now();
        System.out.println(now.getEpochSecond());
        System.out.println(now.getNano());
    }
}

// Saída: 1769348938
//        205174482
```

A cada um bilhão de nanosegundos é igual a um segundo. Com o `Instant.ofEpochSecond(epochSecond, nanoAdjustment)` podemos somar ou subtrair um total de nanosegundos:

```Java
public class InstantTest01 {
    public static void main(String[] args) {
        Instant now = Instant.now();
        System.out.println(Instant.ofEpochSecond(5, 1_000_000_000));
    }
}

// Saída: 1970-01-01T00:00:06Z
```

Adicionamos primeiro os segundo e somamos ou subtrairmos uma quantidade em nanosegundos.

Esta classe é interessante para quando não se precisa trabalhar com dia, mês ou ano.

---

# 123 - Classes Utilitárias - Duration

O Duration tem alguns métodos interessantes como descobrir quanto tempo em horas equivale a tantos dias com o `ofDays` e também o `.between`, como o próprio nome já diz ele calcula o tempo entre dois valores.

```Java
public class DurationTest01 {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();  
        LocalDateTime nowAfterTwoYears = LocalDateTime.now().plusYears(2).plusMinutes(8);
        
        Duration d1 = Duration.between(now, nowAfterTwoYears);
        
        System.out.println(d1);
    }
}

// Saída: PT17520H8M0.000106742S
```

Nesta saída o "P" significa o período, ano (Y), mês (M), semana (w) e o dia (D), já o "T" é o tempo, hora (H), minuto (M) e segundo (S), Com isto em mente é possível entender que não se passou nenhum ano, mês, semana ou dia, mas se passaram 17520 horas e 8 minutos.

Também podemos utilizar com o *Time*:

```Java
public class DurationTest01 {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();
        LocalDateTime nowAfterTwoYears = LocalDateTime.now().plusYears(2).plusMinutes(8);
        LocalTime timeNow = LocalTime.now();
        LocalTime timePlus7Hours = LocalTime.now().plusHours(7);
        
        Duration d1 = Duration.between(now, nowAfterTwoYears);
        Duration d2 = Duration.between(timeNow, timePlus7Hours);
        
        System.out.println(d1);
        System.out.println(d2);
    }
}

// Saída: PT17520H8M0.000106742S
//        PT-16H-59M-59.999983818S
```

Também importante ressaltar que ela não aceita *LocalDate*, pois não suporta segundos.

---

# 124 - Classes Utilitárias - Period

A classe Period já trabalha com datas, diferentemente do Duration, logo, não é possível utilizar LocalDateTime ou LocalTime.

```Java
public class PeriodTest01 {
    public static void main(String[] args) {
        LocalDate now = LocalDate.now();
        LocalDate nowAfterTwoYears = LocalDate.now().plusYears(2);
        
        Period p1 = Period.between(now, nowAfterTwoYears);
        Period p2 = Period.ofDays(5);
        Period p3 = Period.ofWeeks(7);
        Period p4 = Period.ofMonths(3);
        Period p5 = Period.ofYears(4);
        
        System.out.println(p1);
        System.out.println(p2);
        System.out.println(p3);
        System.out.println(p4);
        System.out.println(p5);
    }
}

// Saída: P2Y
//        P5D
//        P49D
//        P3M
//        P4Y
```

O Period não guarda nenhum valor diferente ao próprio, por exemplo, o *p3* não guarda o valor de dias, o *p5* não guarda o valor de dias, semanas ou meses.

---

# 125 - Classes Utilitárias - ChronoUnit

Para mostrar o intervalo entre datas podemos utilizar o *ChronoUnit* desta forma:

```Java
public class ChronoUnitTest01 {
    public static void main(String[] args) {
        LocalDateTime birth = LocalDateTime.of(2007, 8, 2, 1, 0);
        LocalDateTime now = LocalDateTime.now();
        
        System.out.println(ChronoUnit.DAYS.between(birth, now));
        System.out.println(ChronoUnit.WEEKS.between(birth, now));
        System.out.println(ChronoUnit.MONTHS.between(birth, now));
        System.out.println(ChronoUnit.YEARS.between(birth, now));
    }
}
```

---

# 126 - Classes Utilitárias - TemporalAdjusters.

Quando quisermos pegar alguma data específica podemos utilizar o `.with()`:

```Java
public class TemporalAdjustersTest01 {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();
        now = now.withDayOfMonth(12); // Dia do mês
        now = now.withYear(2027); // Ano
        now = now.withMonth(5); // Mês
        System.out.println(now);
        System.out.println(now.getDayOfWeek());
    }
}

// Saída: 2027-05-12T16:38:25.980841748
//        WEDNESDAY
```

Também é possível com o *ChronoField*:

```Java
public class TemporalAdjustersTest01 {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();
		now = now.with(ChronoField.MONTH_OF_YEAR, 7); // Mês
		
        System.out.println(now);
        System.out.println(now.getDayOfWeek());
    }
}

// Saída: 2026-07-26T16:43:24.957819289
//        SUNDAY

```

 Desta forma não viramos os campos de forma contínua, diferentemente de somando.

O *TemporalAdjusters* possui alguns métodos uteis, como:

```Java
public class TemporalAdjustersTest01 {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();
        
        now = LocalDateTime.now().with(TemporalAdjusters.nextOrSame(DayOfWeek.MONDAY));
        System.out.println(now);
        System.out.println(now.getDayOfWeek());
        
        now = LocalDateTime.now().with(TemporalAdjusters.next(now.getDayOfWeek()));
        System.out.println(now);
        System.out.println(now.getDayOfWeek());
        
        now = LocalDateTime.now().with(TemporalAdjusters.previousOrSame(DayOfWeek.MONDAY));
        System.out.println(now);
        System.out.println(now.getDayOfWeek());
        
        now = LocalDateTime.now().with(TemporalAdjusters.previous(now.getDayOfWeek()));
        System.out.println(now);
        System.out.println(now.getDayOfWeek());
        
        now = LocalDateTime.now().with(TemporalAdjusters.lastDayOfMonth());
        System.out.println(now);
        System.out.println(now.getDayOfWeek());
    }
}
```

---

# 127 - Classes Utilitárias - TemporalAdjuster

Classe modelo de negócio:

```Java
class ObterProximoDiaUtil implements TemporalAdjuster {
    @Override  
    public Temporal adjustInto(Temporal temporal) {
        DayOfWeek dayOfWeek = DayOfWeek.of(temporal.get(ChronoField.DAY_OF_WEEK));
        int addDays;  
        switch (dayOfWeek) {
            case THURSDAY:
                addDays = 4;
                break;
            case FRIDAY:
                addDays = 3;
                break;
            case SATURDAY:
                addDays = 2;
                break;
            default:
                addDays = 1;
                break;
        }
        return temporal.plus(addDays, ChronoUnit.DAYS);
    }
}
```

Classe main:

```Java
public class TemporalAdjusterTest01 {
    public static void main(String[] args) {
        LocalDate today = LocalDate.now();
        System.out.println(today);
        System.out.println(today.getDayOfWeek());
        
        System.out.println("-------------------------");
        
        today = LocalDate.now().with(new ObterProximoDiaUtil());
        System.out.println(today);
        System.out.println(today.getDayOfWeek());
        
        System.out.println("-------------------------");
        
        today = LocalDate.now().withDayOfMonth(29).with(new ObterProximoDiaUtil());
        System.out.println(today);
        System.out.println(today.getDayOfWeek());
        
        System.out.println("-------------------------");
        
        today = LocalDate.now().withDayOfMonth(30).with(new ObterProximoDiaUtil());
        System.out.println(today);
        System.out.println(today.getDayOfWeek());
        
        System.out.println("-------------------------");
          
        today = LocalDate.now().withDayOfMonth(31).with(new ObterProximoDiaUtil());
        System.out.println(today);
        System.out.println(today.getDayOfWeek());
    }
}

// Saída: 2026-01-28
//        WEDNESDAY
//        -------------------------
//        2026-01-29
//        THURSDAY
//        -------------------------
//        2026-02-02
//        MONDAY
//        -------------------------
//        2026-02-02
//        MONDAY
//        -------------------------
//        2026-02-02
//        MONDAY
```

Quando se utiliza o `.with()` ele automaticamente chama o `adjustInto()`, portanto quando se passa um objeto que é um *TemporalAdjuster* ele vai chamar o `adjustInto()`.

---

# 128 - Classes Utilitárias - ZonedDateTime, ZoneId, OffsetDateTime

As zonas são faixas no qual determinam os fusos horários em determinadas localidades.

Podemos ver as zonas disponíveis no Java com o `ZoneId` da seguinte forma:

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        Map<String, String> shortIds = ZoneId.SHORT_IDS;
        System.out.println(shortIds);
    }
}
```

Também podemos pegar a zona padrão do sistema com `ZoneId.systemDefault()`:

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        System.out.println(ZoneId.systemDefault());
    }
}

// Saída: America/Sao_Paulo
```

Para pegar a zona de uma localidade específica podemos utilizar o `ZoneId.of` e utiliza-lo com o *LocalDateTime* com o método `atZone`:

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        ZoneId tokyoZone = ZoneId.of("Asia/Tokyo");
        
        LocalDateTime now = LocalDateTime.now();
        System.out.println(now);
        ZonedDateTime zonedDateTime = now.atZone(tokyoZone);  
		System.out.println(zonedDateTime);
    }
}

// Saída: 2026-01-28T18:39:57.283912451
//        2026-01-28T18:39:57.283912451+09:00[Asia/Tokyo]
```

O horário não é descontado na hora, mas nos é avisado que para chegar a tal horário precisaríamos somar ou subtrair tal quantidade de horas.

Vale lembrar que o `ZoneId.of()` tem de estar de acordo com as zonas do Java.

Para vermos com o valor já aplicado utilizamos a classe `Instant`:

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        Instant instant = Instant.now();
        System.out.println(instant);
        
        ZonedDateTime zonedDateTime2 = instant.atZone(tokyoZone);
        System.out.println(zonedDateTime2);
    }  
}

// Saída: 2026-01-28T22:06:59.185473064Z
//        2026-01-29T07:06:59.185473064+09:00[Asia/Tokyo]
```

Quando se sabe o horário mas não a zona podemos utilizar a classe `ZoneOffset()`. Ela permite utilizar horários com valores mínimos e máximos de -18:00 e 18:00 respectivamente.

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        ZoneOffset zoneOffset = ZoneOffset.of("-05:00");
        OffsetDateTime offsetDateTime = now.atOffset(zoneOffset);
        System.out.println(offsetDateTime);
    }
}

// Saída: 2026-01-28T19:13:50.482127974-05:00
```

Ou também podemos fazer desta forma:

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        OffsetDateTime offsetDateTime2 = OffsetDateTime.of(now, zoneOffset);
        System.out.println(offsetDateTime2);
    }
}

// Saída: 2026-01-28T19:13:50.482127974-05:00
```

Também podemos pegar calendários como o calendário Japonês:

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        JapaneseDate japaneseDate = JapaneseDate.from(LocalDate.now());
		System.out.println(japaneseDate);
    }
}

// Saída: Japanese Reiwa 8-01-28
```

Ou de até então alguma outra data:

```Java
public class ZoneTest01 {
    public static void main(String[] args) {
        LocalDate japaneaseDateTime = LocalDate.of(1900, 4, 2);
		JapaneseDate japaneseDate2 = JapaneseDate.from(japaneaseDateTime);
		System.out.println(japaneseDate2);
    }
}

// Saída: Japanese Meiji 33-04-02
```

---

# 129 - Classes Utilitárias - DateTimeFormatter

Para formatar datas utiliza-se o *DateTimeFormatter*:

```Java
public class DateTimeFormatterTest01 {
    public static void main(String[] args) {
        LocalDate date = LocalDate.now();
        String s1 = date.format(DateTimeFormatter.BASIC_ISO_DATE);
        String s2 = date.format(DateTimeFormatter.ISO_DATE);
        String s3 = date.format(DateTimeFormatter.ISO_LOCAL_DATE);
        System.out.println(s1);
        System.out.println(s2);
        System.out.println(s3);
    }
}

// Saída: 20260129
//        2026-01-29
//        2026-01-29
```

Quando temos a String e queremos transforma-la em objeto podemos utilizar o parse. Quando falamos de *Format*, estamos formatando um objeto para String e quando falamos de *parse*, estamos formatando de String para Objeto. 

```Java
public class DateTimeFormatterTest01 {
    public static void main(String[] args) {
        LocalDate p1 = LocalDate.parse("20260129", DateTimeFormatter.BASIC_ISO_DATE);
        LocalDate p2 = LocalDate.parse("2026-01-29", DateTimeFormatter.ISO_DATE);
        LocalDate p3 = LocalDate.parse("2026-01-29", DateTimeFormatter.ISO_LOCAL_DATE);
        
        System.out.println(p1);
        System.out.println(p2);
        System.out.println(p3);
    }
}
```

No parse precisamos informar a data e o padrão da data que passamos.

Também é possível utilizar com LocalDateTime da mesma forma:

```Java
public class DateTimeFormatterTest01 {
    public static void main(String[] args) {
        LocalDate date = LocalDate.now();
        String s1 = date.format(DateTimeFormatter.BASIC_ISO_DATE);
        String s2 = date.format(DateTimeFormatter.ISO_DATE);
        String s3 = date.format(DateTimeFormatter.ISO_LOCAL_DATE);
        System.out.println(s1);
        System.out.println(s2);
        System.out.println(s3);
        
        LocalDate p1 = LocalDate.parse("20260129", DateTimeFormatter.BASIC_ISO_DATE);
        LocalDate p2 = LocalDate.parse("2026-01-29", DateTimeFormatter.ISO_DATE);
        LocalDate p3 = LocalDate.parse("2026-01-29", DateTimeFormatter.ISO_LOCAL_DATE);
        System.out.println(p1);
        System.out.println(p2);
        System.out.println(p3);
        
        LocalDateTime now = LocalDateTime.now();
        String s4 = now.format(DateTimeFormatter.ISO_DATE_TIME);
        System.out.println(s4);
        LocalDateTime p4 = LocalDateTime.parse("2026-01-29T13:34:01.16693005", DateTimeFormatter.ISO_DATE_TIME);
        System.out.println(p4);
    }
}

// Saída: 2026-01-29T13:38:08.183694547
//        2026-01-29T13:34:01.166930050
```

E também com localidades:

```Java
public class DateTimeFormatterTest01 {  
    public static void main(String[] args) {  
        DateTimeFormatter formatterBr = DateTimeFormatter.ofPattern("dd/MM/yyyy");
        String formatBr = LocalDate.now().format(formatterBr);
        System.out.println(formatBr);
        LocalDate parseBr = LocalDate.parse("29/01/2026", formatterBr);
        
        DateTimeFormatter formatterJp = DateTimeFormatter.ofPattern("dd-MM-yyyy", Locale.JAPAN);
        String formatJapan = LocalDate.now().format(formatterJp);
        System.out.println(formatJapan);
        LocalDate parseJp = LocalDate.parse("29-01-2026", formatterJp);
        System.out.println(parseJp);
    }
}

// Saída: 29/01/2026
//        2026-01-29
//        29-01-2026
//        2026-01-29
```

---

# 130 - Classes Utilitárias - ResourceBundle

Com um ResourceBundle é possível traduzir labels das páginas.

Para utiliza-lo devemos criar um aquivo na pasta ***src***. Seu **nome base** não importa de fato, mas o que vem depois é de grande importância, deve se colocar a localização em língua e país separadas por "\_"  e logo após `.properties`, por exemplo, `messages_pt_BR.properties`. 

Este aquivo funciona como chave e valor, ou seja, uma chave única para tal valor.

```properties
# para comentários1
! para comentários2
  
hello = Olá
good.morning = Bom Dia!
```

Com isto utilizamos a classe ResourceBundle e o método `.getBundle(baseName, Locale)` para pegar estes valores:

```Java
public class ResourceBundleTest01 {
    public static void main(String[] args) {
        ResourceBundle.getBundle("messages", new Locale("pt", "BR"));
        System.out.println(bundle.getString("hello"));
        System.out.println(bundle.getString("good.morning"));
    }
}

// Saída: Olá
//        Bom Dia!
```

Sobre isso o Java tem umas regrinhas para saber qual ele deve pegar.
Supondo que nossa localização é "pt-BR", o Java tentará procurar por `messages_pt_BR.properties` se não achar, irá procurar por `messages_pt.properties`, se não achar, irá tentar procurar pelo padrão do seu sistema e se não achar, irá procurar por um aquivo no qual tenha o nome base `messages.properties`.

Exemplo supondo que utilizo o site em outra língua:

```Java
// Locale("ja", "JP"); --> Uso o site
// messages_ja_JP.properties
// messages_ja.properties
// messages_pt_BR.properties --> Padrão do Sistema
// messages_pt.properties
// messages.properties --> Último callback
```

---