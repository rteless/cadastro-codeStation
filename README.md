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
    <div style="border: 1px solid #ccc; padding: 16px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>📌 Atenção:</strong><br>
  Este projeto está em desenvolvimento. Contribuições são bem-vindas!
</div>
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
      <p>📨 Dados enviados com sucesso!</p>
      <button onclick="fecharModal()">OK</button>
    </div>
  </div>

  <script>
    const form = document.getElementById('cadastroForm');
    const btnEnviar = document.getElementById('btnEnviar');
    const modal = document.getElementById('modalSucesso');

    const campos = [
      'nome', 'dataNascimento', 'cpf', 'email', 'telefone',
      'rua', 'numero', 'bairro', 'cidade', 'estado', 'cep',
      'genero', 'escolaridade', 'area', 'comoConheceu'
    ];

    campos.forEach(id => {
      document.getElementById(id).addEventListener('input', validarFormulario);
    });

    function validarFormulario() {
      const todosPreenchidos = campos.every(id => {
        const valor = document.getElementById(id).value.trim();
        return valor !== '';
      });

      const emailValido = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(document.getElementById('email').value);
      const cpfValido = /^\d{11}$/.test(document.getElementById('cpf').value);
      const telValido = /^\d{10,11}$/.test(document.getElementById('telefone').value);
      const cepValido = /^\d{8}$/.test(document.getElementById('cep').value);

      if (todosPreenchidos && emailValido && cpfValido && telValido && cepValido) {
        btnEnviar.disabled = false;
      } else {
        btnEnviar.disabled = true;
      }
    }

    form.addEventListener('submit', function(e) {
      e.preventDefault();
      modal.style.display = 'flex';
      form.reset();
      btnEnviar.disabled = true;
    });

    function fecharModal() {
      modal.style.display = 'none';
    }
  </script>
</body>
</html>

