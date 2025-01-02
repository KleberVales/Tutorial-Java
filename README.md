# Tutorial-Java

## Fundamentos da linguagem java
1. Código-Fonte (.java)
2. Compilador (javac)
3. byte code (.class)
4. Máquina Virtual Java (JVM)

```
                     código fonte (.java)
                             |
                             |
                       Javac compiler
                             |
                      byte code (.class)
                             |
          ___________________|____________________
         |                   |                   |
  JVM Windows           JVM Linux             JVM Mac   

```
   
## Sintaxe do Java
1. Estrutura Básica
   
``` java
  public class MinhaClasse {
      public static void main(String[] args) {
          System.out.println("Olá, Mundo!"); // Imprime uma mensagem no console
      }
  }

```
2. Variáveis
``` java
int numero = 10;         // Inteiro
double pi = 3.14;        // Número decimal
char letra = 'A';        // Caractere
boolean ativo = true;    // Booleano (verdadeiro ou falso)
String nome = "Kleber";  // Cadeia de caracteres (String)

```
3. Estruturas Condicionais
   
if, else if, e else:
``` java
int idade = 18;
if (idade >= 18) {
    System.out.println("Maior de idade.");
} else {
    System.out.println("Menor de idade.");
}
```

switch:
``` java
int dia = 2;
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;
    case 2:
        System.out.println("Segunda-feira");
        break;
    default:
        System.out.println("Outro dia");
        break;
}
```
4. Estruturas de Repetição
for:
```java

for (int i = 0; i < 5; i++) {
    System.out.println("Valor de i: " + i);
}
```
while:
```java

int contador = 0;
while (contador < 5) {
    System.out.println("Contador: " + contador);
    contador++;
}
```
do-while:
```java

int contador = 0;
do {
    System.out.println("Contador: " + contador);
    contador++;
} while (contador < 5);

```
5. Métodos

``` java
public class MinhaClasse {
    public static void main(String[] args) {
        saudacao("Kleber");
    }

    public static void saudacao(String nome) {
        System.out.println("Olá, " + nome);
    }
}
```
6. Classes e Objetos
``` java
public class Pessoa {
    String nome;
    int idade;

    public void apresentar() {
        System.out.println("Meu nome é " + nome + " e tenho " + idade + " anos.");
    }

    public static void main(String[] args) {
        Pessoa pessoa = new Pessoa();
        pessoa.nome = "Kleber";
        pessoa.idade = 25;
        pessoa.apresentar();
    }
}
```
7. Comentários\
Os comentários são ignorados pelo compilador e ajudam a documentar o código.

Linha única: //  Este é um comentário

Múltiplas linhas:
```java

/* Este é um
   comentário de várias linhas */

```

## Programação Orientada a Objetos
A Programação Orientada a Objetos (POO) é um paradigma de programação baseado no conceito de objetos, que são instâncias de classes. Esses objetos encapsulam dados (atributos) e comportamentos (métodos), permitindo a modelagem de problemas do mundo real de forma mais intuitiva e modular.

### Princípios Fundamentais da POO

1. Encapsulamento
- Definição: Os detalhes internos de um objeto são ocultados, expondo apenas o necessário por meio de interfaces públicas. Isso protege os dados e controla o acesso a eles.
- Exemplo em Java:
``` java
public class Pessoa {
    private String nome;

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }
}
```

2. Herança
- Definição: Uma classe pode herdar atributos e métodos de outra classe. A classe que herda é chamada de subclasse, enquanto a classe de onde se herda é a superclasse.
- Exemplo em Java:

