<h1 align="center">
  <img align="center" alt="Imagem trybe" src="https://i.ibb.co/d4W2x4g/trybe.png" width="300px" />
</h1>

<h3 align="center">
  Curso realizado na Trybe - Edu Souza o/
</h3>

<blockquote align="center">“Os indivíduos só são heróis quando não podem agir de outra maneira - Paul Claudel”</blockquote>

<h4 align="center">
  Repositório - Javascript testes unitarios
</h4>

<br/>

<p align="center">
  <a href="https://github.com/EduSouza-programmer"    target="_blank">
    <img alt="Made by Eduardo Souza" src="https://img.shields.io/badge/made%20by-Edu%20Souza-%23F8952D">
  </a>&nbsp;
  <a href="https://edusouza-programmer.github.io/" target="_blank">
    <img alt="Github page Edu_Souza " src="https://img.shields.io/badge/Github%20page-Edu_Souza-orange">
  </a>&nbsp;
  <a href="#" >
    <img alt="License" src="https://img.shields.io/badge/license-MIT-%23F8952D">
  </a>
</p>

<p align="center">
  <a href="#rocket-Sobre-o-projeto">Sobre o projeto</a>&nbsp; &nbsp; |&nbsp; &nbsp;
  <a href="#postbox-Entrega"">Entrega</a>&nbsp; &nbsp; |&nbsp; &nbsp;
  <a href="#unlock-Licença">Licença</a>
</p>

## :rocket: Sobre o projeto

#### Javascript testes unitarios

Você vai implementar funções a partir de requisitos e testes unitários, utilizando o módulo Assert do NodeJS para verificar o correto funcionamento dessas funções.

Testes unitários são fundamentais para a criação de funcionalidades com qualidade. Aprender o que são e como devem ser implementados é primordial para quem desenvolve software.

## :postbox: Entrega

#### :clipboard: Sumário

- <p><a href="#1"> :pushpin: 1.</a> Implemente a função do arquivo `src/average.js`</p>
- <p><a href="#2"> :pushpin: 2.</a> Implemente os casos de teste no arquivo `tests/numbers.spec.js`</p>
- <p><a href="#3"> :pushpin: 3.</a> Implemente a função do arquivo `src/vqv.js`</p>
- <p><a href="#4"> :pushpin: 4.</a> Implemente os casos de teste no arquivo `tests/circle.spec.js`</p>
- <p><a href="#5"> :pushpin: 5.</a> Implemente a função do arquivo `src/createStudent.js`</p>
- <p><a href="#6"> :pushpin: 6.</a> Implemente os casos de teste no arquivo `tests/productDetails.spec.js`</p>
- <p><a href="#7"> :pushpin: 7.</a> Implemente a função do arquivo `src/objCalculator.js`</p>
- <p><a href="#8"> :pushpin: 8.</a> Implemente a função do arquivo `src/myCounter.js`</p>
- <p><a href="#9"> :pushpin: 9.</a> Implemente os casos de teste no arquivo `tests/restaurant.spec.js` e as funções do arquivo `src/restaurant.js`</p>

<br/>

## :books: Exercícios

### 1°

A função average recebe um array (tamanho variável) e retorna a média dos valores recebidos.
Caso a função receba algum valor não númerico ou um array vazio,
o valor undefined deve ser retornado.
Todos os resultados devem ser arredondados para valores inteiros. Ex: 4,6 vira 5; 1,3 vira 1.

Parâmetros:
- Um array. Exemplos: [1, 2]; [1, 2, 3, 4, 5]; [1, 2, '3']; [];

Comportamento:
- average([2, 2]) // Retorno: 2;
- average([1, 1]) // Retorno: 1;
- average([1, '2']) // Retorno: undefined;

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const average = (arrs) => {
  const divisor = arrs.length;
  let total = 0;

  if (arrs.length === 0) {
    return undefined;
  }
  for (let index = 0; index < arrs.length; index += 1) {
    if (typeof arrs[index] !== 'number') {
      return undefined;
    }
    total += arrs[index];
  }
  return Math.round(total / divisor);
};

