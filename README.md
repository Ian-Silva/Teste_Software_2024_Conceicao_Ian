ATIVIDADE 1 - Ian da Silva Santos Conceição: How to test the type of a thrown exception in jest?

REPOSITÓRIO DO PROJETO: https://github.com/Ian-Silva/Teste_Software_2024_Conceicao_Ian

Problema Informado:

O problema publicado no Stack Overflow se direciona querendo saber como o usuário consegue testar o tipo de uma exceção lançada por uma função.

O usuário informou o código dele que estará logo abaixo:

it('should throw Error with message \'UNKNOWN ERROR\' when no params were passed', (t) => {
  const error = t.throws(() => {
    throwError();
  }, TypeError);

  t.is(error.message, 'UNKNOWN ERROR');
});

E buscou ajuda no Site para conseguir solucionar essa questão.


Solução para o problema informado:

Um usuário do Stack Overflow postou uma resposta para 3 casos caso o usuário que estava querendo ajuda precisasse de mais informações, já teria como realiza-las.

Sua primeira resposta foi:

No Jest você tem que passar uma função para expect(function).toThrow(<blank or type of error>).

Exemplo:

test("Test description", () => {
  const t = () => {
    throw new TypeError();
  };
  expect(t).toThrow(TypeError);
});

Segunda resposta:

Caso você também quiser verificar se há mensagem de erro:

test("Test description", () => {
  const t = () => {
    throw new TypeError("UNKNOWN ERROR");
  };
  expect(t).toThrow(TypeError);
  expect(t).toThrow("UNKNOWN ERROR");
});

E a terceira resposta:

Se você precisar testar uma função existente para ver se ela é gerada com um conjunto de argumentos, 
você terá que envolvê-la dentro de uma função anônima em expect().

Exemplo:

test("Test description", () => {
  expect(() => {http.get(yourUrl, yourCallbackFn)}).toThrow(TypeError);
});