``` java
public class Animal {
    public void comer() {
        System.out.println("O animal está comendo.");
    }
}

public class Cachorro extends Animal {
    public void latir() {
        System.out.println("O cachorro está latindo.");
    }
}

public class Main {
    public static void main(String[] args) {
        Cachorro dog = new Cachorro();
        dog.comer(); // Herdado de Animal
        dog.latir(); // Específico de Cachorro
    }
}
```
3. Polimorfismo
- Definição: Um mesmo método ou objeto pode assumir diferentes formas, dependendo do contexto.
- Exemplo em Java:
``` java
public class Animal {
    public void emitirSom() {
        System.out.println("O animal emite um som.");
    }
}

public class Gato extends Animal {
    @Override
    public void emitirSom() {
        System.out.println("O gato mia.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Gato(); // Polimorfismo
        animal.emitirSom(); // Saída: "O gato mia."
    }
}
```
4. Abstração
- Definição: Simplificação da complexidade ao expor apenas os detalhes relevantes de um objeto. Em Java, isso é feito por meio de classes abstratas e interfaces.
- Exemplo com Interface:
``` java
public interface Veiculo {
    void mover();
}

public class Carro implements Veiculo {
    @Override
    public void mover() {
        System.out.println("O carro está se movendo.");
    }
}

public class Main {
    public static void main(String[] args) {
        Veiculo carro = new Carro();
        carro.mover();
    }
}
```
### Elementos Principais da POO em Java

1. Classe: Modelo ou "planta baixa" para criar objetos.
``` java
public class Pessoa {
    String nome;
    int idade;

    public void apresentar() {
        System.out.println("Meu nome é " + nome + " e tenho " + idade + " anos.");
    }
}
```
2. Objeto: Instância de uma classe.
``` java
public class Main {
    public static void main(String[] args) {
        Pessoa pessoa = new Pessoa();
        pessoa.nome = "Kleber";
        pessoa.idade = 25;
        pessoa.apresentar();
    }
}
```
3. Métodos: Comportamentos de uma classe.
```java
public class Calculadora {
    public int somar(int a, int b) {
        return a + b;
    }
}
```
4. Construtores: Métodos especiais usados para inicializar objetos.
```java
public class Pessoa {
    String nome;

    public Pessoa(String nome) {
        this.nome = nome;
    }
}
```
## Maniputaçao de Strings

A manipulação de strings em Java é uma tarefa comum e amplamente suportada pela classe String e por outras classes da biblioteca padrão, como StringBuilder e StringBuffer.

### Principais Características da Classe String

