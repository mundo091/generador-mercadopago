<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Generador de títulos seguros Mercado Pago</title>
<style>
  body {
    font-family: Arial, sans-serif;
    max-width: 600px;
    margin: 2rem auto;
    padding: 1rem;
    background: #f5f5f5;
    color: #333;
  }
  h1 {
    text-align: center;
  }
  label {
    font-weight: bold;
    display: block;
    margin-bottom: 0.5rem;
  }
  textarea {
    width: 100%;
    height: 100px;
    font-size: 1rem;
    padding: 0.5rem;
    border-radius: 4px;
    border: 1px solid #ccc;
    resize: vertical;
  }
  button {
    margin-top: 1rem;
    padding: 0.75rem 1.5rem;
    font-size: 1rem;
    border: none;
    background-color: #0070f3;
    color: white;
    border-radius: 4px;
    cursor: pointer;
  }
  button:hover {
    background-color: #005bb5;
  }
  #resultado {
    margin-top: 1rem;
    background: white;
    border: 1px solid #ccc;
    padding: 1rem;
    white-space: pre-wrap;
    font-family: monospace;
    user-select: all;
  }
  footer {
    margin-top: 2rem;
    font-size: 0.9rem;
    color: #666;
    text-align: center;
  }
</style>
</head>
<body>

<h1>Generador de títulos seguros para Mercado Pago</h1>

<label for="textoEntrada">Escribe el modelo:</label>
<textarea id="textoEntrada" placeholder="Ejemplo: iPhone 15 Pro Max Titanium Natural 256GB"></textarea>

<button id="generarBtn">Generar título seguro</button>

<div id="resultado" title="Haz clic para copiar"></div>

<footer>© 2025 - Tu Asistente Digital</footer>

<script>
  function generarTituloSeguro(texto) {
    const invisible = "\u200B"; // carácter espacio invisible
    let resultado = "";
    for (const letra of texto) {
      resultado += letra + invisible;
    }
    return resultado;
  }

  const btn = document.getElementById('generarBtn');
  const entrada = document.getElementById('textoEntrada');
  const resultado = document.getElementById('resultado');

  btn.addEventListener('click', () => {
    const texto = entrada.value.trim();
    if (!texto) {
      resultado.textContent = "Por favor escribe un modelo válido.";
      return;
    }
    resultado.textContent = generarTituloSeguro(texto);
  });

  // Copiar al hacer clic
  resultado.addEventListener('click', () => {
    const sel = window.getSelection();
    const range = document.createRange();
    range.selectNodeContents(resultado);
    sel.removeAllRanges();
    sel.addRange(range);
    try {
      document.execCommand('copy');
      alert('Texto copiado al portapapeles');
    } catch {
      alert('Error al copiar, selecciona manualmente');
    }
  });
</script>

</body>
</html>
