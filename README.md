<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Inovação CodeStation - Escola de Tecnologia e Desenvolvimento</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      max-width: 700px;
      margin: auto;
      background-color: #f5f5f5;
    }
    h1 {
      text-align: center;
      color: #333;
    }
    label {
      display: block;
      margin-top: 10px;
    }
    input, select {
      width: 100%;
      padding: 8px;
      margin-top: 4px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
    }
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(0,0,0,0.5);
      justify-content: center;
      align-items: center;
    }
    .modal-content {
      background: white;
      padding: 20px;
      border-radius: 6px;
      text-align: center;
    }
  </style>
</head>
<body>

  <h1>Inovação CodeStation - Escola de Tecnologia e Desenvolvimento</h1>

  <form id="cadastroForm">
    <label>Nome completo:
      <input type="text" id="nome" required>
    </label>
    <label>Data de nascimento:
      <input type="date" id="dataNascimento" required>
    </label>
    <label>CPF:
      <input type="text" id="cpf" required>
    </label>
    <label>E-mail:
      <input type="email" id="email" required>
    </label>
    <label>Telefone (com DDD):
      <input type="tel" id="telefone" required>
    </label>
    <label>Rua:
      <input type="text" id="rua" required>
    </label>
    <label>Número:
      <input type="text" id="numero" required>
    </label>
    <label>Bairro:
      <input type="text" id="bairro" required>
    </label>
    <label>Cidade:
      <input type="text" id="cidade" required>
    </label>
    <label>Estado:
      <input type="text" id="estado" required>
    </label>
    <label>CEP:
      <input type="text" id="cep" required>
    </label>
    <label>Gênero:
      <select id="genero" required>
        <option value="">Selecione</option>
        <option value="masculino">Masculino</option>
        <option value="feminino">Feminino</option>
        <option value="outro">Outro</option>
      </select>
    </label>
    <label>Escolaridade:
      <input type="text" id="escolaridade" required>
    </label>
    <label>Área de interesse:
      <input type="text" id="area" required>
    </label>
    <label>Como conheceu a CodeStation?
      <input type="text" id="comoConheceu" required>
    </label>
    <button type="submit" id="btnEnviar" disabled>Enviar</button>
  </form>

  <div class="modal" id="modalSucesso">
    <div class="modal-content">
