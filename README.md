# eive-java-101-exam-2

1. Por que a execução do Java é realizada em pilha?
   * A pilha é realizada para organizar a execução do código, lembrando o que ainda precisa ser executado.

2. Em programação, qual(is) a(s) utilidade(s) de *debugar* um código?
   * É um método muito eficiente para identificar o que o sistema está fazendo passo a passo.
   * Muito utilizado para identificação de erros.

3. Em Java, qual efeito as exceções possuem sobre o fluxo de execução da pilha? Por que, em muitos casos, o próprio desenvolvedor escreve códigos que intencionalmente lançam essas exceções?
   * Exceções param o fluxo da pilha.
   * Existem vários motivos para utilização de exceções, com certeza o principal motivo é para relatar um problema na execução.

4. O que são e qual(is) a(s) diferença(s) entre as classes `Throwable`, `Exception` e `RuntimeException`?
   * `Throwable` É a superclasse de todos os erros e exceções.
   * `Exception` É a subclasse do Throwable com objetivo de ser uma exceção que o sistema possa querer capturar em algum momento.
   * `RuntimeException` É a subclasse do Exception com o mesmo objetivo da sua super classe, porem é um tipo de exceção não verificada.

5. O que são e qual(is) a(s) diferença(s) entre exceções _checked_ e _unchecked_?
   * `checked` São todas as exeções com base na Exception, exceto a RuntimeException. Este tipo de exceção precisa ser tratado ou declaradas nos métodos.
   * `unchecked` São todas as exceções com base no RuntimeException ou suas subclasses, diferentes das exceções checked, não há necessidade de trata-las.

6. Qual(is) a(s) diferença(s) entre uma exceção e um erro em Java?
   * Ambas as classes são subclasses de Throwable.
   * Exceção são utilizadas para tratar uma rota no sistema, controlado pelo desenvolvedor.
   * Erros são levantados pelo proprio Java e quando ocorrem não devem ser tratados pelo sistema, pois são como ocorrências que não deveriam acontecer.

7. Explique as *keywods* `try`, `catch`, `finally`, `throw` e `throws`.
   * `try` Utilizado para proteger um determinado código, indicando que mesmo que ocorra um problema será executado o bloco de catch e/ou finally.
   * `catch` Utilizado para tratar a exceção lançada, onde é tentado para cada catch encontrar o erro lançado.
   * `finally` Utilizado para executar um bloco de comando mesmo se ocorrer uma exceção no sistema.
   * `throw` Utilizado para lançar uma exceção para o sistema.
   * `throws` Utilizado para delegar a responsabilidade de tratar uma exceção.

8. O que é e para que serve a interface `AutoCloseable`? Como funciona o *try with resources*?
   * A interface `AutoCloseable` possui um unico método `close` para utilizarmos com o recurso `try with resources`
   * `try with resources` é um recurso implementado pelo java para garantir a execução do metodo `close` das classes que implementam o `AutoCloseable` se a mesma for construida.

9. Sobre pacotes, é correto afirmar que:
   1. :white_check_mark: É boa prática nomear os pacotes na estrutura `{site_ao_contrário}.{nome_do_projeto}`;
   2. :white_square_button: Não devemos criar muitos pacotes, pois prejudica a navegação e legibilidade dentro do projeto;
   3. :white_square_button: O uso de pacotes corretamente está diretamente relacionado à qualidade arquitetural de um projeto, já que eles servem para organizá-lo;

10. Explique a(s) diferença(s) entre os modificadores de acesso `private`, `default` `protected` e `public` em Java.
    * `private` Somente a própria classe tem acesso.
    * `default` Todas as classes dentro do mesmo pacote tem acesso
    * `protected` Subclasses tem acesso mesmo em outros pacotes
    * `public` Todos tem acesso.
    
11. Qual a ordem correta dos itens abaixo, considerando a estrutura de um arquivo Java onde há somente uma importação e uma classe vazia? (considere * como _wildcard_)
    ```java
    // 1

    // 2

    // 3
    ```
    1. :white_square_button: `package *;`, `imports *;` e `class * {}`;
    2. :white_check_mark: `package *;`, `import *;` e `class * {}`;
    3. :white_square_button: `pack *;`, `imports *;` e `class * {}`;
    4. :white_square_button: `pack *;`, `import *;` e `class * {}`;

