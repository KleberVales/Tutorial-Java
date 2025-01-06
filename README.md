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
   No Java, os tipos de variáveis podem ser divididos em tipos primitivos e referências de objetos. Aqui está um resumo detalhado:

   - Tipos Primitivos
     São os tipos de dados básicos, que armazenam valores diretamente na memória. Existem 8 tipos primitivos no Java:

     a) Numéricos Inteiros
     
     | Tipo |	Tamanho (bits)	| Valor Mínimo	| Valor Máximo |
     |------|-----------------|---------------|--------------|
     |byte	| 8	              |-128	          |    127       |
     | short|	16	            | -32,768	      | 32,767       |
     |  int	|  32	            |-2,147,483,648	| 2,147,483,647|
     | long	| 64	            |-9,223,372,036,854,775,808	| 9,223,372,036,854,775,807|

     b) Numéricos de Ponto Flutuante

     | Tipo	| Tamanho (bits)	| Valor Mínimo	| Valor Máximo	|Precisão Decimal |
     |------|-----------------|---------------|---------------|-----------------|
     |float	| 32	            |~1.4E-45       |	~3.4E+38      |	~6-7  dígitos|
     |double|64             	|~4.9E-324      |	~1.8E+308	    |~15 dígitos

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

### Thread

Trabalhar com Threads em Java permite que você realize multitarefas em um programa, ou seja, execute várias tarefas simultaneamente. Isso é útil em aplicações que exigem desempenho, como servidores, jogos ou sistemas com operações complexas.

1. O Que é Uma Thread?

- Uma Thread é a menor unidade de processamento que pode ser gerenciada pelo sistema operacional.
- Em Java, você pode criar e gerenciar threads para realizar tarefas concorrentes.

2. Criando Threads em Java

- Extender a Classe Thread

Você pode criar uma classe que estenda a classe Thread e sobrescrever o método run().

Exemplo

```java
class MinhaThread extends Thread {
    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Executando thread: " + i);
            try {
                Thread.sleep(1000); // Pausa de 1 segundo
            } catch (InterruptedException e) {
                System.out.println("Thread interrompida");
            }
        }
    }
}

public class ThreadExemplo {
    public static void main(String[] args) {
        MinhaThread thread1 = new MinhaThread();
        MinhaThread thread2 = new MinhaThread();

        thread1.start();
        thread2.start();
    }
}

```

- Implementar a Interface Runnable

Outra abordagem é implementar a interface Runnable e passar a instância para um objeto Thread.

Exemplo

```java
class MinhaRunnable implements Runnable {
    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Executando Runnable: " + i);
            try {
                Thread.sleep(1000); // Pausa de 1 segundo
            } catch (InterruptedException e) {
                System.out.println("Runnable interrompido");
            }
        }
    }
}

public class RunnableExemplo {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MinhaRunnable());
        Thread thread2 = new Thread(new MinhaRunnable());

        thread1.start();
        thread2.start();
    }
}

```

- Usando Expressões Lambda

Como Runnable é uma interface funcional, você pode usar expressões lambda para simplificar o código.

Exemplo

```java
public class LambdaExemplo {
    public static void main(String[] args) {
        Thread thread = new Thread(() -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Executando Lambda: " + i);
                try {
                    Thread.sleep(1000); // Pausa de 1 segundo
                } catch (InterruptedException e) {
                    System.out.println("Lambda interrompido");
                }
            }
        });

        thread.start();
    }
}

```

3. Métodos Importantes da Classe Thread

| Método |	Descrição |
|--------|------------|
| start()	| Inicia a execução da thread. |
| run()	| Contém o código que será executado pela thread. |
| sleep(long millis)	| Faz a thread "dormir" por um tempo especificado. |
| join()	| Faz a thread atual aguardar a conclusão de outra. |
| isAlive()	| Verifica se a thread ainda está em execução. |
| setPriority(int priority)	| Define a prioridade da thread. |
| interrupt()	| Interrompe uma thread em execução. |

### Multithreading

Multithreading em Java é uma técnica que permite que várias partes de um programa sejam executadas simultaneamente. Isso é feito criando e gerenciando múltiplas threads, que são pequenas unidades de execução dentro de um processo.

#### O Que é Multithreading?

- Thread: Uma thread é a menor unidade de execução em um programa.
- Multithreading: Refere-se à execução simultânea de múltiplas threads em um único processo. Cada thread pode executar uma tarefa diferente ao mesmo tempo.

#### Vantagens do Multithreading

- Melhor desempenho em sistemas multicore.
- Maior responsividade em aplicações, como interfaces gráficas.
- Permite a execução de tarefas simultâneas, como download e processamento.

#### Estrutura de Threads em Java

1. Classe Thread

Java fornece a classe Thread para criar e gerenciar threads.

2. Interface Runnable
   
A interface Runnable é usada para definir o código que será executado por uma thread.

#### Criando Threads em Java

1. Extender a Classe Thread

