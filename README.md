<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Academia das Águias - Por Amor</title>
  <style>
    body { font-family: Arial; background: #f0f4ff; margin: 0; padding: 0; }
    header { background: #003366; color: white; padding: 20px; text-align: center; }
    .container { padding: 20px; max-width: 900px; margin: auto; }
    h1, h2 { color: #003366; }
    input[type="text"] { width: 100%; padding: 8px; margin-bottom: 10px; }
    button { padding: 10px 20px; background: #003366; color: white; border: none; cursor: pointer; }
    button:hover { background: #0055aa; }
    .hidden { display: none; }
    footer { background: #003366; color: white; padding: 10px; text-align: center; margin-top: 40px; }
  </style>
</head>
<body>

<header>
  <h1>Academia das Águias</h1>
  <p>Igreja Por Amor</p>
</header>

<div class="container">
  <h2>Módulo 1 - Liderar é Influenciar</h2>
  <p><strong>Pergunta 1:</strong> O que é liderança segundo o curso?</p>
  <input type="text" id="q1">

  <p><strong>Pergunta 2:</strong> Cite uma atitude de um líder de sucesso:</p>
  <input type="text" id="q2">

  <button onclick="finalizarExercicio()">Finalizar Exercício</button>

  <div id="formulario" class="hidden">
    <h2>Formulário de Conclusão</h2>
    <p>Preencha seus dados para confirmar sua conclusão:</p>
    <input type="text" id="nome" placeholder="Seu nome">
    <input type="text" id="telefone" placeholder="Seu telefone com DDD">
    <input type="text" id="instagram" placeholder="Seu Instagram">

    <button onclick="enviarWhatsapp()">Enviar Confirmação</button>
  </div>
</div>

<footer>
  <p>&copy; 2025 Igreja Por Amor - Academia das Águias</p>
</footer>

<script>
function finalizarExercicio() {
  const r1 = document.getElementById('q1').value.trim();
  const r2 = document.getElementById('q2').value.trim();

  if (r1 === "" || r2 === "") {
    alert("Por favor, responda todas as perguntas.");
    return;
  }

  alert("Parabéns! Você concluiu o exercício. Agora preencha seus dados.");
  document.getElementById('formulario').classList.remove('hidden');
}

function enviarWhatsapp() {
  const nome = document.getElementById('nome').value.trim();
  const telefone = document.getElementById('telefone').value.trim();
  const instagram = document.getElementById('instagram').value.trim();

  if (nome === "" || telefone === "" || instagram === "") {
    alert("Por favor, preencha todos os campos.");
    return;
  }

  const mensagem = `✅ *Conclusão do módulo - Academia das Águias*\n\n👤 Nome: ${nome}\n📱 Telefone: ${telefone}\n📸 Instagram: ${instagram}\n\nConcluiu o módulo com sucesso!`;

  const numero = '5561986298041'; // Número da igreja (com DDI)
  const link = `https://wa.me/${numero}?text=${encodeURIComponent(mensagem)}`;

  window.open(link, '_blank');
}
</script>

</body>
</html>