12. Explique o que é FQN (Fully Qualified Name), sua estrutura e como evitamos ter de utilizá-lo sempre que referenciamos uma classe.
    * É o nome completo de uma classe.
    * Sendo o pacote e o nomeda classe
    * Podemos evitar utilizar sempre o FQN com o import.

13. O que é, para que serve, como adquirir e como utilizar um arquivo JAR?
    * É um arquivo compilado do mundo java.
    * Dentro deste arquivos estão os códigos compílados.
    * Utilizamos para compartilhar código como blibliotecas.
    * Podemos importar este arquivo em um projeto para termos acessos as classes compiladas anteriormente

14. O que é o pacote `java.lang` e por que ele é tão essencial para qualquer código Java?
    * É o pacote interno do java que possui muitas classes bases como a String e System.
    * É o unico pacote que não precisa ser feito o import explicito.

15. O que é uma `CharSequence` e qual(is) a(s) diferença(s) entre ela e uma `String`?
    * `CharSequence` é uma interface implementada pela String.
    * Esta interface existe pois existem outras classes que tambem a implementam.
    * Temos a String como classe imutavel, mas tambem temos a StringBuilder que é mutavel
    * Podemos escolher qual utilizar dependendo do cenário para conseguir uma melhor performance.

16. Descreva os métodos da classe String citados abaixo:
    1. `.replace(char oldChar, char newChar);`
       * Função retorna uma string trocando todos os caracteres igual ao oldChar pelo newChar.
    2. `.replaceAll(String regex, String replacement)`;
       * Função retorna uma string trocando o que encontrar no regex pela string replacement.
    3. `.toLowerCase()`;
       * Função retorna uma string trocando todos os carcteres para caixa baixa.
    4. `.concat(String str)`;
       * Função retorna uma string contendo o valor atual da String mais o que passado pelo parametro str.
    5. `.contains(CharSequence s)`;
       * Função retorna um booleano verdadeiro se encontrar o valor de s na String atual.
    6. `.equals(Object anObject)`;
       * Função retorna um booleano verdadeiro se a string passada no parametro possuir o mesmo valor da String Atual.
       * Vale resaltar que outras classes podem ser passadas como parametro e o resultado pode não ser o esperado.
    7. `.equalsIgnoreCase(String anotherString)`;
       * Função retorna um booleano verdadeiro se a string passada no parametro possuir o mesmo valor da String Atual, mas é desconsiderado maisculas e minisculas na comparação
    8. `.isBlank()`;
       * Função retorna um booleano verdadeiro se a string atual estiver vazia.
       * Muita atenção ao usar este metodo com o que deseja, pois uma String com espaços em branco é considerada vazia.
    9. `.matches(String regex)`;
       * Função retorna um booleano verdadeiro se o regex passado por parametro for encontrado na String Atual.

17. Qual(is) a(s) diferença(s) entre `overriding` e `overloading` de métodos? Explique-os dando exemplos úteis da aplicação de ambos.
    * `overriding` É utilizado para estender ou modificar o metodo da superclasse.
      *  Um bom exemplo é a sobrescrita do metodo toString.
      ```java
      public class CPF {
          String CPF;

          public String getCPFFormatado () {
              MaskFormatter mask = new MaskFormatter("###.###.###-##");
              mask.setValueContainsLiteralCharacters(false);
              return mask.valueToString(this.CPF);
          }

          @Override
          public String toString() {
              return this.getCPFFormatado();
          }
      }
      ```
    * `overloading` É o conceito que permite a criação de dois ou mais metodos com o mesmo nome, porem com uma assinatura diferentes.
      * Podemos ter um exemplo na propria classe String
      ```java
      public String substring(int beginIndex) {
          return substring(beginIndex, length());
      }

      public String substring(int beginIndex, int endIndex) {
          int length = length();
          checkBoundsBeginEnd(beginIndex, endIndex, length);
          if (beginIndex == 0 && endIndex == length) {
              return this;
          }
          int subLen = endIndex - beginIndex;
          return isLatin1() ? StringLatin1.newString(value, beginIndex, subLen)
                            : StringUTF16.newString(value, beginIndex, subLen);
      }
      ```

