
TIVIT - .Net com GitHub Copilot


Você se certificou nas seguintes habilidades:

- .NET
- C#
- GitHub
- Git
- POO
- Banco de Dados
- GitHub Copilot


<img width="1010" height="693" alt="image" src="https://github.com/user-attachments/assets/e540a234-f21d-431f-9344-38b6b7b3632b" />

<img width="1101" height="774" alt="image" src="https://github.com/user-attachments/assets/13a5feb9-3f47-4c2b-bad7-fe7f287b83f2" />


 
https://web.dio.me/lab/criando-um-validador-de-bandeiras-de-cartao-de-credito-com-o-github-copilot/learning/d71c1ba2-8f3f-4b23-bfdf-b20bf8f13465?back=/track/tivit-net-github-copilot

# Desafio de projeto

## Criando um Validador de Bandeiras de Cartão de Crédito com o GitHub Copilot


- Introdução ao Ambiente .NET
- Sintaxe Básica com .NET C#
- Dados e Listas com .NET C#
- Programação Orientada a Objetos com C#
- Introdução a Banco de Dados
- Criando APIS com .NET C#
- Desenvolvimento De Aplicações Com Inteligência Artificial


# Validador de Bandeira de Cartão com Copilot

Projeto desenvolvido com o objetivo de aplicar conceitos de **Prompt Engineering** e uso do GitHub Copilot para geração de código.

---

## Objetivo

Criar uma função em **JavaScript** capaz de identificar a bandeira de um cartão de crédito com base no número informado, utilizando **expressões regulares (regex)**.

---

## Prompt utilizado

### Versão recomendada

Crie uma função em JavaScript que identifique a bandeira de um cartão de crédito com base no número informado.

Regras:
- Visa: começa com 4
- MasterCard: começa com 51 até 55
- American Express: começa com 34 ou 37
- Elo: considere padrões comuns (ex: 4011, 4312, 4389)
- Hipercard: começa com 6062

Requisitos:
- A função deve receber o número do cartão como string
- Deve retornar o nome da bandeira
- Caso não identifique, retornar "Bandeira desconhecida"
- Utilize expressões regulares (regex)
- Adicione exemplos de uso

Exemplo:
Entrada: "4111111111111111"  
Saída: "Visa"

---

###  Versão avançada

Você é um desenvolvedor especialista em JavaScript.

Crie uma função limpa e bem estruturada para identificar a bandeira de um cartão de crédito.

Requisitos:
- Usar regex
- Código legível e comentado
- Tratar entradas inválidas
- Retornar a bandeira ou "Bandeira desconhecida"

Inclua exemplos e testes com console.log.

---

## Boas práticas aplicadas

- Linguagem clara e objetiva  
- Definição de regras de negócio  
- Especificação de entrada e saída  
- Uso de exemplos  
- Código limpo e legível  

---

## Como executar

1. Acesse o CodePen (https://codepen.io/)
2. Cole o código na aba **HTML**
3. Execute o projeto
4. Digite o número do cartão e valide

---

## Código do projeto

<img width="1418" height="891" alt="image" src="https://github.com/user-attachments/assets/d9eb4fde-16c3-4e2a-b7e2-a6b5415b650d" />


# Código HTML:

<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Validador de Bandeira de Cartão</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #1e1e1e;
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      background: #2c2c2c;
      padding: 30px;
      border-radius: 10px;
      width: 350px;
      text-align: center;
    }

    input {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      border-radius: 5px;
      border: none;
    }

    button {
      margin-top: 15px;
      padding: 10px;
      width: 100%;
      background: #4CAF50;
      border: none;
      color: white;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background: #45a049;
    }

    .resultado {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="container">
  <h2>Validador de Bandeira</h2>
  <input type="text" id="numeroCartao" placeholder="Digite o número do cartão">
  <button onclick="validarCartao()">Validar</button>
  <div class="resultado" id="resultado"></div>
</div>

<script>
  function identificarBandeira(numero) {
    numero = numero.replace(/\D/g, "");

    const regras = [
      { nome: "Visa", regex: /^4[0-9]{12}(?:[0-9]{3})?$/ },
      { nome: "MasterCard", regex: /^5[1-5][0-9]{14}$/ },
      { nome: "American Express", regex: /^3[47][0-9]{13}$/ },
      { nome: "Elo", regex: /^(4011|4312|4389)[0-9]{12}$/ },
      { nome: "Hipercard", regex: /^6062[0-9]{12}$/ }
    ];

    for (let regra of regras) {
      if (regra.regex.test(numero)) {
        return regra.nome;
      }
    }

    return "Bandeira desconhecida";
  }

  function validarCartao() {
    const numero = document.getElementById("numeroCartao").value;
    const resultado = identificarBandeira(numero);
    document.getElementById("resultado").innerText = resultado;
  }

  // Testes automáticos no console
  console.log(identificarBandeira("4111111111111111")); // Visa
  console.log(identificarBandeira("5500000000000004")); // MasterCard
  console.log(identificarBandeira("340000000000009"));  // Amex
</script>

</body>
</html>


# Código JavaScript:

function testar() {
  const testes = [
    { entrada: "4111111111111111", esperado: "Visa" },
    { entrada: "5500000000000004", esperado: "MasterCard" },
    { entrada: "340000000000009", esperado: "American Express" },
    { entrada: "4011123412341234", esperado: "Elo" },
    { entrada: "6062123412341234", esperado: "Hipercard" },
    { entrada: "123", esperado: "Bandeira desconhecida" }
  ];

  testes.forEach(teste => {
    const resultado = identificarBandeira(teste.entrada);
    if (resultado === teste.esperado) {
      console.log(` OK: ${teste.entrada}`);
    } else {
      console.error(` ERRO: ${teste.entrada} → ${resultado}`);
    }
  });
}

// Executar testes
testar();









