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

### Programação Orientada a Objetos
### Maniputaçao de Strings
### Coleções e Arrays
### Entrada e Saida de dados
### Expressões Lambda
### multithreading 
### Padrões de Projetos