18. Todas as classes Java herdam a classe `Object`, que possui três métodos comumente sobrescritos: `.equals(Object obj)`, `.hashCode()` e `.toString()`. Explique a utilidade de cada um deles.
    * `.equals(Object obj)` É a forma como dizemos que um objeto mesmo com uma referencia diferente é igual a outro objeto.
    * `.hashCode()` Explicando de uma forma simploria, é como definimos que uma lista deste objeto será catalogada, com este método aumentamos a performance consideravelmente ao realizar buscas em coleções.
    * `.toString()` O java oferece uma implementação padrão para o metodo toString, mas podemos sobrescreve-lo para retornar dados de forma que fazem mais sentido para classe.

19. Qual(is) das opções expressa(m) uma sintaxe correta para criar um *array* de inteiros?
    1. :white_square_button: `int[] inteiros = []`;
    2. :white_square_button: `int[] inteiros = new int[]`;
    3. :white_square_button: `int[] inteiros = new int[]{999}`;
    4. :white_check_mark: `int[] inteiros = new int[1]`;
    5. :white_square_button: `int[] inteiros = {999}`;
    6. :white_square_button: `int... inteiros = {999}`;

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
    * No primeiro caso estamos acessando uma variavel primaria que é inicializada com o valor 0
    * No segundo estamos acessando um atributo da classe pessoa, sendo este atributo um objeto o mesmo tambem precisa ser instanciado, como não foi é apresentado uma exceção.

21. Sobre *type casting*, explique:
    1. *Cast* implícito;
       * Quando o proprio java se encarrega de realizar a conversão do valor.
    2. *Cast* explícito;
       * Quando temos que informar manualmente para qual tipo de dado ou objeto queremos converter.
    3. `ClassCastException`;
       * Erro lançado quando tentamos converter uma classe explicitamente e a conversão não pode ser realizada de forma coerente.

22. Explique o que é e como utilizar o `autoboxing` e o `unboxing`.
    * `autoboxing` É a conversão do dado primitivo para uma classe wrapper.
    * `unboxing` É a conversão da classe wrapper para seu tipo primitivo.

23. É possível, no momento em que é executada uma aplicação em Java, passar argumentos para a mesma. Como isso pode ser feito e como podemos acessar esses argumentos dentro do código (no método `main()`)?
    * Qualquer informação passada na linha de comando na chamada de um programa java, após seu nome é um argumento, sendo separados por espaço.
    * Sempre ao declarar a classe main passamos um arrays de string comumente chamado de args, podemos acessar os argumentos trabalhando como uma lista de array de strings.

24. Ao utilizar um `array`, o tamanho máximo do mesmo deve ser declarado. Por que isso não acontece quando utilizamos `ArrayList`? E qual é o limite do que essa estrutura pode armazenar?
    * Na classe ArrayList existe um tamanho pré-definido e quando alcançado é feito a geração de um novo array repassando todos os itens adicionados e aumentando o tamanho do novo array.
    * O limite é o seu equipamento :D

25. Por que, no geral, o `ArrayList` costuma ser mais utilizado que `arrays` em Java?
    * Arrays tendem a ser trabalhados com lista fixa, pois podemos controlar seu tamanho na criação do mesmo.
    * ArrayLista possui uma facilidade para adicionar e remover itens, que é o caso mais comun no dia a dia, tornando muito mais utilizado.

26. Por que sempre devemos optar pelo uso de `Generics` ao declarar um `ArrayList` (declaração no formato `ArrayList<{tipo}>`)?
    * Trabalhando com Generics estamos fazendo uma lista com uma certa assinatura, assim uma lista de String terá somente String adiciona.

27. Explique os métodos `.add(E e)` e `.contains(Object o)`, da interface `Collection`?
    * `.add(E e)` Método utilizado para incluir um novo item a coleção.
    * `.contains(Object o)` Método utilizado para verificar se o Item passado por parâmetro existe dentro da coleção.

