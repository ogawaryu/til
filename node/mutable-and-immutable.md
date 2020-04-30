# Mutable and Immutable Array

Vou começar esse "Today I Learned", com um conceito de array mutável e não mutável.
Técnica muito usada no dia a dia, implementando de forma nativa o que a linguagem javascript pode oferecer.

### Mutável

```javascript

const arrayMutavel = ['Cerveja']

arrayMutavel.push('IPA');
arrayMutavel.splice(arrayMutavel.length, 0, 'IPA');
arrayMutavel[arrayMutavel.length] = 'IPA';

// Resultado
arrayMutavel; // ['cerveja', 'ipa']

```

### Imutável


```javascript

const arrayImutavel = ['Cerveja'];

let novoArray;
novoArray = arrayImutavel.concat('IPA');
novoArray = [...arrayImutavel, 'IPA'];

// Resultado
novoArray; // ['Cerveja', 'IPA']
arrayImutavel; // ['Cerveja']

```

## Vantagem 

Usar o conceito de imutabilidade permite que você controle melhor o que esta sendo realizado no programa e previne que altere uma variável que não poderia ser alterada. Manter esses valores constante economiza em processamento também. Após alocado na memória, seu estado se mantém.
