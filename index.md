title: "Calculadoras Online"
description: "Um site simples com calculadoras úteis."
baseurl: ""
url: "https://seuusuario.github.io"
theme: minima

# Configuração do GitHub Pages
github:
  is_project_page: true

# Plugins necessários (se precisar de extras, adicionar aqui)
plugins:
  - jekyll-seo-tag

# Estrutura de pastas e arquivos
include:
  - _layouts
  - _includes
  - assets
  - calculadoras

# Páginas iniciais
index.md: |
  ---
  layout: default
  title: Calculadoras Online
  ---
  
  # Bem-vindo ao Calculadoras Online
  Aqui você encontra ferramentas úteis para o dia a dia:
  
  - [Calculadora de Salário Líquido](calculadoras/salario.html)
  - [Calculadora de IMC](calculadoras/imc.html)
  - [Calculadora de Ingestão de Água](calculadoras/agua.html)

# Layout padrão
_layouts/default.html: |
  <!DOCTYPE html>
  <html>
  <head>
      <meta charset="utf-8">
      <title>{{ page.title }}</title>
      <link rel="stylesheet" href="/assets/style.css">
  </head>
  <body>
      <header>
          <h1><a href="/">Calculadoras Online</a></h1>
      </header>
      <main>
          {{ content }}
      </main>
      <footer>
          <p>&copy; 2025 Calculadoras Online</p>
      </footer>
  </body>
  </html>

# CSS básico
assets/style.css: |
  body {
      font-family: Arial, sans-serif;
      max-width: 600px;
      margin: 20px auto;
      padding: 10px;
      text-align: center;
  }

# Calculadora de IMC
calculadoras/imc.html: |
  ---
  layout: default
  title: Calculadora de IMC
  ---
  
  <h2>Calculadora de IMC</h2>
  <p>Digite seu peso e altura para calcular o IMC.</p>
  
  <input type="number" id="peso" placeholder="Peso (kg)">
  <input type="number" id="altura" placeholder="Altura (m)">
  <button onclick="calcularIMC()">Calcular</button>
  <p id="resultado"></p>
  
  <script>
  function calcularIMC() {
      let peso = document.getElementById('peso').value;
      let altura = document.getElementById('altura').value;
      let imc = peso / (altura * altura);
      document.getElementById('resultado').innerText = "Seu IMC é " + imc.toFixed(2);
  }
  </script>
