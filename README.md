# Trabalho Final – Engenharia de Software II
## Rafael Devantier Neuenfeldt

##  Padrão de Projeto: Abstract Factory

O padrão **Abstract Factory** é um padrão **criacional** que fornece uma interface para criar **famílias de objetos relacionados ou dependentes** sem especificar suas classes concretas.

Ele encapsula um conjunto de fábricas individuais com um tema comum, permitindo que o código cliente utilize **interfaces abstratas** para trabalhar com diferentes produtos **compatíveis entre si**, de maneira independente.

---

##  Problema

No exemplo vamos tratar de um carro, mas **não sabemos se o cliente espera um carro popular ou de luxo**. Se o código cliente utilizar diretamente `new CarroPopular()` ou `new CarroLuxo()`, isso cria uma forte necessidade do cliente interagir com as classes concretas, passando grande parte da responsabilidade para ele.
Além disso, se for necessário trocar a lógica de construção ou alterar a variante utilizada, o código cliente também precisará ser modificado.

---

##  Solução com Abstract Factory

Com Abstract Factory, o processo de criação é **abstraído** através de interfaces. O cliente não sabe (nem precisa saber) o tipo exato de objeto que está sendo instanciado — ele apenas interage com interfaces.

### Componentes principais:

- `ICarro` — Interface para os produtos (`CarroPopular`, `CarroLuxo`)
- `ICarroFactory` — Interface da fábrica abstrata
- `CarroPopularFactory`, `CarroLuxoFactory` — Fábricas concretas
- Código cliente — Usa apenas `ICarroFactory` e `ICarro`
---
## Pontos positivos 
- O cliente não precisa de contato direto com as classes concretas, apenas interfaces;
- Código com alta abstração e fatorado, tornando de fácil manutenção e extensão;
- Por conta da fatoração, é um código mais fácil de escrever testes de funcionamento;
## Pontos de atenção 
- Como no exemplo, deixa o código muito maior e mais confuso, com muitas partes que podem parecer fazer a mesma coisa dependendo de quem vê;
---
## Conclusão 
O padrão Abstract Factory é útil quando há necessidade de criar famílias de objetos relacionados, como neste caso, onde o sistema precisa trabalhar com diferentes tipos de carro (luxo ou popular).
Embora o padrão introduza certa complexidade, ele promove boa organização, manutenibilidade e extensibilidade, características essenciais em sistemas que tendem a crescer ou mudar com o tempo.