module.exports = average;
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 2°

  A função numbers recebe um array (tamanho variável) e retorna true se todos os parâmetros forem do tipo 'number' e false caso contrário.

  Parâmetros:
    - Um array. Exemplos: [1, 2]; [1, 2, 3, 4, 5]; [1, 2, 'a']; [].
  Comportamento:
    - numbers([2, 3, 4]); // Retorna: true
    - numbers([2, 'errado', 5]); // Retorna: false

  OBS: Lembre-se que você não precisa se preocupar com o describe e o it por enquanto, isso será aprendido posteriormente.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require('assert');
const numbers = require('../src/numbers');

describe('#numbers', () => {
  it('should return an array and return if it has only numbers or not', () => {

    // Escreva um teste em que a função recebe [1, 2, 3, 4, 5] e retorna true
    assert.strictEqual(numbers([1, 2, 3, 4, 5]), true);
    // Escreva um teste em que a função recebe [1, 2, '3', 4, 5] e retorna false
    assert.strictEqual(numbers([1, 2, '3', 4, 5]), false);
    // Escreva um teste em que a função recebe [1, 'a', 3] e retorna false
    assert.strictEqual(numbers([1, 'a', 3]), false);
    // Escreva um teste em que a função recebe [' '] e retorna false
    assert.strictEqual(numbers([' ']), false);
  });
});
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#


### 3°

  Use template literals para escrever uma função que,
  recebe seu nome e sua idade e retorna o parágrafo descrito abaixo.
  Caso a função seja chamada sem nenhum parâmetro, o valor undefined deve ser retornado.

  Parâmetros:
    - Uma string;
    - Um número.
  Comportamento:
    vqv(Tunico, 30) // Retorna:
      'Oi, meu nome é Tunico!
      Tenho 30 anos,
      trabalho na Trybe e mando muito em programação!
      #VQV!'

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const vqv = (nome, idade) => {
  const checkUndefined = nome === undefined || idade === undefined;
  if (checkUndefined) return undefined;

  return `Oi, meu nome é ${nome}!\nTenho ${idade} anos,\ntrabalho na Trybe e mando muito em programação!\n#VQV!`;
};

module.exports = vqv;
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#
### 4°

 Essa função recebe o raio de um círculo e retorna um objeto contendo suas informações (Raio, Área e Circunferência).
  Se não for especificado um raio, a função retorna undefined.
  Elabore testes para verificar se a função está correta.

  Parâmetros:
    - Um número inteiro. Exemplos: 1; 3;
  Comportamento:
    - circle(1) // Retorno: {radius: 1, area: 3.14, circumference: 6.28}
    - circle(7) // Retorno: {radius: 7, area: 153.86, circumference: 43.96}
    - circle(3) // Retorno: {radius: 3, area: 28,26, circumference: 18.84}

  DICA: Números de ponto flutuante em JavaScript são imprecisos!  Para testar, vá no seu navegador e faça `0.2 + 0.1`.
        Uma solução pra isso pode ser fazer a soma no seguinte formato: `parseFloat((0.2 + 0.1).toPrecision(2))`.
        Use esse conhecimento para te ajudar a lidar com possíveis problemas que esses testes trarão!

  OBS: Lembre-se que você não precisa se preocupar com o describe e o it por enquanto, isso será aprendido posteriormente.`Paolillo, Lucas`.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require('assert');
const circle = require('../src/circle');

describe('#circle', () => {
  it('given a radius, should return an object with circles info', () => {

    // ESCREVA SEUS TESTES ABAIXO:
    // Teste se circle retorna um objeto.
    assert.strictEqual(typeof circle(1), 'object');
    // Teste se o objeto retornado tem 3 entradas.
    assert.strictEqual(Object.keys(circle(2)).length, 3);
    // Teste se a função, quando não recebe nenhum parâmetro, retorna undefined.
    assert.strictEqual(circle(), undefined);
    // Teste que a função retorna, dentro de um objeto, a circunferência correta para um círculo de raio 2.
    assert.strictEqual(circle(2).circumference, (2 * 3.14 * 2));
    // Teste que a função retorna, dentro de um objeto, a área correta para um círculo de raio 3.
    assert.strictEqual(circle(3).area, (3.14 * 3 * 3));
    // Teste que a função retorna, num objeto, os dados corretos de um círculo de raio 3.
    assert.deepStrictEqual(Object.values(circle(3)), [
      3,
      (3.14 * 3 * 3),
      (2 * 3.14 * 3)
    ])
  });
});
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#
### 5°

 Dada uma função chamada createStudent que recebe como parâmetro um nome,
  retorne um objeto que contenha duas chaves:
    (1) name, contendo o nome passado como parâmetro;
    (2) feedback, contendo uma função que retorna a frase 'Eita pessoa boa!' ao ser chamada.

  Faça a função da chave feedback com arrow functions!

  Parâmetros:
    - Uma string;
  Comportamento:
    const estudante = createStudent('Leandrão, o Lobo Solitário')

    estudante.name // Retorna: 'Leandrão, o Lobo Solitário'
    estudante.feedback() // Retorna: 'Eita pessoa boa!'

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const createStudent = name => ({
  name,
  feedback: () => 'Eita pessoa boa!',
});

