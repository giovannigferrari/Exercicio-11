<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>10Composição de Metal e Ametal</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
        }
        .result {
            margin-top: 20px;
        }
        .container{
            align-items: center;
            align-content: center;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
    <h1>Composição de Metal e Ametal em uma Liga</h1>
    <label for="metalPercent">Informe a porcentagem de metal (%):</label>
    <input type="number" id="metalPercent" placeholder="Porcentagem de metal" step="0.01" />
    <br>
    <label for="ametalPercent">Informe a porcentagem de ametal (%):</label>
    <input type="number" id="ametalPercent" placeholder="Porcentagem de ametal" step="0.01" />
    <br>
    <button onclick="calcularComposicao()">Calcular Composição</button>
    <div class="result">
        <p><strong>Resultado:</strong> <span id="resultado"></span></p>
    </div>
    </div>
    <script>
        function calcularComposicao() {
            const metal = parseFloat(document.getElementById('metalPercent').value);
            const ametal = parseFloat(document.getElementById('ametalPercent').value);
            if (isNaN(metal) || isNaN(ametal)) {
                alert("Por favor, insira valores válidos para as porcentagens.");
                return;
            }
            const soma = metal + ametal;
            if (soma !== 100) {
                alert("A soma das porcentagens deve ser exatamente 100%.");
                return;
            }
            if (metal > 50) {
                document.getElementById('resultado').textContent = "A liga é predominantemente metálica.";
            } else if (ametal > 50) {
                document.getElementById('resultado').textContent = "A liga é predominantemente ametálica.";
            } else {
                document.getElementById('resultado').textContent = "A liga tem proporções iguais de metal e ametal.";
            }
        }
    </script>
</body>
</html>