- Imutabilidade: Uma instância de String não pode ser alterada após ser criada. Qualquer operação que modifique uma string cria uma nova instância.
- Strings podem ser inicializadas diretamente usando aspas duplas (").

Exemplo:
```java
String nome = "Kleber";

```

### Métodos Comuns para Manipulação de Strings

1. Obter o Comprimento

```java
String texto = "Olá, mundo!";
int tamanho = texto.length();
System.out.println("Tamanho: " + tamanho); // Saída: 11

```

2. Comparação
- equals: Compara conteúdo.
- equalsIgnoreCase: Ignora diferença de maiúsculas e minúsculas.
  
``` java
String a = "Java";
String b = "java";

System.out.println(a.equals(b)); // false
System.out.println(a.equalsIgnoreCase(b)); // true

```

3. Concatenar Strings
- Com o operador + ou concat.
     
``` java
String nome = "Kleber";
String saudacao = "Olá, " + nome;
System.out.println(saudacao); // Olá, Kleber

String saudacao2 = "Olá, ".concat(nome);
System.out.println(saudacao2); // Olá, Kleber

```

4. Substring
- Extrai uma parte da string.
  
``` java
String texto = "Programação em Java";
String parte = texto.substring(14); // A partir do índice 14
System.out.println(parte); // "Java"

String parte2 = texto.substring(0, 12); // Do índice 0 ao 12 (exclusivo)
System.out.println(parte2); // "Programação"

```

5. Transformar Maiúsculas e Minúsculas

```java
String texto = "Java";
System.out.println(texto.toUpperCase()); // "JAVA"
System.out.println(texto.toLowerCase()); // "java"

```
6. Procurar Caracteres ou Substrings

- indexOf: Retorna a posição da primeira ocorrência.
- lastIndexOf: Retorna a posição da última ocorrência.

``` java
String texto = "Java é divertido!";
int posicao = texto.indexOf("é"); // 5
System.out.println(posicao);

int ultimaPosicao = texto.lastIndexOf("i"); // 13
System.out.println(ultimaPosicao);

```
7. Substituir Caracteres ou Substrings
```java
String texto = "Java é legal!";
String novoTexto = texto.replace("legal", "incrível");
System.out.println(novoTexto); // "Java é incrível!"

```

8. Remover Espaços

- trim: Remove espaços no início e no fim.

``` java
String texto = "   Olá, Java!   ";
System.out.println(texto.trim()); // "Olá, Java!"

```

9. Dividir uma String

- split: Divide uma string em partes com base em um delimitador.

``` java
String texto = "Java,Python,C++";
String[] linguagens = texto.split(",");
for (String linguagem : linguagens) {
    System.out.println(linguagem);
}

```

10. Verificar Conteúdo

- contains: Verifica se a string contém uma substring.
- startsWith: Verifica se a string começa com algo.
- endsWith: Verifica se a string termina com algo.

``` java
String texto = "Aprender Java é divertido!";
System.out.println(texto.contains("Java")); // true
System.out.println(texto.startsWith("Aprender")); // true
System.out.println(texto.endsWith("divertido!")); // true

```

### Uso de StringBuilder e StringBuffer

Essas classes são mutáveis e mais eficientes para operações repetitivas de manipulação de strings.

1. StringBuilder

Ideal para operações em um único thread.

```java
StringBuilder sb = new StringBuilder("Olá");
sb.append(", mundo!"); // Adiciona texto
System.out.println(sb); // "Olá, mundo!"

```

2. StringBuffer

Semelhante ao StringBuilder, mas seguro para threads.

```java
StringBuffer sb = new StringBuffer("Olá");
sb.append(", mundo!"); // Adiciona texto
System.out.println(sb); // "Olá, mundo!"

```



## Coleções e Arrays
Coleções e arrays são fundamentais em Java para armazenar, manipular e organizar dados. Enquanto arrays oferecem um mecanismo básico para armazenar elementos de forma estática, coleções fornecem ferramentas mais flexíveis e poderosas.

1. Arrays em Java
   
Um array é uma estrutura de dados que armazena uma coleção de elementos do mesmo tipo, com tamanho fixo.

### Declaração e Inicialização
``` java
int[] numeros = new int[5]; // Declaração com tamanho
int[] valores = {10, 20, 30, 40, 50}; // Inicialização direta

```
### Acessar Elementos
```java
int[] numeros = {1, 2, 3, 4, 5};
System.out.println(numeros[0]); // Saída: 1

```
### Percorrendo Arrays
``` java
int[] numeros = {1, 2, 3, 4, 5};

// For tradicional
for (int i = 0; i < numeros.length; i++) {
    System.out.println(numeros[i]);
}

// For-each
for (int num : numeros) {
    System.out.println(num);
}

```
2. Coleções em Java

Java fornece a API de coleções no pacote java.util, que inclui interfaces e classes para manipular listas, conjuntos e mapas.

### Principais Interfaces

- List: Coleção ordenada que permite elementos duplicados. classes: ArrayList, LinkedList.
- Set: Coleção que não permite duplicatas. classes: HashSet, TreeSet
- Map: Estrutura de chave-valor. classes: HashMap, TreeMap

## Entrada e Saida de dados

Em Java, a entrada e saída de dados é realizada por meio das classes fornecidas no pacote java.io e da biblioteca padrão. Aqui estão os conceitos principais:

### Entrada de Dados

A entrada de dados pode ser feita de várias formas, dependendo do contexto.

1. Usando Scanner

A classe Scanner é a maneira mais comum de ler dados do usuário via console.

- Exemplo - Leitura de Inteiros e Strings
```java
import java.util.Scanner;

public class EntradaScanner {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Lendo um número inteiro
        System.out.print("Digite um número inteiro: ");
        int numero = scanner.nextInt();

        // Limpando o buffer (necessário ao alternar entre nextInt/nextLine)
        scanner.nextLine();

        // Lendo uma string
        System.out.print("Digite seu nome: ");
        String nome = scanner.nextLine();

        System.out.println("Olá, " + nome + "! Você digitou o número " + numero + ".");
        scanner.close();
    }
}

```
- Principais Métodos de Scanner

| Método	  |              Descrição                 |
|------------------|---------------------------------------|
| nextLine()	| Lê uma linha inteira como String.         |
| next()	    | Lê a próxima palavra como String.         |
| nextInt()	  | Lê um número inteiro.                     |
| nextDouble()|	Lê um número decimal (double).            |
| nextBoolean()|	Lê um valor booleano (true ou false).   |

2. Usando BufferedReader

BufferedReader é uma maneira mais eficiente para leitura de grandes volumes de dados.

- Exemplo - Leitura com BufferedReader

``` java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.IOException;

public class EntradaBufferedReader {
    public static void main(String[] args) throws IOException {
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));

        System.out.print("Digite seu nome: ");
        String nome = reader.readLine();

        System.out.println("Olá, " + nome + "!");
    }
}

```

### Saída de Dados

A saída de dados em Java é feita principalmente com as classes System.out.

1. Usando System.out.print e System.out.println

- print: Exibe texto na mesma linha.
- println: Exibe texto e quebra a linha.

- Exemplo

``` java
public class SaidaSimples {
    public static void main(String[] args) {
        System.out.print("Este é um texto ");
        System.out.println("com uma quebra de linha.");
    }
}

```

2. Formatação de Saída com printf

O método printf permite formatação detalhada da saída.

- Exemplo - Saída Formatada

```java
public class SaidaFormatada {
    public static void main(String[] args) {
        String nome = "Kleber";
        int idade = 30;
        double salario = 2500.50;

        System.out.printf("Nome: %s, Idade: %d, Salário: %.2f%n", nome, idade, salario);
    }
}
```
| Placeholder |	Descrição |
|-------------|------------|
|%s	 | String. |
|%d	| Inteiro decimal. |
|%f	| Número de ponto flutuante (float/double). |
|%.2f |	Número de ponto flutuante com 2 casas decimais. |
|%n	| Quebra de linha (plataforma independente). |

### Entrada e Saída de Arquivos

A leitura e escrita em arquivos pode ser feita com várias classes, como FileReader, FileWriter, BufferedReader, e BufferedWriter.

1. Escrever em um Arquivo

```java
import java.io.FileWriter;
import java.io.IOException;

public class EscreverArquivo {
    public static void main(String[] args) {
        try (FileWriter writer = new FileWriter("saida.txt")) {
            writer.write("Olá, este é um exemplo de escrita em arquivo.");
            System.out.println("Arquivo escrito com sucesso!");
        } catch (IOException e) {
            System.err.println("Erro ao escrever no arquivo: " + e.getMessage());
        }
    }
}

```

2. Ler de um Arquivo

``` java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class LerArquivo {
    public static void main(String[] args) {
        try (BufferedReader reader = new BufferedReader(new FileReader("saida.txt"))) {
            String linha;
            while ((linha = reader.readLine()) != null) {
                System.out.println(linha);
            }
        } catch (IOException e) {
            System.err.println("Erro ao ler o arquivo: " + e.getMessage());
        }
    }
}

```
### Entrada e Saída com Dados Binários

Para manipulação de dados binários, você pode usar DataInputStream e DataOutputStream.

- Exemplo - Escrevendo Dados Binários

```java
import java.io.DataOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class EscreverBinario {
    public static void main(String[] args) {
        try (DataOutputStream output = new DataOutputStream(new FileOutputStream("dados.bin"))) {
            output.writeInt(123);
            output.writeDouble(45.67);
            output.writeUTF("Olá, binário!");
            System.out.println("Dados gravados com sucesso!");
        } catch (IOException e) {
            System.err.println("Erro ao gravar os dados: " + e.getMessage());
        }
    }
}
```
- Exemplo - Lendo Dados Binários

```java
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.IOException;

public class LerBinario {
    public static void main(String[] args) {
        try (DataInputStream input = new DataInputStream(new FileInputStream("dados.bin"))) {
            int numero = input.readInt();
            double valor = input.readDouble();
            String texto = input.readUTF();

            System.out.println("Número: " + numero);
            System.out.println("Valor: " + valor);
            System.out.println("Texto: " + texto);
        } catch (IOException e) {
            System.err.println("Erro ao ler os dados: " + e.getMessage());
        }
    }
}
```

## Expressões Lambda

As expressões lambda em Java foram introduzidas no Java 8 como parte da programação funcional e tornam o código mais conciso e legível. Lambdas são essencialmente funções anônimas que podem ser usadas para implementar métodos de interfaces funcionais.

### Estrutura de uma Expressão Lambda

Uma expressão lambda tem a seguinte sintaxe básica:

```java
(parametros) -> { corpo }

```
- Componentes
  * Parâmetros: A lista de entradas para a função. Parênteses podem ser omitidos se houver apenas um parâmetro.
  * Seta (->): Separador entre os parâmetros e o corpo da função.
  * Corpo: O código que será executado. Pode ser uma única expressão ou um bloco de código.

### Interface Funcional

Uma interface funcional é uma interface que possui apenas um método abstrato. Ela pode ter métodos default ou estáticos adicionais, mas somente um método abstrato.

- Exemplo de Interface Funcional

```java
@FunctionalInterface
interface Operacao {
    int executar(int a, int b);
}
```

### Exemplos Práticos

1. Uso Básico com uma Interface Funcional
```java
@FunctionalInterface
interface Operacao {
    int executar(int a, int b);
}

public class LambdaExemplo {
    public static void main(String[] args) {
        // Implementação usando lambda
        Operacao soma = (a, b) -> a + b;
        Operacao multiplicacao = (a, b) -> a * b;

        System.out.println("Soma: " + soma.executar(5, 3)); // Saída: 8
        System.out.println("Multiplicação: " + multiplicacao.executar(5, 3)); // Saída: 15
    }
}
```

2. Com Runnable
   
Runnable é uma interface funcional usada para definir tarefas.

```java
public class LambdaRunnable {
    public static void main(String[] args) {
        // Sem lambda
        Runnable tarefa1 = new Runnable() {
            @Override
            public void run() {
                System.out.println("Tarefa 1 executada");
            }
        };

        // Com lambda
        Runnable tarefa2 = () -> System.out.println("Tarefa 2 executada");

        tarefa1.run();
        tarefa2.run();
    }
}
```

3. Uso com Coleções
   
- Iteração com forEach
```java
import java.util.Arrays;
import java.util.List;

public class LambdaForeach {
    public static void main(String[] args) {
        List<String> nomes = Arrays.asList("João", "Maria", "Pedro");

        // Iteração com lambda
        nomes.forEach(nome -> System.out.println(nome));
    }
}
```

- Filtragem com Stream

```java
import java.util.Arrays;
import java.util.List;

public class LambdaStream {
    public static void main(String[] args) {
        List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5, 6);

        // Filtrando números pares e imprimindo
        numeros.stream()
               .filter(n -> n % 2 == 0)
               .forEach(System.out::println); // Saída: 2 4 6
    }
}
```

- Com Comparator

O Comparator é frequentemente usado para ordenação. Expressões lambda tornam sua implementação mais simples.

```java
import java.util.Arrays;
import java.util.Comparator;
import java.util.List;

public class LambdaComparator {
    public static void main(String[] args) {
        List<String> nomes = Arrays.asList("João", "Maria", "Pedro");

        // Ordenação por tamanho do nome
        nomes.sort((a, b) -> Integer.compare(a.length(), b.length()));

        System.out.println(nomes); // Saída: [João, Maria, Pedro]
    }
}
```

### Métodos de Referência

Os métodos de referência são atalhos para expressões lambda comuns.

- Tipos de Métodos de Referência

1. Referência a um método estático: Classe::metodoEstatico
2. Referência a um método de instância: objeto::metodo
3. Referência a um método de instância de um objeto arbitrário: Classe::metodoInstancia
4. Referência a um construtor: Classe::new

- Exemplo
```java
import java.util.Arrays;
import java.util.List;

public class MetodoReferencia {
    public static void main(String[] args) {
        List<String> nomes = Arrays.asList("João", "Maria", "Pedro");

        // Método de referência em vez de lambda
        nomes.forEach(System.out::println);
    }
}
```

### Benefícios das Expressões Lambda

- Redução do código boilerplate.
- Maior legibilidade, especialmente em operações simples.
- Integração com APIs modernas, como Streams.

## multithreading 
## Padrões de Projetos