module.exports = createStudent;
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#
### 6°

 Dadas duas strings que representam nomes de produtos, retorne um array contendo dois objetos com os detalhes dos respectivos produtos.

  Parâmetros:
  - Uma string;
  - Uma string;

  Comportamento:
  productDetails('Alcool gel', 'Máscara') // Retorna:
  [
    {
      name: 'Alcool gel'
      details: {
        productId: 'Alcool gel123'
      }
    },
    {
      name: 'Máscara'
      details: {
        productId: 'Máscara123'
      }
    }
  ]

  OBS: Lembre-se que você não precisa se preocupar com o describe e o it por enquanto, isso será aprendido posteriormente.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require('assert');
const productDetails = require('../src/productDetails');


describe('#productDetails', () => {
  it('tests the function has the correct behaviour', () => {
    // ESCREVA SEUS TESTES ABAIXO:
    // Teste que o retorno da função é um array.
    //prettier-ignore
    assert.strictEqual(Array.isArray(productDetails('Alcool', 'Máscara')), true);

    // Teste que o array retornado pela função contém dois itens dentro.
    assert.strictEqual(productDetails('Alcool', 'Máscara').length, 2);

    // Teste que os dois itens dentro do array retornado pela função são objetos.
    assert.strictEqual(
      typeof Object.values(productDetails('Alcool', 'Máscara')),
      'object'
    );
    // Teste que os dois objetos são diferentes entre si.
    assert.notStrictEqual(
      productDetails('Alcool', 'Máscara')[0],
      productDetails('Alcool', 'Máscara')[1]
    );
    // (Difícil) Teste que os dois productIds terminam com 123.
    const [{ details: obj1 }, { details: obj2 }] = productDetails(
      'Alcool',
      'Máscara'
    );
    const endProductId = obj1.productId.slice(-3) === obj2.productId.slice(-3);
    assert.strictEqual(endProductId, true);
  });
});
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#
### 7°

 Desenvolva um objeto calculator que possui quatro chaves:
    - add;
    - mult;
    - div;
    - sub.
  Para cada uma delas atribua uma função que realiza a respectiva operação.
  A função deve receber dois inteiros e retornar um inteiro.
  Os resultados das divisões devem sempre ser arredondados para baixo.

  Faça as funções com arrow functions!

  Parâmetros:
  - Um número inteiro;
  - Um número inteiro;

  Comportamento:
  calculator.add(1, 1) // Retorno: 2;
  calculator.div(3, 2) // Retorno: 1;

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const calculator = {
  add: (num1, num2) => num1 + num2,
  mult: (num1, num2) => num1 * num2,
  div: (num1, num2) => Math.floor(num1 / num2),
  sub: (num1, num2) => num1 - num2,
};

module.exports = calculator;
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#
### 8°

   A função myCounter possui dois loops aninhados que inserem valores dentro de um array.
  Como podemos perceber, eles vão adicionando valores ao array até sua condição de parada.
  Corrija o código abaixo para que a função retorne o array correto.

  Parâmetros:
  - Nenhum.

  Comportamento:
  myCounter() // Retorna: [0, 2, 3, 1, 2, 3, 2, 2, 3, 3, 2, 3];

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const myCounter = () => {
  const myArray = [];
  for (let counter1 = 0; counter1 <= 3; counter1 += 1) {
    myArray.push(counter1);
    for (let counter2 = 2; counter2 <= 3; counter2 += 1) {
      myArray.push(counter2);
    }
  }
  return myArray;
};

