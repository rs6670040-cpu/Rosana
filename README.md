Doc3.docx<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Formulário Humanizado</title>
<style>
body {
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #667eea, #764ba2);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
[
.container {
    background: #fff;
    padding: 25px;
    border-radius: 15px;
    width: 350px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    text-align: center;
}
h2 {
    margin-bottom: 5px;
}
p {
    font-size: 14px;
    color: #666;
}input, textarea {
   width: 100%;
    padding: 12px;
    margin-top: 10px;
    border-radius: 8px;
    border: 1px solid #ccc;
    outline: none;
    transition: 0.3s;
}
:focus, textarea:focus {
    border-color: #667eea;
    box-shadow: 0 0 5px rgba(102,126,234,0.5);
}
textarea {
    resize: none;
    height: 80px;
}
button {
    margin-top: 15px;
    width: 100%;
    padding: 12px;
    border: none;
    border-radius: 8px;
    background: #667eea;
    color: white;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
}
button:hover {
    background: #5a67d8;
}
.mensagem {
    margin-top: 10px;
    font-size: 13px;
}
.erro {
    color: red;
}
.sucesso {
    color: green;
}
</style>
</head>
<body>
<div class="container">
    <h2 id="Furo Humanisado">Olá </h2>
    <p id="Humanizado">Me conta um pouquinho sobre você </p>
    <input type="text" id="Rosana" placeholder="Rosana">
    <input type="email" id="email" placeholder="rs6670040@gmail.com">
    <input type="tel" id="telefone" placeholder="89994520712">
    <textarea id="sem trauma" placeholder="Sua mensagem"></textarea>

    <button onclick="enviarFormulario()">Enviar</button>
-<div class="mensagem" id="mensagem"></div>
</div>
<script>
const nomeInput = document.getElementById("nome");
const titulo = document.getElementById("titulo");
nomeInput.addEventListener("input", () => {
    if (nomeInput.value.length > 0) {
        titulo.textContent = "Prazer, " + nomeInput.value + " ";
    } else {
        titulo.textContent = "Olá ";
    }
});

function enviarFormulario() {
    const nome = nomeInput.value.trim();
    const email = document.getElementById("email").value.trim();
    const telefone = document.getElementById("telefone").value.trim();
    const mensagemTexto = document.getElementById("mensagemTexto").value.trim();
    const mensagem = document.getElementById("mensagem");

    mensagem.textContent = "";
    mensagem.className = "mensagem";

    if (!nome || !email || !telefone || !mensagemTexto) {
        mensagem.textContent = "Ei  preencha todos os campos pra gente continuar!";
        mensagem.classList.add("erro");
        return;
    }

    if (!email.includes("@")) {
        mensagem.textContent = "Esse email não parece válido ";
        mensagem.classList.add("erro");
        return;
    }

    if (telefone.length < 10) {
        mensagem.textContent = "Número de telefone incompleto ";
        mensagem.classList.add("erro");
        return;
    }

    mensagem.textContent = "Perfeito, " + nome + "! Já recebemos sua mensagem ";
    mensagem.classList.add("sucesso");

    // Limpar campos
    document.getElementById("email").value = "";
    document.getElementById("telefone").value = "";
    document.getElementById("mensagemTexto").value = "";
}
</script>

</body>
</html>