Uma maneira simples de criar uma thread é extender a classe Thread e sobrescrever o método run().

Exemplo
```java
class MinhaThread extends Thread {
    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Executando thread: " + i);
            try {
                Thread.sleep(500); // Pausa de 500ms
            } catch (InterruptedException e) {
                System.out.println("Thread interrompida");
            }
        }
    }
}

public class MultithreadingExemplo {
    public static void main(String[] args) {
        MinhaThread thread1 = new MinhaThread();
        MinhaThread thread2 = new MinhaThread();

        thread1.start();
        thread2.start();
    }
}
```

2. Implementar a Interface Runnable

Outra abordagem é implementar a interface Runnable, que permite maior flexibilidade.

Exemplo
```java

class MinhaRunnable implements Runnable {
    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Executando Runnable: " + i);
            try {
                Thread.sleep(500); // Pausa de 500ms
            } catch (InterruptedException e) {
                System.out.println("Runnable interrompido");
            }
        }
    }
}

public class RunnableExemplo {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MinhaRunnable());
        Thread thread2 = new Thread(new MinhaRunnable());

        thread1.start();
        thread2.start();
    }
}

```

3. Usando Expressões Lambda

Como a interface Runnable é funcional, você pode usar expressões lambda para simplificar o código.

Exemplo

```java
public class LambdaExemplo {
    public static void main(String[] args) {
        Thread thread = new Thread(() -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Executando Lambda: " + i);
                try {
                    Thread.sleep(500);
                } catch (InterruptedException e) {
                    System.out.println("Lambda interrompido");
                }
            }
        });

        thread.start();
    }
}
```

#### Sincronização de Threads

Quando várias threads acessam o mesmo recurso, pode haver problemas de consistência. A sincronização é usada para evitar isso.

1. Bloco synchronized

Exemplo
```java
class Contador {
    private int valor = 0;

    public synchronized void incrementar() {
        valor++;
    }

    public int getValor() {
        return valor;
    }
}

public class SincronizacaoExemplo {
    public static void main(String[] args) {
        Contador contador = new Contador();

        Thread thread1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                contador.incrementar();
            }
        });

        Thread thread2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                contador.incrementar();
            }
        });

        thread1.start();
        thread2.start();

        try {
            thread1.join();
            thread2.join();
        } catch (InterruptedException e) {
            System.out.println("Thread interrompida");
        }

        System.out.println("Valor final: " + contador.getValor()); // Saída: 2000
    }
}
```

2. Usando ReentrantLock

O ReentrantLock fornece controle mais granular sobre os bloqueios.

Exemplo
```java
import java.util.concurrent.locks.ReentrantLock;

class ContadorLock {
    private int valor = 0;
    private final ReentrantLock lock = new ReentrantLock();

    public void incrementar() {
        lock.lock();
        try {
            valor++;
        } finally {
            lock.unlock();
        }
    }

    public int getValor() {
        return valor;
    }
}

public class LockExemplo {
    public static void main(String[] args) {
        ContadorLock contador = new ContadorLock();

        Thread thread1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                contador.incrementar();
            }
        });

        Thread thread2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                contador.incrementar();
            }
        });

        thread1.start();
        thread2.start();

        try {
            thread1.join();
            thread2.join();
        } catch (InterruptedException e) {
            System.out.println("Thread interrompida");
        }

        System.out.println("Valor final: " + contador.getValor()); // Saída: 2000
    }
}
```

#### Executor Framework

O pacote java.util.concurrent fornece uma maneira mais eficiente de gerenciar threads, usando o Executor Framework.

Exemplo com ExecutorService

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class ExecutorExemplo {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(2);

        Runnable tarefa1 = () -> System.out.println("Executando tarefa 1");
        Runnable tarefa2 = () -> System.out.println("Executando tarefa 2");

        executor.submit(tarefa1);
        executor.submit(tarefa2);

        executor.shutdown(); // Finaliza o executor
    }
}
```


## Padrões de Projetos

Design Patterns são soluções reutilizáveis para problemas comuns no desenvolvimento de software. Eles ajudam a criar sistemas flexíveis, escaláveis e de fácil manutenção. Java, sendo uma linguagem amplamente usada, possui suporte nativo para implementar vários padrões de design.

Abaixo, estão os principais tipos de design patterns e exemplos práticos em Java:

### Categorias de Design Patterns

1. Creational (Criação): Focados na criação de objetos.

- Singleton
- Factory Method
- Abstract Factory
- Builder
- Prototype

2. Structural (Estrutural): Lidam com a composição de classes e objetos.

- Adapter
- Bridge
- Composite
- Decorator
- Facade
- Flyweight
- Proxy

3. Behavioral (Comportamental): Focados na comunicação entre objetos.

- Chain of Responsibility
- Command
- Interpreter
- Iterator
- Mediator
- Memento
- Observer
- State
- Strategy
- Template Method
- Visitor

### Exemplos de Design Patterns

1. Singleton Pattern (Creational)

Garante que uma classe tenha apenas uma instância e fornece um ponto global de acesso a ela.

Exemplo
```java

