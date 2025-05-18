# Manipulando o DOM (Document Object Model)
### O DOM é a representação do seu HTML que o JavaScript pode manipular.
## Selecionando Elementos
```javascript
// Por ID
let elemento = document.getElementById('meuId');

// Por classe (retorna coleção)
let elementos = document.getElementsByClassName('minhaClasse');

// Por seletor CSS (moderno)
let elemento = document.querySelector('#meuId .minhaClasse');
let todosElementos = document.querySelectorAll('div');
```
## Modificando Elementos
```javascript
// Alterar conteúdo
elemento.textContent = 'Novo texto';
elemento.innerHTML = '<strong>Texto</strong> com HTML';

// Alterar atributos
elemento.setAttribute('src', 'nova-imagem.jpg');

// Alterar estilos
elemento.style.color = 'blue';
elemento.style.backgroundColor = '#f0f0f0';

// Adicionar/remover classes
elemento.classList.add('nova-classe');
elemento.classList.remove('classe-antiga');
elemento.classList.toggle('classe-alternada');
```
## Eventos
```javascript
// Ouvinte de evento simples
botao.addEventListener('click', function() {
    console.log('Botão clicado!');
});

// Evento comum com parâmetros
document.querySelector('form').addEventListener('submit', function(event) {
    event.preventDefault(); // Evita recarregar a página
    console.log('Formulário enviado');
});
```
## Fuções
```javascript
// Declaração de função
function saudacao(nome) {
    return 'Olá, ' + nome + '!';
}

// Expressão de função
const soma = function(a, b) {
    return a + b;
};

// Arrow function (moderna)
const quadrado = x => x * x;

// Chamando funções
saudacao('Maria'); // "Olá, Maria!"
soma(2, 3); // 5
quadrado(4); // 16
```
## Objetos e Arrays
```javascript
// Objeto
let pessoa = {
    nome: 'Carlos',
    idade: 28,
    saudar: function() {
        return 'Oi, eu sou ' + this.nome;
    }
};

console.log(pessoa.nome); // "Carlos"
console.log(pessoa.saudar()); // "Oi, eu sou Carlos"

// Array
let frutas = ['maçã', 'banana', 'laranja'];

// Métodos úteis de array
frutas.push('morango'); // Adiciona no final
frutas.pop(); // Remove do final
frutas.map(fruta => fruta.toUpperCase()); // Transforma cada item
frutas.filter(fruta => fruta.length > 5); // Filtra itens
```
## Exemplo Prático: Contador Interativo
```javascript
<!DOCTYPE html>
<html>
<head>
    <title>Contador</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Contador</h1>
    <p id="contador">0</p>
    <button id="incrementar">+</button>
    <button id="decrementar">-</button>
    <button id="zerar">Zerar</button>

    <script>
        // Seleciona elementos
        const contadorElemento = document.getElementById('contador');
        const incrementarBtn = document.getElementById('incrementar');
        const decrementarBtn = document.getElementById('decrementar');
        const zerarBtn = document.getElementById('zerar');

        // Estado inicial
        let contador = 0;

        // Atualiza o contador na tela
        function atualizarContador() {
            contadorElemento.textContent = contador;
        }

        // Event listeners
        incrementarBtn.addEventListener('click', () => {
            contador++;
            atualizarContador();
        });

        decrementarBtn.addEventListener('click', () => {
            contador--;
            atualizarContador();
        });

        zerarBtn.addEventListener('click', () => {
            contador = 0;
            atualizarContador();
        });

        // Inicializa
        atualizarContador();
    </script>
</body>
</html>
```