module.exports = myCounter;
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#
### 9°

Você é responsável por escrever o código do sistema de pedidos de um restaurante. Deve ser possível, através desse sistema, cadastrar um menu. Dado que um menu foi cadastrado, o sistema deve disponibilizar um objeto através do qual se consegue:
  - ler o menu cadastrado;
  - fazer pedidos;
  - verificar o que foi pedido;
  - somar o valor da conta.

  A estrutura deste código e deste objeto já foi definida e você irá implementá-la.
  Abaixo você verá uma série de testes e passos que devem ser, NECESSARIAMENTE, feitos em ordem para o bom desenvolvimento do sistema. Eles guiarão você pelo desenvolvimento.

  Parâmetros:
  - Um objeto. Exemplos: { food: {'coxinha': 3.9, 'sopa': 9.9}, drink: {'agua': 3.9, 'cerveja': 6.9} }.
  Comportamento:

  const meuRestaurante = createMenu({ food: {'coxinha': 3.9, 'sopa': 9.9}, drink: {'agua': 3.9, 'cerveja': 6.9} }).

  meuRestaurante.fetchMenu() // Retorno: { food: {'coxinha': 3.9, 'sopa': 9.9}, drink: {'agua': 3.9, 'cerveja': 6.9} }

  meuRestaurante.order('coxinha') // Retorno: undefined

  meuRestaurante.consumption // Retorno: ['coxinha']

  meuRestaurante.pay() // Retorno: 3.9

  Uma função createMenu retorna um objeto com as seguintes características:
  - Uma chave `fetchMenu` retorna o objeto que a função `createMenu` recebe por parâmetro. O menu tem sempre duas chaves, `food` e `drink`, no seguinte formato:

  const meuRestaurante = createMenu({
    food: {'coxinha': 3.90, 'sanduiche', 9.90},
    drinks: {'agua': 3.90, 'cerveja': 6.90}
  });

  meuRestaurante.fetchMenu() // Retorno: Menu acima

  - Uma chave `consumption` que contém um array de strings, com cada string sendo a chave de um pedido. Por exemplo: ['coxinha', 'cerveja']

  - Uma chave `order` que tem uma função que, recebida uma string como parâmetro, adiciona essa string à lista salva em `consumption`.

  - Uma chave `pay` que, quando chamada, invoca uma função que soma o valor de todos os pedidos e dá o preço com acréscimo de 10%.

  IMPORTANTE: FAÇA OS TESTES E PASSOS DE ACORDO COM A ORDEM INDICADA!

  OBS: Lembre-se que você não precisa se preocupar com o describe e o it por enquanto, isso será aprendido posteriormente.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const assert = require('assert');
const createMenu = require('../src/restaurant');

