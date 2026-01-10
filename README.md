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

O polimorfismo significa múltiplas formas, isto significa, trocar o tipo da variável de referência e continuar utilizando outros objetos, somente aplicado na herança.

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

