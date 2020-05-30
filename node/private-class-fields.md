# Atributos privados de classes

Até o ES2019, por padrão, todas os atributos da classe são públicos por padrão. Normalmente os desenvolvedores usavam "_" sempre antes de um atributo para sinalizar que aquele atributo era pra somente ser usado no contexto da classe, porem isso não impossibilita de ser usado de forma pública. A partir do ES2019 podemos então definir atributos privados em classes, usando prefixo # nos nomes dos atributos.

### Classe com atributo público

```javascript

class User {

  nome = 'Joãozinho'
  idade = 13
  #cpf = '324.424.324-42'

  meuCPF () {
    return this.#cpf
  }
}

const user = new User()
user.meuCPF() // OK
user.#cpf = '333.333.333-33' // Uncaught SyntaxError: Private field '#cpf' must be declared in an enclosing class

```

Percebe que somente tem acesso ao atributo atravez de um método. Também gera um erro caso você tente atribuir um valor ao atributo privado.

