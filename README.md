# index.html
Es el diccionario definitivo 
<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Diccionario Web</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 800px;
      margin: 2rem auto;
      padding: 0 1rem;
      color: #333;
    }
    h1 {
      text-align: center;
      margin-bottom: 1rem;
    }
    #search-container {
      display: flex;
      justify-content: center;
      margin-bottom: 1rem;
    }
    #search-input {
      width: 100%;
      max-width: 400px;
      padding: 0.5rem;
      font-size: 1rem;
      border: 1px solid #ccc;
      border-radius: 4px 0 0 4px;
    }
    #search-button {
      padding: 0.5rem 1rem;
      font-size: 1rem;
      border: 1px solid #ccc;
      border-left: none;
      border-radius: 0 4px 4px 0;
      cursor: pointer;
      background-color: #f5f5f5;
    }
    #definition {
      background-color: #f9f9f9;
      padding: 1rem;
      border-radius: 4px;
      box-shadow: 0 1px 3px rgba(0,0,0,0.1);
      min-height: 100px;
    }
    .term {
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Diccionario Web</h1>
  <div id="search-container">
    <input type="text" id="search-input" placeholder="Escribe una palabra..." />
    <button id="search-button">Buscar</button>
  </div>
  <div id="definition">Introduce un término y pulsa "Buscar" para ver la definición.</div>  <script>
    // Diccionario de ejemplo
    const dictionary = {
      infinito: "Que no tiene ni puede tener fin.",
      ser: "Existir, tener presencia real en el mundo.",
      monstruo: "Animal fabulado, extraordinario, de figura horrible.",
      tirabuzón: "Cada una de las espirales que forma un cabello enrollado naturalmente.",
      ropa: "Conjunto de prendas que sirven para cubrir el cuerpo humano."
    };

    const input = document.getElementById('search-input');
    const button = document.getElementById('search-button');
    const output = document.getElementById('definition');

    function buscar() {
      const term = input.value.trim().toLowerCase();
      if (!term) {
        output.textContent = 'Por favor, escribe una palabra.';
        return;
      }
      const definition = dictionary[term];
      if (definition) {
        output.innerHTML = `<span class="term">${term}</span>: ${definition}`;
      } else {
        output.textContent = `La palabra "${term}" no está en el diccionario.`;
      }
    }

    button.addEventListener('click', buscar);
    input.addEventListener('keydown', e => {
      if (e.key === 'Enter') buscar();
    });
  </script></body>
</html>
