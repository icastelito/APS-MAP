# RPGFactoryMethod README

## Descri��o

Este projeto � uma implementa��o do padr�o de design Factory Method em C# dentro do contexto de um jogo de RPG. Ele define uma estrutura para criar diferentes tipos de desafios (como monstros e armadilhas) sem acoplar o c�digo do jogo �s classes concretas desses desafios. O c�digo demonstra como usar classes abstratas e heran�a para criar uma solu��o extens�vel e modular.

## Estrutura do C�digo

O c�digo � composto por v�rias classes organizadas da seguinte forma:

### Classes Abstratas

1. **Desafio**:
   - Classe base abstrata que representa um desafio no jogo.
   - Cont�m uma propriedade abstrata `Nome` e um m�todo abstrato `Executar`.

2. **FabricaDesafio**:
   - Classe base abstrata para as f�bricas de desafios.
   - Define um m�todo abstrato `CriarDesafio` que retorna um objeto do tipo `Desafio`.

### Classes Concretas

1. **Monstro**:
   - Subclasse concreta de `Desafio`.
   - Implementa a propriedade `Nome` e o m�todo `Executar`, que exibe uma mensagem indicando que um monstro apareceu.

2. **Armadilha**:
   - Subclasse concreta de `Desafio`.
   - Implementa a propriedade `Nome` e o m�todo `Executar`, que exibe uma mensagem indicando que uma armadilha foi acionada.

3. **FabricaMonstro**:
   - Subclasse concreta de `FabricaDesafio`.
   - Implementa o m�todo `CriarDesafio`, retornando uma nova inst�ncia de `Monstro`.

4. **FabricaArmadilha**:
   - Subclasse concreta de `FabricaDesafio`.
   - Implementa o m�todo `CriarDesafio`, retornando uma nova inst�ncia de `Armadilha`.

### Classe Principal

1. **Program**:
   - Classe principal que cont�m o m�todo `Main`, ponto de entrada do programa.
   - Cria inst�ncias das f�bricas de desafios (`FabricaMonstro` e `FabricaArmadilha`), utiliza essas f�bricas para criar desafios espec�ficos, e executa esses desafios, exibindo mensagens no console.

## Passo a Passo

1. **Definir a classe base Desafio**:
   - `Desafio` � uma classe abstrata que cont�m uma propriedade abstrata `Nome` e um m�todo abstrato `Executar`.

2. **Criar subclasses concretas de Desafio**:
   - `Monstro` e `Armadilha` s�o subclasses concretas de `Desafio` que implementam a propriedade `Nome` e o m�todo `Executar` com mensagens espec�ficas.

3. **Definir a classe base FabricaDesafio**:
   - `FabricaDesafio` � uma classe abstrata com um m�todo abstrato `CriarDesafio` que retorna um objeto do tipo `Desafio`.

4. **Criar subclasses concretas de FabricaDesafio**:
   - `FabricaMonstro` e `FabricaArmadilha` s�o subclasses concretas de `FabricaDesafio` que implementam o m�todo `CriarDesafio` para retornar inst�ncias de `Monstro` e `Armadilha`, respectivamente.

5. **Implementar a classe Program**:
   - No m�todo `Main`, instanciar `FabricaMonstro` e `FabricaArmadilha`.
   - Utilizar essas inst�ncias para criar objetos `Monstro` e `Armadilha`.
   - Chamar o m�todo `Executar` em cada um desses objetos para exibir as mensagens no console.

## Execu��o

Para executar o programa, siga os passos abaixo:

1. Compile o c�digo utilizando um compilador C# (por exemplo, atrav�s do Visual Studio ou linha de comando com `csc`).
2. Execute o programa compilado. Voc� ver� as seguintes mensagens no console:

```
Desafio criado: Monstro
Um monstro apareceu! Prepare-se para a batalha!
Desafio criado: Armadilha
Voc� caiu em uma armadilha! Tente escapar!
```

Essas mensagens indicam que os desafios foram criados e executados corretamente.

## Conclus�o

Este projeto demonstra o uso do padr�o Factory Method para criar uma estrutura de jogo extens�vel, onde novos tipos de desafios podem ser adicionados facilmente sem modificar o c�digo existente. Isso promove um design limpo e modular, seguindo os princ�pios de programa��o orientada a objetos.