<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LUMINA 5s - Análise de Ambiente</title>
    <!-- Inclui o Tailwind CSS para um design rápido e responsivo -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Fonte Inter para tipografia moderna -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Orbitron:wght[700]&display=swap" rel="stylesheet">
    <!-- Ícones para melhorar a comunicação visual -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" xintegrity="sha512-ieY5r/p9O9+2F5fLq8z5F8w/A3y5r5+rQ9+2+A+n5O+a+k5P/w5bT+W+k6s6F5fFfA8P9" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <style>
        /* Define a paleta de cores e fontes customizadas */
        :root {
            --color-bg-primary: #0a0a0a;
            --color-bg-secondary: #16161a;
            --color-card: #1f1f26;
            --color-text-primary: #e4e4e7;
            --color-text-secondary: #a1a1aa;
            --color-accent-purple: #8b5cf6;
            --color-accent-green: #10b981;
            --color-accent-blue: #3b82f6;
            --color-accent-red: #ef4444;
            --color-accent-yellow: #f59e0b;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--color-bg-primary);
            color: var(--color-text-primary);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 1rem;
            box-sizing: border-box;
            transition: background-color 0.3s ease;
        }

        .container {
            background-color: var(--color-bg-secondary);
            border-radius: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            padding: 2.5rem;
            max-width: 650px;
            width: 100%;
            text-align: center;
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            transition: all 0.3s ease;
        }

        /* Efeito da logo e tipografia */
        .logo {
            font-family: 'Orbitron', sans-serif;
            font-size: 3rem;
            font-weight: 700;
            text-shadow: 0 0 15px rgba(139, 92, 246, 0.8), 0 0 30px rgba(139, 92, 246, 0.6);
            margin-bottom: 1rem;
            background: linear-gradient(90deg, var(--color-text-primary) 0%, var(--color-accent-purple) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .logo .five {
            color: var(--color-accent-green);
        }
        .logo .s {
            color: var(--color-accent-purple);
        }

        /* Estilo dos cards/seções */
        .card {
            background-color: var(--color-card);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 1.5rem;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 20px rgba(0, 0, 0, 0.3);
        }

        /* Vídeo e Canvas com bordas suaves */
        video, canvas {
            width: 100%;
            max-width: 100%;
            height: auto;
            border-radius: 1rem;
            background-color: #2d3748;
            margin: 0 auto;
            object-fit: cover;
            border: 2px solid var(--color-accent-purple);
            box-shadow: 0 0 10px rgba(139, 92, 246, 0.5);
        }

        /* Botões com gradiente e efeitos de hover */
        button {
            padding: 1rem 2rem;
            border-radius: 1.5rem;
            font-weight: 600;
            transition: all 0.2s ease-in-out;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            font-size: 1rem;
            border: none;
        }
        button:hover:not(:disabled) {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        }
        button:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .btn-primary {
            background-image: linear-gradient(45deg, var(--color-accent-blue), var(--color-accent-purple));
            color: white;
        }
        .btn-primary:hover:not(:disabled) {
            background-image: linear-gradient(45deg, #2563eb, #7c3aed);
        }

        .btn-secondary {
            background-color: #4a5568;
            color: white;
        }
        .btn-secondary:hover:not(:disabled) {
            background-color: #6b7280;
        }

        .btn-success {
            background-image: linear-gradient(45deg, var(--color-accent-green), #059669);
            color: white;
        }
        .btn-success:hover:not(:disabled) {
            background-image: linear-gradient(45deg, #059669, #047857);
        }
        
        .btn-completed {
            background-image: linear-gradient(45deg, var(--color-accent-purple), #7c3aed);
            color: white;
        }
        .btn-completed:hover:not(:disabled) {
            background-image: linear-gradient(45deg, #7c3aed, #6d28d9);
        }

        .btn-back {
            background-image: linear-gradient(45deg, var(--color-accent-yellow), #d97706);
            color: white;
        }
        .btn-back:hover:not(:disabled) {
            background-image: linear-gradient(45deg, #d97706, #b45309);
        }

        .btn-whatsapp {
            background-color: #25d366;
            color: white;
        }
        .btn-whatsapp:hover:not(:disabled) {
            background-color: #128c7e;
        }

        /* Campo de input */
        .input-field {
            padding: 1rem;
            border: 2px solid var(--color-accent-purple);
            border-radius: 1.5rem;
            width: 100%;
            box-sizing: border-box;
            font-size: 1rem;
            background-color: var(--color-bg-secondary);
            color: var(--color-text-primary);
            transition: border-color 0.2s ease;
        }
        .input-field:focus {
            outline: none;
            border-color: var(--color-accent-blue);
            box-shadow: 0 0 10px rgba(59, 130, 246, 0.5);
        }
        .input-field::placeholder {
            color: var(--color-text-secondary);
        }

        /* Estilo das mensagens */
        .message-box {
            font-size: 1.1rem;
            border-radius: 1rem;
            padding: 1.5rem;
            margin-top: 1.5rem;
            text-align: left;
            word-wrap: break-word;
            border-left: 5px solid;
            display: flex;
            align-items: flex-start;
            gap: 1rem;
            background-color: var(--color-card);
        }
        .message-box i {
            font-size: 1.5rem;
            line-height: 1;
        }
        .message-box.positive {
            border-color: var(--color-accent-green);
            color: var(--color-accent-green);
        }
        .message-box.negative {
            border-color: var(--color-accent-red);
            color: var(--color-accent-red);
        }
        .message-box.info {
            border-color: var(--color-accent-blue);
            color: var(--color-accent-blue);
        }

        /* Spinner de carregamento */
        .loading-spinner {
            border: 4px solid rgba(255, 255, 255, 0.1);
            border-left-color: var(--color-accent-blue);
            border-radius: 50%;
            width: 32px;
            height: 32px;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Classes utilitárias */
        .hidden {
            display: none;
        }
        .text-lg {
            font-size: 1.125rem;
        }

        /* Estilo dos contadores e recompensas */
        .counter-box {
            background-color: #10322d;
            border: 1px solid var(--color-accent-green);
            border-radius: 1rem;
            padding: 1rem;
            margin-top: 1rem;
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--color-text-primary);
        }
        .reward-box {
            background-color: #2b1d68;
            border: 1px solid var(--color-accent-purple);
            border-radius: 1rem;
            padding: 1.5rem;
            margin-top: 1rem;
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--color-text-primary);
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.02); opacity: 0.9; }
            100% { transform: scale(1); opacity: 1; }
        }

        /* Estilo do modal customizado */
        #custom-modal .modal-content {
            background-color: var(--color-card);
            border-radius: 1rem;
            box-shadow: 0 10px 20px rgba(0,0,0,0.4);
        }
        .checklist-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 1rem;
            padding: 0.75rem 1rem;
            background-color: rgba(255, 255, 255, 0.05);
            border-radius: 0.75rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                LUMINA<span class="five">5</span><span class="s">s</span>
            </div>
            <p class="text-gray-400 text-lg">
                Sua ferramenta para uma análise 5S eficiente e gamificada.
            </p>
        </header>

        <!-- Seção para a Permissão da Câmera -->
        <div id="permission-section" class="card">
            <h2 class="text-2xl font-bold mb-4 text-purple-400">Permissão de Acesso</h2>
            <p class="text-gray-300 text-lg mb-6">
                Para usar a análise de ambiente, precisamos acessar sua câmera.
                Por favor, clique em "Permitir" quando solicitado.
            </p>
            <button id="request-permission-button" class="btn-primary w-full">
                <i class="fas fa-camera"></i> Permitir Câmera
            </button>
        </div>

        <!-- Seção de Introdução e Contador (Visível após a permissão) -->
        <div id="intro-section" class="card hidden">
            <h2 class="text-2xl font-bold mb-4">Bem-vindo(a) à Plataforma 5S</h2>
            <p class="text-gray-300 text-lg mb-6">
                Utilize a plataforma para registrar sua autoavaliação 5S diária.
            </p>
            
            <!-- Contador de Dias Visível -->
            <div id="days-counter-box" class="counter-box mb-6 hidden">
                <span class="font-bold text-xl">
                    <i class="fas fa-check-circle mr-2 text-green-400"></i>Dias de Organização Contínua: <span id="days-count">0</span>
                </span>
                <p id="reward-countdown" class="text-sm mt-2 text-gray-400"></p>
            </div>
            
            <button id="start-button" class="btn-primary w-full">
                <i class="fas fa-play"></i> Iniciar
            </button>
        </div>
        
        <!-- Seção de Login (Simulado) -->
        <div id="login-section" class="card hidden">
            <h2 class="text-2xl font-bold mb-4 text-purple-400">1. Entrada do Funcionário</h2>
            <input type="text" id="employee-name" placeholder="Nome do Funcionário" class="input-field mb-4">
            <div class="flex flex-col md:flex-row gap-4">
                 <button id="start-internal-work" class="btn-primary flex-grow">
                    <i class="fas fa-user-check"></i> Iniciar Trabalho Interno
                </button>
                <button id="external-work-button" class="btn-secondary flex-grow">
                    <i class="fas fa-briefcase"></i> Trabalho Externo
                </button>
            </div>
            <div id="login-message" class="message-box mt-4 hidden positive">
                <i id="login-message-icon" class="fas fa-check-circle"></i>
                <p id="login-message-text"></p>
            </div>
        </div>

        <!-- Nova seção para Trabalho Externo -->
        <div id="external-work-section" class="card hidden">
            <h2 class="text-2xl font-bold mb-4 text-purple-400">Trabalho Externo</h2>
            <p class="text-gray-300 text-lg mb-4">Por favor, insira o código de confirmação enviado ao seu gestor para iniciar o ciclo.</p>
            <input type="text" id="manager-code-input" placeholder="Código de Confirmação" class="input-field mb-4">
            <div class="flex flex-col md:flex-row gap-4">
                <!-- Botão para o WhatsApp do gestor -->
                <a href="https://wa.me/5521980595904" target="_blank" class="flex-grow no-underline">
                    <button class="btn-whatsapp w-full">
                        <i class="fab fa-whatsapp"></i> WhatsApp do Gestor
                    </button>
                </a>
                <button id="confirm-external-work" class="btn-primary flex-grow">
                    <i class="fas fa-paper-plane"></i> Confirmar
                </button>
                <button id="back-to-login" class="btn-back flex-grow">
                    <i class="fas fa-arrow-left"></i> Voltar
                </button>
            </div>
            <div id="external-work-message" class="message-box mt-4 hidden info">
                <i id="external-work-message-icon" class="fas fa-info-circle"></i>
                <p id="external-work-message-text"></p>
            </div>
        </div>

        <!-- Nova Seção de Autoavaliação com Checklist -->
        <div id="self-evaluation-section" class="card hidden">
            <h2 class="text-2xl font-bold mb-4 text-purple-400">Avaliação Diária 5S</h2>
            <p class="text-gray-300 text-lg mb-6">
                Responda com sinceridade às perguntas abaixo para registrar seu progresso.
            </p>
            <div id="checklist-container">
                <div class="checklist-item">
                    <p class="text-left font-semibold">1. Classificação (Seiri): Descartei itens desnecessários da minha área de trabalho?</p>
                    <div>
                        <input type="radio" id="seiri-sim" name="seiri" value="Sim" class="mr-2">
                        <label for="seiri-sim">Sim</label>
                        <input type="radio" id="seiri-nao" name="seiri" value="Não" class="ml-4 mr-2">
                        <label for="seiri-nao">Não</label>
                    </div>
                </div>
                <div class="checklist-item">
                    <p class="text-left font-semibold">2. Organização (Seiton): Cada item está em seu lugar correto e identificado?</p>
                    <div>
                        <input type="radio" id="seiton-sim" name="seiton" value="Sim" class="mr-2">
                        <label for="seiton-sim">Sim</label>
                        <input type="radio" id="seiton-nao" name="seiton" value="Não" class="ml-4 mr-2">
                        <label for="seiton-nao">Não</label>
                    </div>
                </div>
                <div class="checklist-item">
                    <p class="text-left font-semibold">3. Limpeza (Seiso): Meu ambiente de trabalho está limpo e sem resíduos?</p>
                    <div>
                        <input type="radio" id="seiso-sim" name="seiso" value="Sim" class="mr-2">
                        <label for="seiso-sim">Sim</label>
                        <input type="radio" id="seiso-nao" name="seiso" value="Não" class="ml-4 mr-2">
                        <label for="seiso-nao">Não</label>
                    </div>
                </div>
                <div class="checklist-item">
                    <p class="text-left font-semibold">4. Padronização (Seiketsu): As regras de organização e limpeza estão sendo seguidas?</p>
                    <div>
                        <input type="radio" id="seiketsu-sim" name="seiketsu" value="Sim" class="mr-2">
                        <label for="seiketsu-sim">Sim</label>
                        <input type="radio" id="seiketsu-nao" name="seiketsu" value="Não" class="ml-4 mr-2">
                        <label for="seiketsu-nao">Não</label>
                    </div>
                </div>
                <div class="checklist-item">
                    <p class="text-left font-semibold">5. Disciplina (Shitsuke): Promovo ativamente a melhoria contínua e a manutenção dos 5S?</p>
                    <div>
                        <input type="radio" id="shitsuke-sim" name="shitsuke" value="Sim" class="mr-2">
                        <label for="shitsuke-sim">Sim</label>
                        <input type="radio" id="shitsuke-nao" name="shitsuke" value="Não" class="ml-4 mr-2">
                        <label for="shitsuke-nao">Não</label>
                    </div>
                </div>
            </div>
            <button id="submit-checklist-button" class="btn-primary w-full mt-4">
                <i class="fas fa-check-circle"></i> Enviar Avaliação
            </button>
        </div>

        <!-- Nova Seção de Resumo e Opções Pós-Checklist -->
        <div id="daily-summary-section" class="card hidden">
            <h2 class="text-2xl font-bold mb-4 text-green-400">Avaliação do Dia</h2>
            <div id="summary-message" class="message-box positive hidden">
                <i id="summary-icon" class="fas fa-thumbs-up"></i>
                <p id="summary-text"></p>
            </div>
            <div class="flex flex-col md:flex-row gap-4 mt-6">
                 <button id="conclude-day-button" class="btn-completed flex-grow">
                    <i class="fas fa-calendar-check"></i> Finalizar o Dia
                </button>
                <button id="improve-environment-button" class="btn-secondary flex-grow">
                    <i class="fas fa-camera"></i> Melhorar Ambiente
                </button>
                <button id="show-tips-button" class="btn-success flex-grow">
                    <i class="fas fa-lightbulb"></i> Ver Dicas de Organização
                </button>
                 <button id="show-health-tips-button" class="btn-primary flex-grow">
                    <i class="fas fa-heartbeat"></i> Ver Dicas de Saúde
                </button>
            </div>
        </div>

        <!-- Nova Seção de Dicas de Organização Fixas -->
        <div id="fixed-suggestions-section" class="card hidden">
            <h2 class="text-2xl font-bold mb-4 text-blue-400">Dicas de Organização</h2>
            <p class="text-gray-300 text-lg mb-6">
                Aqui estão algumas sugestões gerais para manter seu ambiente organizado.
            </p>
            <ul id="fixed-suggestions-list" class="list-disc list-inside text-gray-300 text-left pl-4"></ul>
            <button id="back-from-tips-button" class="btn-back w-full mt-4">
                <i class="fas fa-arrow-left"></i> Voltar
            </button>
        </div>

        <!-- Nova Seção de Dicas de Saúde e Bem-Estar -->
        <div id="health-tips-section" class="card hidden">
            <h2 class="text-2xl font-bold mb-4 text-purple-400">Dicas de Saúde e Bem-Estar</h2>
            <p class="text-gray-300 text-lg mb-6">
                Lembretes importantes para cuidar da sua saúde no ambiente de trabalho.
            </p>
            <ul id="health-tips-list" class="list-disc list-inside text-gray-300 text-left