28. Explique as interfaces `Comparator<{tipo}>` e `Comparable<{tipo}>`.
    * `Comparator` Interface utilizada para criar ordenações personalizadas, podendo criar varias para uma mesma classe.
    * `Comparable` Interface que define a operação de comparação do próprio objeto com outro, usado para definir a ordem natural dos elementos de uma coleção.

29. Qual(is) a(s) diferença(s) entre as interfaces `List` e `Set`?
    * `List` Permite a adição ordenada de itens e valores duplicados, tambem é possível acessar os itens através de um indice.
    * `Set` Não há garantia de posição na adição de um item, tambem não se pode incluir itens duplicados e não consiguimos acessar seus itens através de um indice.

30. Como funciona a implementação `HashSet`? Qual a relação dela com o método `.hashCode()`?
    * A classe HashSet implementa a interface Set , apoiada por uma tabela hash que é, na verdade, uma instância HashMap.
    * O método hashCode é o que garante a unicidade das coleções set.

31. Por que é recomendado que o *overriding* dos métodos `.equals(Object obj)` e `.hashCode()` seja realizado sempre em pares (ao sobreescrever um, o outro também deve ser sobreescrito)?
    * Para garantir a unicidade do objeto, pois ao utilizar o método `equals` o método `hashCode` é usado para validar se o objeto é o mesmo.

32. Qual é a estrutura de uma expressão *lambda*, em Java? Explique e dê um exemplo, em código.
    * Podemos utilizar a expressão lambda passando um ou mais argumentos e podemos dizer o que fazer com estes argumentos.
    * Quando o argumento é unico não precisamos informar seu tipo e não ha necessidade de parenteses.
    * Quando a instrução chamada é uma só não há necessidade das chaves e nem o return.
    ```java
    Set<String> lista = new HashSet<String>();
    lista.add("Primeiro");
    lista.add("Segundo");
    lista.add("Terceiro");
    lista.forEach((String s) -> {
        System.out.println(s);
    });
    ```
    Podemos neste caso resumir a expressão lambda.
    ```java
    Set<String> lista = new HashSet<String>();
    lista.add("Primeiro");
    lista.add("Segundo");
    lista.add("Terceiro");
    lista.forEach(s -> System.out.println(s));
    ```

33. Qual é a estrutura de uma expressão *lambda* utilizando *method reference*, em Java? Explique e dê um exemplo, em código.
    * è uma forma ainda mais resumida para utilizar o lambda, informamos a classe e o metodo que queremos utilizar.
    ```java
    Set<String> lista = new HashSet<String>();
    lista.add("Primeiro");
    lista.add("Segundo");
    lista.add("Terceiro");
    lista.forEach(System.out::println);
    ```

34. Qual é a estrutura de uma `stream`, em Java? Explique e dê um exemplo, em código.
    * É a forma implementada pelo java para tratar coleções de forma mais simple e eficaz.
    * Podemos por exemplo preeencher uma lista filtrar com alguma condição, ordena-la e retornar o primeiro item.
    ```java
    List<String> lista = new ArrayList<String>();
    lista.add("Sucuri");
    lista.add("Leão");
    lista.add("Sapo");
    System.out.println(lista.stream().filter(s -> s.startsWith("S")).sorted().findFirst());
    ```

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
    * Está faltando um comando para validar a operação realizada e retornar se o esperado foi atendido ou não
    * Existem varias formas de fazer isso neste caso o mais indicado seria o assertEquals

36. Como é aplicado o TDD? Qual(is) benefício(s) ele traz e quando devemos utilizá-lo?
    * A base do TDD é realizar o teste antes da programação.
    * Programando os casos de testes a serem protegidos, podemos fazer a programação de forma mais segura.
    * Refatorações podem serem feitas sem problemas.

37. Quais métodos podemos utilizar para validar o lançamento de exceções em testes automatizados?
    * Podemos utilizar o comando assertThrows para capturar a exceção e comparar se é a esperada.