describe('#createMenu', () => {
  it('tests the function has the correct behaviour', () => {
    // TESTE 1: Verifique que, dado um objeto qualquer passado como um parâmetro para a função createMenu(), checa se o retorno da função é um objeto no seguinte formato: { fetchMenu: objetoQualquer }.
    // ```
    // createMenu(objetoQualquer) // Retorno: { fetchMenu: objetoQualquer }
    // ```
    const object = {
      food: { coxinha: 3.9, sanduiche: 9.9 },
      drinks: { agua: 3.9, cerveja: 6.9 },
    };
    const menuTest = createMenu(object);
    const { fetchMenu } = createMenu(object);
    assert.strictEqual(fetchMenu, object);
    // Agora faça o PASSO 1 no arquivo `src/restaurant.js`.
    // --------------------------------------------------------------------------------------
    // TESTE 2: Verifique que, dado que a função createMenu foi chamada com o objeto: `{ food: {}, drink: {} }`, verifique que 'objetoRetornado.fetchMenu' retorna um objeto cujas chaves são somente `food` e `drink`.
    // ```
    // const objetoRetornado = createMenu(objetoQualquer);
    // objetoRetornado.fetchMenu // Retorno: { food: {}, drink: {}}

    assert.deepStrictEqual(createMenu({ food: {}, drink: {} }).fetchMenu, {
      food: {},
      drink: {},
    });

    // ```
    // Agora faça o TESTE 3 deste arquivo.
    // --------------------------------------------------------------------------------------
    // TESTE 3: Verifique que o menu passado pra função createMenu é identico ao menu recuperado pela função 'objetoRetornado.fetchMenu'
    // ```
    // const objetoRetornado = createMenu(objetoQualquer);
    // objetoRetornado.fetchMenu // Retorno: objetoQualquer

    const objectForCompare1 = createMenu(object).fetchMenu;
    assert.deepStrictEqual(objectForCompare1, object);
    // ```
    // Agora faça o TESTE 4 deste arquivo.
    // --------------------------------------------------------------------------------------
    // TESTE 4: Verifique que 'objetoRetornado.consumption', após a criação do menu, retorna um array vazio.
    // ```
    // const objetoRetornado = createMenu(objetoQualquer);
    // objetoRetornado.consumption // Retorno: []

    const objectForCompare2 = createMenu({}).consumption;
    assert.deepStrictEqual(objectForCompare2, []);
    // ```
    // Agora faça o PASSO 2 no arquivo `src/restaurant.js`.
    // --------------------------------------------------------------------------------------
    // TESTE 5: Verifique que chamar uma função associada à chave `order` no objeto retornado, passando uma string como parâmetro, como `objetoRetornado.order('coxinha')`, tal string é adicionada ao array retornado em `objetoRetornado.consumption
    // ```;
    // const objetoRetornado = createMenu(objetoQualquer);
    // objetoRetornado.order("coxinha");
    // objetoRetornado.comsuption // Retorno: ["coxinha"]
    menuTest.order('coxinha');
    assert.deepStrictEqual(menuTest.consumption, ['coxinha']);
    // ```
    // Agora faça o PASSO 3 no arquivo `src/restaurant.js`.
    // --------------------------------------------------------------------------------------
    // TESTE 6: Verifique que as três orders seguintes, de bebidas e comidas mescladas, somam três itens no array `objetoRetornado.consumption` conforme os itens pedidos.
    // ```
    // objetoRetornado.order("coxinha");
    // objetoRetornado.order("agua");
    // objetoRetornado.order("sopa");
    // objetoRetornado.order("sashimi");
    // objetoRetornado.consumption // Retorno: ["coxinha", "agua", "sopa", "sashimi"]
    menuTest.order('agua');
    menuTest.order('cerveja');
    menuTest.order('sanduiche');
    assert.deepStrictEqual(menuTest.consumption, [
      'coxinha',
      'agua',
      'cerveja',
      'sanduiche',
    ]);
    // ```
    // Agora faça o TESTE 7 deste arquivo.
    // --------------------------------------------------------------------------------------
    // TESTE 7: Verifique que a função `order` aceita que pedidos repetidos sejam acrescidos a consumption.
    // ```
    // objetoRetornado.order('coxinha');
    // objetoRetornado.order('agua');
    // objetoRetornado.order('coxinha');
    // objetoRetornado.comsuption // Retorno: ['coxinha', 'agua', 'coxinha']
    menuTest.order('agua');
    assert.deepStrictEqual(menuTest.consumption, [
      'coxinha',
      'agua',
      'cerveja',
      'sanduiche',
      'agua',
    ]);
    // ```
    // Agora faça o TESTE 8 deste arquivo.
    // --------------------------------------------------------------------------------------
    // TESTE 8: Verifique que, ao chamar `objetoRetornado.pay()`, retorna-se a soma dos preços de tudo que foi pedido, conforme registrado em `objetoRetornado.consumption`
    // ```
    // objetoRetornado.order('coxinha');
    // objetoRetornado.order('agua');
    // objetoRetornado.order('coxinha');
    // objetoRetornado.pay() // Retorno: somaDosPreçosDosPedidos
    assert.strictEqual(menuTest.pay(), '31.35');
    // ```
    // Agora faça o PASSO 4 no arquivo `src/restaurant.js`.
  });
});
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

## :unlock: Licença

Este projeto está licenciado sob a Licença MIT - consulte [LICENSE](https://opensource.org/licenses/MIT) para maiores detalhes.