public class Singleton {
    private static Singleton instanciaUnica;

    private Singleton() {
        // Construtor privado
    }

    public static Singleton getInstance() {
        if (instanciaUnica == null) {
            instanciaUnica = new Singleton();
        }
        return instanciaUnica;
    }
}

public class TesteSingleton {
    public static void main(String[] args) {
        Singleton obj1 = Singleton.getInstance();
        Singleton obj2 = Singleton.getInstance();

        System.out.println(obj1 == obj2); // Saída: true
    }
}

```

2. Factory Method (Creational)

Define uma interface para criar objetos, mas permite que subclasses decidam qual classe instanciar.

Exemplo

```java
abstract class Produto {
    public abstract void usar();
}

class ProdutoA extends Produto {
    @Override
    public void usar() {
        System.out.println("Usando Produto A");
    }
}

class ProdutoB extends Produto {
    @Override
    public void usar() {
        System.out.println("Usando Produto B");
    }
}

abstract class Criador {
    public abstract Produto criarProduto();
}

class CriadorA extends Criador {
    @Override
    public Produto criarProduto() {
        return new ProdutoA();
    }
}

class CriadorB extends Criador {
    @Override
    public Produto criarProduto() {
        return new ProdutoB();
    }
}

public class TesteFactoryMethod {
    public static void main(String[] args) {
        Criador criadorA = new CriadorA();
        Produto produtoA = criadorA.criarProduto();
        produtoA.usar();

        Criador criadorB = new CriadorB();
        Produto produtoB = criadorB.criarProduto();
        produtoB.usar();
    }
}

```

3. Observer Pattern (Behavioral)

Define uma dependência um-para-muitos entre objetos, de modo que, quando um objeto muda de estado, todos os seus dependentes são notificados.

Exemplo

```java

import java.util.ArrayList;
import java.util.List;

interface Observador {
    void atualizar(String mensagem);
}

class Observado {
    private List<Observador> observadores = new ArrayList<>();

    public void adicionarObservador(Observador observador) {
        observadores.add(observador);
    }

    public void notificarObservadores(String mensagem) {
        for (Observador observador : observadores) {
            observador.atualizar(mensagem);
        }
    }
}

class Cliente implements Observador {
    private String nome;

    public Cliente(String nome) {
        this.nome = nome;
    }

    @Override
    public void atualizar(String mensagem) {
        System.out.println(nome + " recebeu: " + mensagem);
    }
}

public class TesteObserver {
    public static void main(String[] args) {
        Observado loja = new Observado();

        Cliente cliente1 = new Cliente("Alice");
        Cliente cliente2 = new Cliente("Bob");

        loja.adicionarObservador(cliente1);
        loja.adicionarObservador(cliente2);

        loja.notificarObservadores("Nova promoção disponível!");
    }
}

```

4. Strategy Pattern (Behavioral)

Define uma família de algoritmos, encapsula cada um deles e os torna intercambiáveis.

Exemplo
```java
interface EstrategiaPagamento {
    void pagar(int valor);
}

class PagamentoCartaoCredito implements EstrategiaPagamento {
    @Override
    public void pagar(int valor) {
        System.out.println("Pagamento de " + valor + " realizado com cartão de crédito.");
    }
}

class PagamentoPaypal implements EstrategiaPagamento {
    @Override
    public void pagar(int valor) {
        System.out.println("Pagamento de " + valor + " realizado com PayPal.");
    }
}

class ContextoPagamento {
    private EstrategiaPagamento estrategia;

    public void setEstrategia(EstrategiaPagamento estrategia) {
        this.estrategia = estrategia;
    }

    public void executarPagamento(int valor) {
        estrategia.pagar(valor);
    }
}

public class TesteStrategy {
    public static void main(String[] args) {
        ContextoPagamento contexto = new ContextoPagamento();

        contexto.setEstrategia(new PagamentoCartaoCredito());
        contexto.executarPagamento(100);

        contexto.setEstrategia(new PagamentoPaypal());
        contexto.executarPagamento(200);
    }
}
```

5. Decorator Pattern (Structural)

Adiciona responsabilidades a um objeto dinamicamente.

Exemplo
```
java
interface Componente {
    void executar();
}

class ComponenteBase implements Componente {
    @Override
    public void executar() {
        System.out.println("Executando componente base");
    }
}

class Decorador implements Componente {
    private Componente componente;

    public Decorador(Componente componente) {
        this.componente = componente;
    }

    @Override
    public void executar() {
        componente.executar();
        System.out.println("Executando funcionalidade adicional");
    }
}

public class TesteDecorator {
    public static void main(String[] args) {
        Componente componente = new ComponenteBase();
        Componente componenteDecorado = new Decorador(componente);

        componente.executar(); // Apenas o componente base
        componenteDecorado.executar(); // Base + funcionalidade adicional
    }
}

```



