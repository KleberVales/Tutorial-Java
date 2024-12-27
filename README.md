# Tutorial-Java

### Fundamentos da linguagem java
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
   
### Sintaxe do Java
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
7. Comentários
Os comentários são ignorados pelo compilador e ajudam a documentar o código.

Linha única: // Este é um comentário
Múltiplas linhas:
```java

/* Este é um
   comentário de várias linhas */

```

### Programação Orientada a Objetos
### Maniputaçao de Strings
### Coleções e Arrays
### Entrada e Saida de dados
### Expressões Lambda
### multithreading 
### Padrões de Projetos
