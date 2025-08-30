<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Estoque de Plantas - Horta</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #f0f5f1;
      margin: 0;
      padding: 20px;
    }

    h1 {
      text-align: center;
      color: #2f6d3b;
    }

    form {
      max-width: 800px;
      margin: auto;
      background-color: #ffffff;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    label {
      display: block;
      margin-bottom: 6px;
      font-weight: bold;
      color: #3e3e3e;
    }

    input, select, textarea {
      width: 100%;
      padding: 10px;
      margin-bottom: 20px;
      border: 1px solid #ccc;
      border-radius: 6px;
      box-sizing: border-box;
    }

    textarea {
      resize: vertical;
    }

    button {
      background-color: #4CAF50;
      color: white;
      padding: 12px 20px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-size: 16px;
    }

    button:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>

  <h1>Registro de Estoque da Horta</h1>

  <form>

    <label for="data">Data da Coleta de Informações</label>
    <input type="date" id="data" name="data" required>

    <label for="gleba">Gleba</label>
    <select id="gleba" name="gleba" required>
      <option value="">Selecione a Gleba</option>
    </select>

    <label for="linha">Linha</label>
    <input type="text" id="linha" name="linha" placeholder="Ex: Linha 1, Linha B..." required>

    <label for="especie">Espécie da Planta</label>
    <select id="especie" name="especie" required>
      <option value="">Selecione a Espécie</option>
      <option>Alface Americana</option>
      <option>Alface Crespa</option>
      <option>Alface Roxa</option>
      <option>Alface Mimosa</option>
      <option>Acelga Chinesa</option>
      <option>Rúcula</option>
      <option>Salsa</option>
      <option>Couve</option>
      <option>Coentro</option>
      <option>Cebolinha</option>
    </select>

    <label for="colhidas">Mudas Colhidas</label>
    <input type="number" id="colhidas" name="colhidas" min="0" required>

    <label for="descartadas">Mudas Descartadas</label>
    <input type="number" id="descartadas" name="descartadas" min="0" required>

    <label for="doadas">Mudas Doadas</label>
    <input type="number" id="doadas" name="doadas" min="0" required>

    <label for="responsavel">Responsável pelo Registro</label>
    <input type="text" id="responsavel" name="responsavel" required>

    <label for="obs">Observações</label>
    <textarea id="obs" name="obs" rows="4" placeholder="Anote pragas, clima, status das mudas, etc..."></textarea>

    <button type="submit">Salvar Registro</button>
  </form>

  <script>
    // Preenche automaticamente a data com hoje
    const dataHoje = new Date().toISOString().split('T')[0];
    document.getElementById('data').value = dataHoje;

    // Preenche o nome do responsável automaticamente (mas editável)
    document.getElementById('responsavel').value = "";

    // Gera 18 glebas automaticamente
    const glebaSelect = document.getElementById("gleba");
    for (let i = 1; i <= 18; i++) {
      const option = document.createElement("option");
      option.value = `Gleba ${i}`;
      option.textContent = `Gleba ${i}`;
      glebaSelect.appendChild(option);
    }
  </script>

</body>
</html>
