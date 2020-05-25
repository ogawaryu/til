# Função Assíncrinas

Quando você declara uma função `async` ela retorna uma `Promise`, um objeto `AsyncFunction`. Porem, diferente de uma Promise normal, retorna o valor resolvido e não um objeto `Promise`, sem precisar implementar uma callback para ter acesso ao valor.

### Async Function

```javascript

function somar(valor1, valor2) {
  return new Promise(resolve => {
    resolve(valor1 + valor2);
  });
}


async function calcular () {
  const resultado = await somar(10, 10)
  return resultado
}

// Resultado
calcular() // 20

``` 

### Promise Normal

```javascript

function somar(valor1, valor2) {
  return new Promise(resolve => {
    resolve(valor1 + valor2);
  });
}

// Resultado
function calcular (resultado) {
  console.log(resultado) // 20
}

somar(10, 10)
  .then(calcular)

````

São duas formas de resolver um objeto de processamento assíncrono. Use a forma que achar mais interessante nos seus projetos. Eu, particularmente, gosto do `async/await`. :)
