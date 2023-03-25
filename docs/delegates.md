# Delegates em C#

Delegates são uma maneira de permitir que métodos sejam tratados como [objetos](objeto.md) em C#. Eles são úteis para a criação de **callbacks**, **eventos** e outras funcionalidades avançadas.

De maneira simples, podemos dizer que um delegate é um tipo que *representa um método* com um determinado conjunto de parâmetros e um tipo de retorno específico. Ele é uma espécie de ponteiro para um método que pode ser passado como argumento para outro método.

## Criando um delegate
Exemplo de como criar um delegate em C#:

```csharp
public delegate void MeuDelegate(string mensagem);
```

O código acima define um novo tipo chamado `MeuDelegate` que pode ser usado para representar qualquer método que aceite uma string como parâmetro e não tenha retorno.

## Usando um delegate

Agora que temos um delegate, podemos usá-lo para criar referências a métodos específicos. Aqui está um exemplo:

```csharp
public class ExemploDelegates {
    public static void MeuMetodo(string mensagem) {
        Console.WriteLine(mensagem);
    }
    
    public static void Main() {
        MeuDelegate meuDelegate = new MeuDelegate(MeuMetodo);
        meuDelegate("Olá, mundo!");
    }
}
```

O código acima define uma classe `ExemploDelegates` que tem um método MeuMetodo que aceita uma string como parâmetro e a imprime no console. Em seguida, o método **Main** cria uma nova instância do delegate `MeuDelegate` e a associa ao método MeuMetodo. Em seguida, o delegate é chamado com a string *"Olá, mundo!"* como argumento.

## Multicast delegates

Em C#, também é possível criar delegates **multicast**, que são delegates que podem apontar para vários métodos ao mesmo tempo. Para criar um delegate multicast, basta usar o operador **+** para concatenar vários delegates. Aqui está um exemplo:

```csharp
public class ExemploMulticastDelegates {
    public static void MeuMetodo1(string mensagem) {
        Console.WriteLine("Método 1: " + mensagem);
    }
    
    public static void MeuMetodo2(string mensagem) {
        Console.WriteLine("Método 2: " + mensagem);
    }
    
    public static void Main() {
        MeuDelegate meuDelegate = new MeuDelegate(MeuMetodo1);
        meuDelegate += new MeuDelegate(MeuMetodo2);
        meuDelegate("Olá, mundo!");
    }
}
```

O código acima define uma classe `ExemploMulticastDelegates` que tem dois métodos `MeuMetodo1` e `MeuMetodo2`. Em seguida, o método **Main** cria uma nova instância do delegate `MeuDelegate` e a associa aos métodos `MeuMetodo1` e `MeuMetodo2` usando o operador +. Quando o delegate é chamado com a string "Olá, mundo!" como argumento, ambos os métodos são executados em ordem.