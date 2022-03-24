# eive-java-101-exam-2

1. Por que a execução do Java é realizada em pilha?

2. Em programação, qual(is) a(s) utilidade(s) de *debugar* um código?

3. Em Java, qual efeito as exceções possuem sobre o fluxo de execução da pilha? Por que, em muitos casos, o próprio desenvolvedor escreve códigos que intencionalmente lançam essas exceções?

4. O que são e qual(is) a(s) diferença(s) entre as classes `Throwable`, `Exception` e `RuntimeException`?

5. O que são e qual(is) a(s) diferença(s) entre exceções _checked_ e _unchecked_?

6. Qual(is) a(s) diferença(s) entre uma exceção e um erro em Java?

7. Explique as *keywods* `try`, `catch`, `finally`, `throw` e `throws`.

8. O que é e para que serve a interface `AutoCloseable`? Como funciona o *try with resources*?

9. Sobre pacotes, é correto afirmar que:
   1. É boa prática nomear os pacotes na estrutura `{site_ao_contrário}.{nome_do_projeto}`;
   2. Não devemos criar muitos pacotes, pois prejudica a navegação e legibilidade dentro do projeto;
   3. O uso de pacotes corretamente está diretamente relacionado à qualidade arquitetural de um projeto, já que eles servem para organizá-lo;

2. Explique a(s) diferença(s) entre os modificadores de acesso `private`, `default` `protected` e `public` em Java.

3. Qual a ordem correta dos itens abaixo, considerando a estrutura de um arquivo Java onde há somente uma importação e uma classe vazia? (considere * como _wildcard_)
   ```java
   // 1

   // 2

   // 3
   ```
   1. `package *;`, `imports *;` e `class * {}`;
   2. `package *;`, `import *;` e `class * {}`;
   3. `pack *;`, `imports *;` e `class * {}`;
   4. `pack *;`, `import *;` e `class * {}`;

4. Explique o que é FQN (Fully Qualified Name), sua estrutura e como evitamos ter de utilizá-lo sempre que referenciamos uma classe.

13. O que é, para que serve, como adquirir e como utilizar um arquivo JAR?

14. O que é o pacote `java.lang` e por que ele é tão essencial para qualquer código Java?

15. O que é uma `CharSequence` e qual(is) a(s) diferença(s) entre ela e uma `String`?

16. Descreva os métodos da classe String citados abaixo:
    1. `.replace(char oldChar, char newChar);`
    2. `.replaceAll(String regex, String replacement)`;
    3. `.toLowerCase()`;
    4. `.concat(String str)`;
    5. `.contains(CharSequence s)`;
    6. `.equals(Object anObject)`;
    7. `.equalsIgnoreCase(String anotherString)`;
    8. `.isBlank()`;
    9. `.matches(String regex)`;

17. Qual(is) a(s) diferença(s) entre `overriding` e `overloading` de métodos? Explique-os dando exemplos úteis da aplicação de ambos.

18. Todas as classes Java herdam a classe `Object`, que possui três métodos comumente sobrescritos: `.equals(Object obj)`, `.hashCode()` e `.toString()`. Explique a utilidade de cada um deles.

19. Qual(is) das opções expressa(m) uma sintaxe correta para criar um *array* de inteiros?
    1. `int[] inteiros = []`;
    2. `int[] inteiros = new int[]`;
    3. `int[] inteiros = new int[]{999}`;
    4. `int[] inteiros = new int[1]`;
    5. `int[] inteiros = {999}`;
    6. `int... inteiros = {999}`;

20. Por que o primeiro código abaixo exibe o valor `0` no terminal, mas o segundo produz uma exceção?
    ```java
    // código 1
    class App {
        public static void main(String... args) {
            int[] inteiros = new int[1];
            System.out.println(inteiros[0]);
        }
    }
    ```
    ```java
    // código 2
    class Pessoa {
        Endereco endereco;
    }

    class Endereco {
        String cep;
    }

    class App {
        public static void main(String... args) {
            Pessoa[] pessoas = new Pessoa[1];
            System.out.println(pessoas[0].endereco.cep);
        }
    }
    ```

21. Sobre *type casting*, explique:
    1. *Cast* implícito;
    2. *Cast* explícito;
    3. `ClassCastException`;

22. Explique o que é e como utilizar o `autoboxing` e o `unboxing`.

23. É possível, no momento em que é executada uma aplicação em Java, passar argumentos para a mesma. Como isso pode ser feito e como podemos acessar esses argumentos dentro do código (no método `main()`)?

24. Ao utilizar um `array`, o tamanho máximo do mesmo deve ser declarado. Por que isso não acontece quando utilizamos `ArrayList`? E qual é o limite do que essa estrutura pode armazenar?

25. Por que, no geral, o `ArrayList` costuma ser mais utilizado que `arrays` em Java?

26. Por que sempre devemos optar pelo uso de `Generics` ao declarar um `ArrayList` (declaração no formato `ArrayList<{tipo}>`)?

27. Explique os métodos `.add(E e)` e `.contains(Object o)`, da interface `Collection`?

28. Explique as interfaces `Comparator<{tipo}>` e `Comparable<{tipo}>`.

29. Qual(is) a(s) diferença(s) entre as interfaces `List` e `Set`?

30. Como funciona a implementação `HashSet`? Qual a relação dela com o método `.hashCode()`?

31. Por que é recomendado que o *overriding* dos métodos `.equals(Object obj)` e `.hashCode()` seja realizado sempre em pares (ao sobreescrever um, o outro também deve ser sobreescrito)?

32. Qual é a estrutura de uma expressão *lambda*, em Java? Explique e dê um exemplo, em código.

33. Qual é a estrutura de uma expressão *lambda* utilizando *method reference*, em Java? Explique e dê um exemplo, em código.

34. Qual é a estrutura de uma `stream`, em Java? Explique e dê um exemplo, em código.

35. O que falta no código abaixo para ser considerado um teste útil?
    ```java
    // package & imports
    class CalculadoraTest {

    	@Test
    	public void deveSomarDoisValores() {
            Calculadora calculadora = new Calculadora();
            int resultado = calculadora.somar(2, 2);
    	}

    }
    ```

36. Como é aplicado o TDD? Qual(is) benefício(s) ele traz e quando devemos utilizá-lo?

37. Quais métodos podemos utilizar para validar o lançamento de exceções em testes automatizados?

