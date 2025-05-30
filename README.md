<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Academia das Águias - Por Amor</title>
    <style>
        body {
            background-color: #f4f9ff;
            font-family: Arial, sans-serif;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #0057b8;
            color: white;
            padding: 20px;
            text-align: center;
        }
        main {
            max-width: 800px;
            margin: 30px auto;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px #ccc;
        }
        h1, h2 {
            color: #0057b8;
        }
        label {
            display: block;
            margin-top: 15px;
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            margin-top: 20px;
            padding: 10px 20px;
            background-color: #0057b8;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #003d80;
        }
        .content {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<header>
    <h1>Academia das Águias - Por Amor</h1>
</header>

<main>
    <h2>Estudo - Liderar é Influenciar</h2>
    <div class="content">
        <p><strong>Reflexão:</strong></p>
        <p>Como está sua influência com:</p>
        <ul>
            <li>As pessoas acima de você?</li>
            <li>As pessoas na mesma posição?</li>
            <li>As pessoas sob sua liderança?</li>
        </ul>
        <p>Preencha abaixo suas respostas e confirme sua conclusão.</p>
    </div>

    <form id="form">
        <label>Nome Completo:
            <input type="text" id="nome" required>
        </label>
        <label>Telefone com DDD:
            <input type="text" id="telefone" placeholder="Ex: 61999999999" required>
        </label>

        <label>Como está sua influência com quem está acima de você?
            <textarea id="acima" rows="3" required></textarea>
        </label>
        <label>Com quem está na mesma posição?
            <textarea id="mesmo" rows="3" required></textarea>
        </label>
        <label>Com quem está abaixo de você?
            <textarea id="abaixo" rows="3" required></textarea>
        </label>

        <button type="button" onclick="enviarWhatsapp()">Concluir e Enviar no WhatsApp</button>
    </form>
</main>

<script>
    function enviarWhatsapp() {
        const nome = document.getElementById('nome').value.trim();
        const telefone = document.getElementById('telefone').value.trim();
        const acima = document.getElementById('acima').value.trim();
        const mesmo = document.getElementById('mesmo').value.trim();
        const abaixo = document.getElementById('abaixo').value.trim();

        if (!nome || !telefone || !acima || !mesmo || !abaixo) {
            alert('Por favor, preencha todos os campos.');
            return;
        }

        const numeroEnvio = '5561986298041'; // Número que irá receber no WhatsApp
        const mensagem = `✅ *Confirmação de Conclusão - Academia das Águias* ✅

👤 *Nome:* ${nome}
📱 *Telefone:* ${telefone}

📝 *Avaliação de Influência:*
- Acima: ${acima}
- Mesmo nível: ${mesmo}
- Abaixo: ${abaixo}

🔔 *Deus te abençoe!*`;

        const url = `https://wa.me/${numeroEnvio}?text=${encodeURIComponent(mensagem)}`;
        window.open(url, '_blank');
    }
</script>

</body>
</html>
