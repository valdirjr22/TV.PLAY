<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TV PLAY - Gestão e Acesso</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* Variáveis CSS para o tema de cores */
        :root {
            --primary-blue: #007bff; /* Azul para destaque */
            --primary-blue-dark: #0056b3; /* Azul mais escuro para hover */
            --success-green: #2ecc71; /* Verde de sucesso */
            --success-green-dark: #27ae60; /* Verde mais escuro para hover */
            --danger-red: #dc3545; /* Vermelho para destaque */
            --danger-red-dark: #c82333; /* Vermelho mais escuro para hover */
            --light-gray-bg: #f0f2f5; /* Fundo cinza claro (menos usado agora) */
            --card-bg: #ffffff; /* Fundo branco para cartões */
            --text-dark: #212529; /* Texto escuro (quase preto) */
            --text-medium: #495057; /* Texto médio */
            --border-light: #dee2e6; /* Borda clara */
            --focus-ring: rgba(0, 123, 255, 0.25); /* Cor do anel de foco baseada no novo azul */
            --button-text: #ffffff; /* Cor do texto dos botões */
            --info-color: #17a2b8; /* Ciano/Turquesa para botões de informação */
            --info-color-dark: #138496; /* Ciano/Turquesa mais escuro para hover */
            /* Cores de fundo principal */
            --dark-bg-start: #000000; /* Preto puro */
            --dark-bg-end: #1a1a2e; /* Azul muito escuro */
        }

        /* Estilos globais do corpo */
        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(to bottom right, var(--dark-bg-start), var(--dark-bg-end)); /* Gradiente escuro */
            color: var(--text-medium);
            line-height: 1.6;
            min-height: 100vh; /* Garante que o gradiente cubra toda a altura */
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 2rem;
            box-sizing: border-box; /* Inclui padding no cálculo da largura/altura total */
        }

        /* Estilo do contêiner principal */
        .container {
            max-width: 1200px;
            width: 100%;
            margin: 0 auto; /* Centraliza o contêiner */
            padding: 1.5rem;
            background-color: var(--card-bg);
            border-radius: 8px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4); /* Sombra mais pronunciada e escura */
        }

        /* Estilos de títulos */
        h1, h2, h3, h4 {
            color: var(--text-dark);
            font-weight: 700;
            margin-bottom: 1rem;
        }

        h1 { font-size: 2.25rem; }
        h2 { font-size: 1.75rem; }
        h3 { font-size: 1.25rem; }

        /* Estilo de grupos de formulário */
        .form-group {
            margin-bottom: 1rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--text-dark);
        }

        /* Estilo de inputs e selects */
        input[type="text"],
        input[type="password"],
        input[type="number"],
        input[type="email"],
        select,
        textarea {
            width: 100%;
            padding: 0.75rem 1rem;
            border: 1px solid var(--border-light);
            border-radius: 6px;
            font-size: 1rem;
            color: var(--text-dark);
            background-color: #ffffff;
            transition: border-color 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        input[type="text"]:focus,
        input[type="password"]:focus,
        input[type="number"]:focus,
        input[type="email"]:focus,
        select:focus,
        textarea:focus {
            border-color: var(--primary-blue);
            box-shadow: 0 0 0 3px var(--focus-ring);
            outline: none;
        }

        /* Estilo para selects múltiplos */
        select[multiple] {
            min-height: 100px; /* Altura mínima para visualização de múltiplas opções */
            padding: 0.5rem;
            background-image: none; /* Remove a seta padrão */
            border: 1px solid var(--border-light);
            border-radius: 6px;
            font-size: 1rem;
            color: var(--text-dark);
        }

        select[multiple] option {
            padding: 0.5rem 0.75rem;
        }

        select[multiple] option:checked {
            background-color: var(--primary-blue);
            color: var(--button-text);
        }

        /* Adicionado para foco em selects múltiplos */
        select[multiple]:focus {
            border-color: var(--primary-blue);
            box-shadow: 0 0 0 3px var(--focus-ring), 0 0 8px rgba(52, 152, 219, 0.2); /* Adicionado sombra sutil */
            outline: none;
        }

        /* Estilo de botões base */
        button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 6px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.2s ease-in-out, transform 0.1s ease-in-out;
            color: var(--button-text);
        }

        /* Estilos de botões específicos */
        .btn-primary {
            background-color: var(--primary-blue);
        }

        .btn-primary:hover {
            background-color: var(--primary-blue-dark);
            transform: translateY(-1px);
        }

        .btn-success {
            background-color: var(--success-green);
        }

        .btn-success:hover {
            background-color: var(--success-green-dark);
            transform: translateY(-1px);
        }

        .btn-danger {
            background-color: var(--danger-red);
        }

        .btn-danger:hover {
            background-color: var(--danger-red-dark);
            transform: translateY(-1px);
        }

        .btn-info {
            background-color: var(--info-color);
        }

        .btn-info:hover {
            background-color: var(--info-color-dark);
            transform: translateY(-1px);
        }

        /* Estilo de caixas de mensagem */
        .message-box {
            padding: 1rem;
            border-radius: 6px;
            margin-bottom: 1rem;
            font-weight: 500;
            text-align: center;
        }

        .message-box.success {
            background-color: #d4edda;
            color: #155724;
            border-color: #c3e6cb;
        }

        .message-box.error {
            background-color: #f8d7da;
            color: #721c24;
            border-color: #f5c6cb;
        }

        .message-box.info {
            background-color: #d1ecf1;
            color: #0c5460;
            border-color: #bee5eb;
        }

        /* Classes de utilidade */
        .hidden {
            display: none !important;
        }

        .hidden-section {
            display: none;
        }

        /* Estilo do cabeçalho de seção */
        .section-header {
            border-bottom: 1px solid var(--border-light);
            padding-bottom: 1rem;
            margin-bottom: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .section-header h2 {
            margin-bottom: 0;
        }

        /* Estilo de tabelas */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
            background-color: var(--card-bg);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            border-radius: 8px;
            overflow: hidden; /* Garante que as bordas arredondadas sejam aplicadas */
        }

        th, td {
            text-align: left;
            padding: 12px 15px;
            border-bottom: 1px solid var(--border-light);
        }

        th {
            background-color: #e9ecef;
            color: var(--text-dark);
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.85rem;
        }

        tr:nth-child(even) {
            background-color: #f9f9f9;
        }

        tr:hover {
            background-color: #f0f0f0;
        }

        /* Estilo de células editáveis na tabela */
        .editable-cell {
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            width: 100%;
            box-sizing: border-box; /* Inclui padding e border no cálculo da largura/altura total */
        }
        .editable-cell:focus {
            border-color: var(--primary-blue);
            box-shadow: 0 0 0 2px var(--focus-ring);
        }

        /* Estilos para o modal de confirmação */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7); /* Fundo mais escuro para o modal */
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
        }

        .modal-content {
            background-color: var(--card-bg);
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5); /* Sombra mais forte para o modal */
            text-align: center;
            max-width: 400px;
            width: 90%;
            color: var(--text-dark); /* Garante que o texto do modal seja escuro */
        }

        .modal-content h3 {
            margin-top: 0;
            color: var(--text-dark);
        }

        .modal-buttons {
            margin-top: 1.5rem;
            display: flex;
            justify-content: center;
            gap: 1rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <section id="initialSelectionSection">
            <h1 class="text-3xl text-center mb-8">Bem-vindo ao TV PLAY</h1>
            <div class="max-w-md mx-auto bg-white p-10 rounded-lg shadow-2xl border border-gray-300"> <h2 class="text-3xl text-center mb-6 text-gray-800 font-bold">Escolha o Tipo de Acesso</h2> <div class="flex flex-col space-y-4">
                    <button id="adminLoginButton" class="btn-primary w-full py-3">Acesso Administrador</button>
                    <button id="userLoginButton" class="btn-info w-full py-3">Acesso Usuário</button>
                </div>
            </div>
        </section>

        <section id="adminLoginSection" class="hidden-section">
            <h1 class="text-3xl text-center mb-8">TV PLAY - Painel de Gestão</h1>
            <div class="max-w-md mx-auto bg-white p-10 rounded-lg shadow-2xl border border-gray-300"> <h2 class="text-3xl text-center mb-6 text-gray-800 font-bold">Login do Administrador</h2> <form id="adminLoginForm">
                    <div class="form-group">
                        <label for="adminUsername">Nome de Utilizador:</label>
                        <input type="text" id="adminUsername" name="adminUsername" required>
                    </div>
                    <div class="form-group">
                        <label for="adminPassword">Senha:</label>
                        <input type="password" id="adminPassword" name="adminPassword" required>
                    </div>
                    <div id="adminLoginMessage" class="message-box hidden" role="alert"></div>
                    <button type="submit" class="btn-primary w-full mt-4 py-3">Entrar</button>
                    <button type="button" id="backToInitialSelectionFromAdmin" class="btn-info w-full mt-2 py-3">Voltar</button>
                </form>
            </div>
        </section>

        <section id="userLoginSection" class="hidden-section">
            <h1 class="text-3xl text-center mb-8">TV PLAY - Acesso ao Usuário</h1>
            <div class="max-w-md mx-auto bg-white p-10 rounded-lg shadow-2xl border border-gray-300"> <h2 class="text-3xl text-center mb-6 text-gray-800 font-bold">Login do Usuário</h2> <form id="userLoginForm">
                    <div class="form-group">
                        <label for="userUsername">Nome de Utilizador:</label>
                        <input type="text" id="userUsername" name="userUsername" required>
                    </div>
                    <div class="form-group">
                        <label for="userPassword">Senha:</label>
                        <input type="password" id="userPassword" name="userPassword" required>
                    </div>
                    <div id="userLoginMessage" class="message-box hidden" role="alert"></div>
                    <button type="submit" class="btn-info w-full mt-4 py-3">Entrar</button>
                    <button type="button" id="backToInitialSelectionFromUser" class="btn-primary w-full mt-2 py-3">Voltar</button>
                </form>
            </div>
        </section>

        <section id="adminPanelSection" class="hidden-section">
            <header class="section-header">
                <h1 class="text-3xl">Painel de Gestão TV PLAY</h1>
                <p class="text-sm text-gray-600">ID de Utilizador Atual: <span id="userIdDisplay">Modo de Demonstração</span></p>
                <button id="adminLogoutButton" class="btn-danger">Sair</button>
            </header>

            <h2 class="text-2xl mt-8 mb-4">Adicionar Utilizador Manualmente</h2>
            <div class="bg-white p-6 rounded-lg shadow-md mb-8">
                <form id="addManualUserForm">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="form-group">
                            <label for="manualUsername">Nome de Utilizador:</label>
                            <input type="text" id="manualUsername" name="manualUsername" required>
                        </div>
                        <div class="form-group">
                            <label for="manualPassword">Senha:</label>
                            <input type="password" id="manualPassword" name="manualPassword" required>
                            <p id="passwordHint" class="text-xs text-gray-500 mt-1">Mínimo 6 caracteres, com pelo menos uma letra e um número.</p>
                        </div>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="form-group">
                            <label for="manualCredits">Créditos (cada 30 dias):</label>
                            <input type="number" id="manualCredits" name="manualCredits" min="1" value="1" required>
                            <p class="text-xs text-gray-500 mt-1">Cada crédito adiciona 30 dias à expiração do usuário.</p>
                        </div>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="form-group">
                            <label for="manualSelectCategory">Categoria(s) do Canal:</label>
                            <select id="manualSelectCategory" name="manualSelectCategory" multiple required>
                                </select>
                            <p class="text-base text-gray-600 mt-1 font-bold">Segure Ctrl (ou Cmd no Mac) para selecionar múltiplas categorias.</p>
                        </div>
                        <div class="form-group">
                            <label for="manualSelectChannel">Canal(is) a Associar:</label>
                            <select id="manualSelectChannel" name="manualSelectChannel" multiple disabled required>
                                <option value="">Selecione uma categoria primeiro</option>
                            </select>
                            <p class="text-base text-gray-600 mt-1 font-bold">Segure Ctrl (ou Cmd no Mac) para selecionar múltiplos canais.</p>
                        </div>
                    </div>
                    <div id="manualUserMessage" class="message-box hidden mt-4" role="alert"></div>
                    <button type="submit" class="btn-primary mt-4">Adicionar Utilizador</button>
                </form>
            </div>

            <h2 class="text-2xl mt-8 mb-4">Gerar Utilizador Automaticamente</h2>
            <div class="bg-white p-6 rounded-lg shadow-md mb-8">
                <form id="generateUserForm" class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="form-group">
                        <label for="genSelectCategory">Categoria do Canal:</label>
                        <select id="genSelectCategory" name="genSelectCategory" required>
                            </select>
                    </div>
                    <div class="form-group">
                        <label for="selectChannel">Canal a Associar:</label>
                        <select id="selectChannel" name="selectChannel" disabled required>
                            <option value="">Selecione uma categoria primeiro</option>
                        </select>
                    </div>
                    <div class="md:col-span-2">
                        <div id="userGenMessage" class="message-box hidden mt-4" role="alert"></div>
                        <button type="submit" class="btn-primary mt-4">Gerar Credenciais</button>
                    </div>
                </form>

                <div id="generatedCredentials" class="hidden bg-gray-100 p-6 rounded-lg mt-6 border border-gray-200">
                    <h3 class="text-xl font-semibold mb-3">Credenciais Geradas:</h3>
                    <p class="mb-2"><strong>Nome de Utilizador:</strong> <span id="displayUsername" class="font-mono text-blue-700"></span> <button class="copy-button ml-2 text-sm text-gray-600 hover:text-blue-500" data-target="displayUsername">Copiar</button></p>
                    <p class="mb-2"><strong>Senha:</strong> <span id="displayPassword" class="font-mono text-blue-700"></span> <button class="copy-button ml-2 text-sm text-gray-600 hover:text-blue-500" data-target="displayPassword">Copiar</button></p>
                    <p><strong>Data de Expiração:</strong> <span id="displayExpiryDate" class="font-mono text-blue-700"></span></p>
                </div>
            </div>

            <h2 class="text-2xl mt-8 mb-4">Utilizadores Gerados</h2>
            <div class="overflow-x-auto">
                <table id="userTable">
                    <thead>
                        <tr>
                            <th>Nome de Utilizador</th>
                            <th>Senha</th>
                            <th>Canal(is)</th>
                            <th>Categoria(s)</th>
                            <th>Créditos</th>
                            <th>Expiração</th>
                            <th>Criação</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="userTableBody">
                        <tr id="loadingUsers">
                            <td colspan="8" class="text-center text-gray-500 py-4">Carregando utilizadores... (Apenas para demonstração)</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <h2 class="text-2xl mt-8 mb-4">Gestão de Canais</h2>
            <div class="bg-white p-6 rounded-lg shadow-md mb-8">
                <h3 class="text-xl font-semibold mb-4">Adicionar Novo Canal (Apenas demonstração)</h3>
                <form id="addChannelForm" class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="form-group">
                        <label for="channelName">Nome do Canal:</label>
                        <input type="text" id="channelName" name="channelName" required>
                    </div>
                    <div class="form-group">
                        <label for="channelCategory">Categoria do Canal:</label>
                        <select id="channelCategory" name="channelCategory" required>
                            </select>
                    </div>
                    <div class="md:col-span-2">
                        <div id="channelMessage" class="message-box hidden mt-4" role="alert"></div>
                        <button type="submit" class="btn-success mt-4">Adicionar Canal</button>
                    </div>
                </form>

                <h3 class="text-xl font-semibold mb-4 mt-8">Canais Existentes</h3>
                <div id="channelList" class="max-h-64 overflow-y-auto border border-gray-200 p-4 rounded-md bg-gray-50">
                    <p class="text-gray-500 text-center">Carregando canais...</p>
                </div>
            </div>
        </section>

        <section id="userChannelsSection" class="hidden-section">
            <header class="section-header">
                <h1 class="text-3xl">Meus Canais TV PLAY</h1>
                <p class="text-sm text-gray-600">Bem-vindo(a), <span id="currentUserDisplay">Usuário!</span></p>
                <p class="text-sm text-gray-600">Vencimento: <span id="userExpiryDisplay">N/A</span></p>
                <button id="userLogoutButton" class="btn-danger">Sair</button>
            </header>

            <h2 class="text-2xl mt-8 mb-4">Canais Disponíveis</h2>
            <div class="overflow-x-auto">
                <table id="userChannelsTable">
                    <thead>
                        <tr>
                            <th>Canal</th>
                            <th>Categoria</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="userChannelsTableBody">
                        <tr>
                            <td colspan="3" class="text-center text-gray-500 py-4">Carregando seus canais...</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>
    </div>

    <div id="confirmationModal" class="modal-overlay hidden">
        <div class="modal-content">
            <h3 id="modalMessage" class="text-xl font-semibold mb-4"></h3>
            <div class="modal-buttons">
                <button id="modalConfirmBtn" class="btn-danger">Confirmar</button>
                <button id="modalCancelBtn" class="btn-info">Cancelar</button>
            </div>
        </div>
    </div>

    <script type="module">
        // Variáveis globais (simulação de dados, não persistente)
        const createdUsers = new Map(); // Map(username -> { password, channels, categories, expiryDate, createdAt, credits })
        let messageTimeout;
        let loggedInUser = null; // Para armazenar o usuário atualmente logado

        // Dados dos canais (centralizado para facilitar a gestão)
        const channelsData = [
            // Canais SD
            { id: "globo-sd", name: "Rede Globo", category: "Canais SD", streamUrl: "https://example.com/globo-sd" },
            { id: "record-sd", name: "Rede Record", category: "Canais SD", streamUrl: "https://example.com/record-sd" },
            { id: "band-sd", name: "Rede Bandeirantes", category: "Canais SD", streamUrl: "https://example.com/band-sd" },
            { id: "redetv-sd", name: "RedeTV!", category: "Canais SD", streamUrl: "https://example.com/redetv-sd" },
            { id: "sbt-sd", name: "SBT", category: "Canais SD", streamUrl: "https://example.com/sbt-sd" },
            { id: "cultura-sd", name: "TV Cultura", category: "Canais SD", streamUrl: "https://example.com/cultura-sd" },
            { id: "gazeta-sd", name: "TV Gazeta", category: "Canais SD", streamUrl: "https://example.com/gazeta-sd" },
            { id: "brasil-sd", name: "TV Brasil", category: "Canais SD", streamUrl: "https://example.com/brasil-sd" },
            { id: "recordnews-sd", name: "Record News", category: "Canais SD", streamUrl: "https://example.com/recordnews-sd" },
            { id: "rede21-sd", name: "Rede 21", category: "Canais SD", streamUrl: "https://example.com/rede21-sd" },
            { id: "aparecida-sd", name: "TV Aparecida", category: "Canais SD", streamUrl: "https://example.com/aparecida-sd" },
            { id: "nbr-sd", name: "TV NBR", category: "Canais SD", streamUrl: "https://example.com/nbr-sd" },
            { id: "escola-sd", name: "TV Escola", category: "Canais SD", streamUrl: "https://example.com/escola-sd" },
            { id: "camara-sd", name: "TV Câmara", category: "Canais SD", streamUrl: "https://example.com/camara-sd" },
            { id: "senado-sd", name: "TV Senado", category: "Canais SD", streamUrl: "https://example.com/senado-sd" },
            { id: "mtv-sd", name: "MTV Brasil", category: "Canais SD", streamUrl: "https://example.com/mtv-sd" },
            { id: "futura-sd", name: "Canal Futura", category: "Canais SD", streamUrl: "https://example.com/futura-sd" },
            { id: "redevida-sd", name: "Rede Vida", category: "Canais SD", streamUrl: "https://example.com/redevida-sd" },
            { id: "rbtv-sd", name: "RBTV (Rede Bahia)", category: "Canais SD", streamUrl: "https://example.com/rbtv-sd" },

            // Canais HD
            { id: "globo-hd", name: "Rede Globo", category: "Canais HD", streamUrl: "https://example.com/globo-hd" },
            { id: "record-hd", name: "Rede Record", category: "Canais HD", streamUrl: "https://example.com/record-hd" },
            { id: "band-hd", name: "Rede Bandeirantes", category: "Canais HD", streamUrl: "https://example.com/band-hd" },
            { id: "redetv-hd", name: "RedeTV!", category: "Canais HD", streamUrl: "https://example.com/redetv-hd" },
            { id: "sbt-hd", name: "SBT", category: "Canais HD", streamUrl: "https://example.com/sbt-hd" },
            { id: "cultura-hd", name: "TV Cultura", category: "Canais HD", streamUrl: "https://example.com/cultura-hd" },
            { id: "gazeta-hd", name: "TV Gazeta", category: "Canais HD", streamUrl: "https://example.com/gazeta-hd" },
            { id: "brasil-hd", name: "TV Brasil", category: "Canais HD", streamUrl: "https://example.com/brasil-hd" },
            { id: "recordnews-hd", name: "Record News", category: "Canais HD", streamUrl: "https://example.com/recordnews-hd" },
            { id: "aparecida-hd", name: "TV Aparecida", category: "Canais HD", streamUrl: "https://example.com/aparecida-hd" },
            { id: "redevida-hd", name: "Rede Vida", category: "Canais HD", streamUrl: "https://example.com/redevida-hd" },
            { id: "rbtv-hd", name: "RBTV (Rede Bahia)", category: "Canais HD", streamUrl: "https://example.com/rbtv-hd" },
            { id: "intertv-hd", name: "InterTV (afiliada da Rede Globo em Minas Gerais)", category: "Canais HD", streamUrl: "https://example.com/intertv-hd" },
            { id: "verdesmares-hd", name: "TV Verdes Mares (afiliada da Rede Globo no Ceará)", category: "Canais HD", streamUrl: "https://example.com/verdesmares-hd" },
            { id: "tvbahia-hd", name: "TV Bahia (afiliada da Rede Globo na Bahia)", category: "Canais HD", streamUrl: "https://example.com/tvbahia-hd" },
            { id: "tvliberal-hd", name: "TV Liberal (afiliada da Rede Globo no Pará)", category: "Canais HD", streamUrl: "https://example.com/tvliberal-hd" },
            { id: "tvcabobranco-hd", name: "TV Cabo Branco (afiliada da Rede Globo na Paraíba)", category: "Canais HD", streamUrl: "https://example.com/tvcabobranco-hd" },
            { id: "rpc-hd", name: "RPC (afiliada da Rede Globo no Paraná)", category: "Canais HD", streamUrl: "https://example.com/rpc-hd" },
            { id: "rbs-hd", name: "RBS TV (afiliada da Rede Globo no Rio Grande do Sul)", category: "Canais HD", streamUrl: "https://example.com/rbs-hd" },

            // Canais FULL HD
            { id: "globo-fullhd", name: "Rede Globo", category: "Canais FULLHD", streamUrl: "https://example.com/globo-fullhd" },
            { id: "record-fullhd", name: "Rede Record", category: "Canais FULLHD", streamUrl: "https://example.com/record-fullhd" },
            { id: "band-fullhd", name: "Rede Bandeirantes", category: "Canais FULLHD", streamUrl: "https://example.com/band-fullhd" },
            { id: "redetv-fullhd", name: "RedeTV!", category: "Canais FULLHD", streamUrl: "https://example.com/redetv-fullhd" },
            { id: "sbt-fullhd", name: "SBT", category: "Canais FULLHD", streamUrl: "https://example.com/sbt-fullhd" },
            { id: "cultura-fullhd", name: "TV Cultura", category: "Canais FULLHD", streamUrl: "https://example.com/cultura-fullhd" },

            // Canais 4K
            { id: "globo-4k", name: "Rede Globo", category: "Canais 4K", streamUrl: "https://example.com/globo-4k" },
            { id: "record-4k", name: "Rede Record", category: "Canais 4K", streamUrl: "https://example.com/record-4k" },
            { id: "band-4k", name: "Rede Bandeirantes", category: "Canais 4K", streamUrl: "https://example.com/band-4k" },
            { id: "redetv-4k", name: "RedeTV!", category: "Canais 4K", streamUrl: "https://example.com/redetv-4k" },
            { id: "sbt-4k", name: "SBT", category: "Canais 4K", streamUrl: "https://example.com/sbt-4k" },
            { id: "cultura-4k", name: "TV Cultura", category: "Canais 4K", streamUrl: "https://example.com/cultura-4k" },
            { id: "gazeta-4k", name: "TV Gazeta", category: "Canais 4K", streamUrl: "https://example.com/gazeta-4k" },
            { id: "brasil-4k", name: "TV Brasil", category: "Canais 4K", streamUrl: "https://example.com/brasil-4k" },
            { id: "recordnews-4k", name: "Record News", category: "Canais 4K", streamUrl: "https://example.com/recordnews-4k" },
            { id: "rede21-4k", name: "Rede 21", category: "Canais 4K", streamUrl: "https://example.com/rede21-4k" },
            { id: "aparecida-4k", name: "TV Aparecida", category: "Canais 4K", streamUrl: "https://example.com/aparecida-4k" },
            { id: "nbr-4k", name: "TV NBR", category: "Canais 4K", streamUrl: "https://example.com/nbr-4k" },
            { id: "escola-4k", name: "TV Escola", category: "Canais 4K", streamUrl: "https://example.com/escola-4k" },
            { id: "camara-4k", name: "TV Câmara", category: "Canais 4K", streamUrl: "https://example.com/camara-4k" },
            { id: "senado-4k", name: "TV Senado", category: "Canais 4K", streamUrl: "https://example.com/senado-4k" },
            { id: "mtv-4k", name: "MTV Brasil", category: "Canais 4K", streamUrl: "https://example.com/mtv-4k" },
            { id: "futura-4k", name: "Canal Futura", category: "Canais 4K", streamUrl: "https://example.com/futura-4k" },
            { id: "redevida-4k", name: "Rede Vida", category: "Canais 4K", streamUrl: "https://example.com/redevida-4k" },
            { id: "rbtv-4k", name: "RBTV (Rede Bahia)", category: "Canais 4K", streamUrl: "https://example.com/rbtv-4k" },
            { id: "intertv-4k", name: "InterTV (afiliada da Rede Globo em Minas Gerais)", category: "Canais 4K", streamUrl: "https://example.com/intertv-4k" },
            { id: "verdesmares-4k", name: "TV Verdes Mares (afiliada da Rede Globo no Ceará)", category: "Canais 4K", streamUrl: "https://example.com/verdesmares-4k" },
            { id: "tvbahia-4k", name: "TV Bahia (afiliada da Rede Globo na Bahia)", category: "Canais 4K", streamUrl: "https://example.com/tvbahia-4k" },
            { id: "tvliberal-4k", name: "TV Liberal (afiliada da Rede Globo no Pará)", category: "Canais 4K", streamUrl: "https://example.com/tvliberal-4k" },
            { id: "tvcabobranco-4k", name: "TV Cabo Branco (afiliada da Rede Globo na Paraíba) (4K)", category: "Canais 4K", streamUrl: "https://example.com/tvcabobranco-4k" },
            { id: "rpc-4k", name: "RPC (afiliada da Rede Globo no Paraná)", category: "Canais 4K", streamUrl: "https://example.com/rpc-4k" },
            { id: "rbs-4k", name: "RBS TV (afiliada da Rede Globo no Rio Grande do Sul)", category: "Canais 4K", streamUrl: "https://example.com/rbs-4k" },

            // Novos Canais e Categorias
            { id: "a&e", name: "A&E", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/ae" },
            { id: "amc", name: "AMC", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/amc" },
            { id: "axn", name: "AXN", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/axn" },
            { id: "canal-brasil", name: "Canal Brasil", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/canal-brasil" },
            { id: "cine-brasil-tv", name: "Cine Brasil TV", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/cine-brasil-tv" },
            { id: "cinemax", name: "Cinemax", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/cinemax" },
            { id: "comedy-central-brasil", name: "Comedy Central Brasil", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/comedy-central" },
            { id: "hbo", name: "HBO", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo" },
            { id: "hbo-2", name: "HBO 2", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo2" },
            { id: "hbo-family", name: "HBO Family", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo-family" },
            { id: "hbo-mundi", name: "HBO Mundi", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo-mundi" },
            { id: "hbo-plus", name: "HBO+", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo-plus" },
            { id: "hbo-pop", name: "HBO Pop", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo-pop" },
            { id: "hbo-signature", name: "HBO Signature", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo-signature" },
            { id: "hbo-xtreme", name: "HBO Xtreme", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/hbo-xtreme" },
            { id: "paramount-network", name: "Paramount Network", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/paramount-network" },
            { id: "prime-box-brasil", name: "Prime Box Brazil", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/prime-box" },
            { id: "sony-channel", name: "Sony Channel", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/sony-channel" },
            { id: "sony-movies", name: "Sony Movies", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/sony-movies" },
            { id: "space", name: "Space", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/space" },
            { id: "studio-universal", name: "Studio Universal", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/studio-universal" },
            { id: "tcm", name: "TCM", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/tcm" },
            { id: "tnt", name: "TNT", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/tnt" },
            { id: "tnt-novelas", name: "TNT Novelas", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/tnt-novelas" },
            { id: "tnt-series", name: "TNT Séries", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/tnt-series" },
            { id: "universal-tv", name: "Universal TV", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/universal-tv" },
            { id: "usa-network", name: "USA Network", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/usa-network" },
            { id: "warner-channel", name: "Warner Channel", category: "Canais Cinematográficos/Dramatúrgicos", streamUrl: "https://example.com/warner-channel" },

            { id: "espn", name: "ESPN", category: "Canais Esportivos", streamUrl: "https://example.com/espn" },
            { id: "sportv", name: "SporTV", category: "Canais Esportivos", streamUrl: "https://example.com/sportv" },
            { id: "fox-sports", name: "Fox Sports", category: "Canais Esportivos", streamUrl: "https://example.com/fox-sports" },
            { id: "bandsports", name: "BandSports", category: "Canais Esportivos", streamUrl: "https://example.com/bandsports" },

            { id: "globonews", name: "GloboNews", category: "Canais de Notícias", streamUrl: "https://example.com/globonews" },
            { id: "cnn-brasil", name: "CNN Brasil", category: "Canais de Notícias", streamUrl: "https://example.com/cnn-brasil" },
            { id: "bandnews", name: "BandNews", category: "Canais de Notícias", streamUrl: "https://example.com/bandnews" },
            { id: "bbc-news", name: "BBC News", category: "Canais de Notícias", streamUrl: "https://example.com/bbc-news" },

            { id: "discovery-kids", name: "Discovery Kids", category: "Canais Infantis", streamUrl: "https://example.com/discovery-kids" },
            { id: "cartoon-network", name: "Cartoon Network", category: "Canais Infantis", streamUrl: "https://example.com/cartoon-network" },
            { id: "disney-channel", name: "Disney Channel", category: "Canais Infantis", streamUrl: "https://example.com/disney-channel" },
            { id: "nickelodeon", name: "Nickelodeon", category: "Canais Infantis", streamUrl: "https://example.com/nickelodeon" },
            { id: "gloob", name: "Gloob", category: "Canais Infantis", streamUrl: "https://example.com/gloob" },
            { id: "boomerang", name: "Boomerang", category: "Canais Infantis", streamUrl: "https://example.com/boomerang" },

            { id: "gnt", name: "GNT", category: "Canais de Variedades", streamUrl: "https://example.com/gnt" },
            { id: "multishow", name: "Multishow", category: "Canais de Variedades", streamUrl: "https://example.com/multishow" },
            { id: "viva", name: "Viva", category: "Canais de Variedades", streamUrl: "https://example.com/viva" },
            { id: "e-channel", name: "E!", category: "Canais de Variedades", streamUrl: "https://example.com/e-channel" },

            { id: "national-geographic", name: "National Geographic", category: "Canais de Documentários", streamUrl: "https://example.com/national-geographic" },
            { id: "discovery-channel", name: "Discovery Channel", category: "Canais de Documentários", streamUrl: "https://example.com/discovery-channel" },
            { id: "animal-planet", name: "Animal Planet", category: "Canais de Documentários", streamUrl: "https://example.com/animal-planet" },

            { id: "tv-brasil-cultural", name: "TV Brasil", category: "Canais Culturais", streamUrl: "https://example.com/tv-brasil-cultural" },
            { id: "canal-futura-cultural", name: "Canal Futura", category: "Canais Culturais", streamUrl: "https://example.com/canal-futura-cultural" },
            { id: "arte-1", name: "Arte 1", category: "Canais Culturais", streamUrl: "https://example.com/arte-1" },

            { id: "rede-vida-religioso", name: "Rede Vida", category: "Canais Religiosos", streamUrl: "https://example.com/rede-vida-religioso" },
            { id: "tv-aparecida-religioso", name: "TV Aparecida", category: "Canais Religiosos", streamUrl: "https://example.com/tv-aparecida-religioso" },
            { id: "canal-cancao-nova", name: "Canal Canção Nova", category: "Canais Religiosos", streamUrl: "https://example.com/canal-cancao-nova" },
        ];

        const uniqueCategories = [...new Set(channelsData.map(channel => channel.category))].sort();

        // Elementos da UI
        const initialSelectionSection = document.getElementById('initialSelectionSection');
        const adminLoginButton = document.getElementById('adminLoginButton');
        const userLoginButton = document.getElementById('userLoginButton');

        const adminLoginSection = document.getElementById('adminLoginSection');
        const adminLoginForm = document.getElementById('adminLoginForm');
        const adminUsernameInput = document.getElementById('adminUsername');
        const adminPasswordInput = document.getElementById('adminPassword');
        const adminLoginMessage = document.getElementById('adminLoginMessage');
        const backToInitialSelectionFromAdmin = document.getElementById('backToInitialSelectionFromAdmin');

        const userLoginSection = document.getElementById('userLoginSection');
        const userLoginForm = document.getElementById('userLoginForm');
        const userUsernameInput = document.getElementById('userUsername');
        const userPasswordInput = document.getElementById('userPassword');
        const userLoginMessage = document.getElementById('userLoginMessage');
        const backToInitialSelectionFromUser = document.getElementById('backToInitialSelectionFromUser');

        const adminPanelSection = document.getElementById('adminPanelSection');
        const userIdDisplay = document.getElementById('userIdDisplay');
        const addChannelForm = document.getElementById('addChannelForm');
        const channelNameInput = document.getElementById('channelName');
        const channelCategoryInput = document.getElementById('channelCategory');
        const channelMessage = document.getElementById('channelMessage');
        const channelList = document.getElementById('channelList');
        const adminLogoutButton = document.getElementById('adminLogoutButton');

        const addManualUserForm = document.getElementById('addManualUserForm');
        const manualUsernameInput = document.getElementById('manualUsername');
        const manualPasswordInput = document.getElementById('manualPassword');
        const manualCreditsInput = document.getElementById('manualCredits'); // Novo elemento
        const manualSelectCategory = document.getElementById('manualSelectCategory');
        const manualSelectChannel = document.getElementById('manualSelectChannel');
        const manualUserMessage = document.getElementById('manualUserMessage');
        const passwordHint = document.getElementById('passwordHint');

        const generateUserForm = document.getElementById('generateUserForm');
        const genSelectCategory = document.getElementById('genSelectCategory');
        const selectChannel = document.getElementById('selectChannel');
        const userGenMessage = document.getElementById('userGenMessage');
        const generatedCredentials = document.getElementById('generatedCredentials');
        const displayUsername = document.getElementById('displayUsername');
        const displayPassword = document.getElementById('displayPassword');
        const displayExpiryDate = document.getElementById('displayExpiryDate');
        const userTableBody = document.getElementById('userTableBody');

        const userChannelsSection = document.getElementById('userChannelsSection');
        const currentUserDisplay = document.getElementById('currentUserDisplay');
        const userChannelsTableBody = document.getElementById('userChannelsTableBody');
        const userExpiryDisplay = document.getElementById('userExpiryDisplay'); // Novo elemento
        const userLogoutButton = document.getElementById('userLogoutButton');

        // Elementos do modal de confirmação
        const confirmationModal = document.getElementById('confirmationModal');
        const modalMessage = document.getElementById('modalMessage');
        const modalConfirmBtn = document.getElementById('modalConfirmBtn');
        const modalCancelBtn = document.getElementById('modalCancelBtn');

        // Credenciais do administrador (HARDCODED PARA DEMONSTRAÇÃO - NÃO USAR EM PRODUÇÃO)
        const ADMIN_USERNAME = "admtv";
        const ADMIN_PASSWORD = "123456";

        let editingUser = null;
        let resolveModalPromise = null; // Para controlar a promessa do modal de confirmação

        // --- Funções Auxiliares ---
        function showMessage(element, message, type, duration = 3000) {
            clearTimeout(messageTimeout);
            element.textContent = message;
            element.className = `message-box ${type}`;
            element.classList.remove('hidden');
            messageTimeout = setTimeout(() => {
                hideMessage(element);
            }, duration);
        }

        function hideMessage(element) {
            element.classList.add('hidden');
        }

        function hideAllSections() {
            initialSelectionSection.classList.add('hidden-section');
            adminLoginSection.classList.add('hidden-section');
            userLoginSection.classList.add('hidden-section');
            adminPanelSection.classList.add('hidden-section');
            userChannelsSection.classList.add('hidden-section');
        }

        function showInitialSelection() {
            hideAllSections();
            initialSelectionSection.classList.remove('hidden-section');
        }

        function showAdminLogin() {
            hideAllSections();
            adminLoginSection.classList.remove('hidden-section');
            adminLoginForm.reset();
            hideMessage(adminLoginMessage);
        }

        function showUserLogin() {
            hideAllSections();
            userLoginSection.classList.remove('hidden-section');
            userLoginForm.reset();
            hideMessage(userLoginMessage);
        }

        function showAdminPanel() {
            hideAllSections();
            adminPanelSection.classList.remove('hidden-section');
            userIdDisplay.textContent = 'Modo de Demonstração (Admin)';
            populateCategoryDropdowns();
            renderExistingChannels();
            renderUsersTable();
        }

        function showUserChannelsPanel(user) {
            hideAllSections();
            userChannelsSection.classList.remove('hidden-section');
            currentUserDisplay.textContent = user.username;
            // Atualiza a exibição da data de vencimento
            userExpiryDisplay.textContent = user.expiryDate ? new Date(user.expiryDate).toLocaleDateString('pt-BR') : 'N/A';
            renderUserChannels(user);
        }

        // Função para exibir o modal de confirmação customizado
        function showConfirmationModal(message) {
            modalMessage.textContent = message;
            confirmationModal.classList.remove('hidden');
            return new Promise(resolve => {
                resolveModalPromise = resolve;
            });
        }

        // Função para esconder o modal de confirmação
        function hideConfirmationModal() {
            confirmationModal.classList.add('hidden');
        }

        // Event listeners para os botões do modal de confirmação
        modalConfirmBtn.addEventListener('click', () => {
            if (resolveModalPromise) {
                resolveModalPromise(true);
                hideConfirmationModal();
            }
        });

        modalCancelBtn.addEventListener('click', () => {
            if (resolveModalPromise) {
                resolveModalPromise(false);
                hideConfirmationModal();
            }
        });


        function populateCategoryDropdowns() {
            const dropdowns = [channelCategoryInput, manualSelectCategory, genSelectCategory];
            dropdowns.forEach(dropdown => {
                const selectedValues = Array.from(dropdown.options).filter(opt => opt.selected).map(opt => opt.value);
                dropdown.innerHTML = '';

                if (!dropdown.hasAttribute('multiple') || dropdown.id === 'genSelectCategory') {
                    const defaultOption = document.createElement('option');
                    defaultOption.value = "";
                    defaultOption.textContent = `Selecione uma categoria`;
                    dropdown.appendChild(defaultOption);
                }


                uniqueCategories.forEach(category => {
                    const option = document.createElement('option');
                    option.value = category;
                    option.textContent = category;
                    dropdown.appendChild(option);
                });

                if (dropdown.hasAttribute('multiple') || dropdown.id === 'genSelectCategory') {
                    Array.from(dropdown.options).forEach(option => {
                        if (selectedValues.includes(option.value)) {
                            option.selected = true;
                        }
                    });
                }
            });
        }

        function renderExistingChannels() {
            channelList.innerHTML = '';
            const categoriesMap = new Map();
            channelsData.forEach(channel => {
                if (!categoriesMap.has(channel.category)) {
                    categoriesMap.set(channel.category, []);
                }
                categoriesMap.get(channel.category).push(channel);
            });

            uniqueCategories.forEach(category => {
                const categoryChannels = categoriesMap.get(category) || [];
                const categoryDiv = document.createElement('div');
                categoryDiv.classList.add('mb-4');
                categoryDiv.innerHTML = `
                    <h4 class="text-lg font-bold text-gray-800 mb-2">${category}</h4>
                    <ul class="list-disc list-inside space-y-1"></ul>
                `;
                const ul = categoryDiv.querySelector('ul');
                categoryChannels.forEach(channel => {
                    const li = document.createElement('li');
                    li.textContent = `${channel.name}`;
                    ul.appendChild(li);
                });
                channelList.appendChild(categoryDiv);
            });
        }

        // --- Funções de Gestão de Canais ---
        async function addChannel(channelName, channelCategory) {
            const exists = channelsData.some(c => c.name.toLowerCase() === channelName.toLowerCase() && c.category === channelCategory);
            if (exists) {
                showMessage(channelMessage, `O canal '${channelName}' já existe na categoria '${channelCategory}'.`, "error", 5000);
                return;
            }

            const newChannelId = `${channelName.toLowerCase().replace(/\s/g, '-')}-${channelCategory.toLowerCase().replace(/\s/g, '-')}-${Date.now()}`;
            const newChannel = { id: newChannelId, name: channelName, category: channelCategory, streamUrl: `https://example.com/${newChannelId}` };

            channelsData.push(newChannel);
            const tempUniqueCategories = [...new Set(channelsData.map(channel => channel.category))].sort();
            uniqueCategories.splice(0, uniqueCategories.length, ...tempUniqueCategories);

            showMessage(channelMessage, `Canal '${channelName}' (${channelCategory}) adicionado com sucesso (apenas demonstração)!`, "success");
            addChannelForm.reset();
            renderExistingChannels();
            populateCategoryDropdowns();

            const selectedManualCategories = Array.from(manualSelectCategory.selectedOptions).map(opt => opt.value);
            populateChannelsDropdown(selectedManualCategories, manualSelectChannel);
            populateChannelsDropdown(genSelectCategory.value, selectChannel);
        }

        // --- Funções de Geração e Gestão de Utilizadores ---
        function generateUsername(length = 8) {
            const characters = 'abcdefghijklmnopqrstuvwxyz0123456789';
            let result = '';
            const charactersLength = characters.length;
            do {
                result = '';
                for (let i = 0; i < length; i++) {
                    result += characters.charAt(Math.floor(Math.random() * charactersLength));
                }
            } while (createdUsers.has(result));
            return result;
        }

        function generatePassword(length = 12) {
            const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()';
            let result = '';
            const charactersLength = characters.length;
            for (let i = 0; i < length; i++) {
                result += characters.charAt(Math.floor(Math.random() * charactersLength));
            }
            return result;
        }

        function validatePassword(password) {
            if (password.length < 6) {
                return "A senha deve ter no mínimo 6 caracteres.";
            }
            if (!/[a-zA-Z]/.test(password)) {
                return "A senha deve conter pelo menos uma letra.";
            }
            if (!/\d/.test(password)) {
                return "A senha deve conter pelo menos um número.";
            }
            return null;
        }

        // Função para calcular a data de expiração com base nos créditos
        function calculateExpiryDate(credits) {
            const expiry = new Date();
            expiry.setDate(expiry.getDate() + (credits * 30)); // Cada crédito = 30 dias
            return expiry;
        }

        async function addUser(userData, isManual = false) {
            if (createdUsers.has(userData.username)) {
                const messageElement = isManual ? manualUserMessage : userGenMessage;
                showMessage(messageElement, `Erro: O nome de utilizador '${userData.username}' já existe.`, "error", 5000);
                return;
            }

            const messageElement = isManual ? manualUserMessage : userGenMessage;

            showMessage(messageElement, `Utilizador '${userData.username}' adicionado com sucesso (apenas demonstração)!`, "success");

            userData.id = `user-${Date.now()}-${Math.random().toString(36).substr(2, 9)}`;
            userData.createdAt = new Date();

            createdUsers.set(userData.username, userData);

            if (!isManual) {
                generatedCredentials.classList.remove('hidden');
                displayUsername.textContent = userData.username;
                displayPassword.textContent = userData.password;
                displayExpiryDate.textContent = new Date(userData.expiryDate).toLocaleDateString('pt-BR');
            } else {
                addManualUserForm.reset();
                manualSelectChannel.innerHTML = '<option value="">Selecione uma categoria primeiro</option>';
                manualSelectChannel.disabled = true;
                Array.from(manualSelectCategory.options).forEach(option => {
                    option.selected = false;
                });
                manualCreditsInput.value = 1; // Reset credits to default
            }
            renderUsersTable();
        }

        function populateChannelsDropdown(selectedCategories, targetSelectElement) {
            targetSelectElement.innerHTML = '';
            const categoriesToFilter = Array.isArray(selectedCategories) ? selectedCategories : [selectedCategories];

            if (categoriesToFilter.length === 0 || (categoriesToFilter.length === 1 && categoriesToFilter[0] === "")) {
                targetSelectElement.disabled = true;
                const option = document.createElement('option');
                option.value = "";
                option.textContent = "Selecione uma categoria primeiro";
                targetSelectElement.appendChild(option);
                return;
            }

            const filteredChannels = channelsData.filter(channel =>
                categoriesToFilter.includes(channel.category)
            );

            if (filteredChannels.length > 0) {
                targetSelectElement.disabled = false;
                if (!targetSelectElement.hasAttribute('multiple')) {
                    const defaultOption = document.createElement('option');
                    defaultOption.value = "";
                    defaultOption.textContent = "Selecione o canal";
                    targetSelectElement.appendChild(defaultOption);
                }


                filteredChannels.forEach(channel => {
                    const option = document.createElement('option');
                    option.value = channel.id;
                    option.textContent = `${channel.name} (${channel.category.replace('Canais ', '')})`;
                    option.dataset.category = channel.category;
                    targetSelectElement.appendChild(option);
                });
            } else {
                targetSelectElement.disabled = true;
                const option = document.createElement('option');
                option.value = "";
                option.textContent = "Nenhum canal encontrado para as categorias selecionadas";
                targetSelectElement.appendChild(option);
            }
        }

        function renderUsersTable() {
            userTableBody.innerHTML = '';

            if (createdUsers.size === 0) {
                const row = document.createElement('tr');
                row.id = 'loadingUsers';
                row.innerHTML = `<td colspan="8" class="text-center text-gray-500 py-4">Nenhum utilizador gerado ainda (apenas demonstração).</td>`;
                userTableBody.appendChild(row);
                return;
            }

            createdUsers.forEach(user => {
                const row = document.createElement('tr');
                row.setAttribute('data-username', user.username);
                row.id = `user-row-${user.username}`;

                let channelNames = 'N/A';
                let channelCategoriesDisplay = 'N/A';

                if (Array.isArray(user.channels) && user.channels.length > 0) {
                    channelNames = user.channels.map(c => c.name).join(', ');
                    channelCategoriesDisplay = user.categories.map(cat => cat.replace('Canais ', '')).join(', ');
                }

                const expiryDateStr = user.expiryDate ? new Date(user.expiryDate).toLocaleDateString('pt-BR') : 'N/A';
                const createdAtStr = user.createdAt ? new Date(user.createdAt).toLocaleDateString('pt-BR') : 'N/A';
                const creditsDisplay = user.credits !== undefined ? user.credits : 'N/A'; // Display credits

                row.innerHTML = `
                    <td data-field="username">${user.username}</td>
                    <td data-field="password">${user.password}</td>
                    <td data-field="channels">${channelNames}</td>
                    <td data-field="categories">${channelCategoriesDisplay}</td>
                    <td data-field="credits">${creditsDisplay}</td>
                    <td data-field="expiryDate">${expiryDateStr}</td>
                    <td data-field="createdAt">${createdAtStr}</td>
                    <td class="whitespace-nowrap">
                        <button class="edit-button btn-primary py-1 px-3 text-sm" data-username="${user.username}">Editar</button>
                        <button class="delete-button btn-danger py-1 px-3 text-sm ml-2" data-username="${user.username}">Apagar</button>
                    </td>
                `;
                userTableBody.appendChild(row);
            });
        }

        function editUser(usernameToEdit) {
            if (editingUser) {
                cancelEdit(); // Cancela qualquer edição em andamento
            }

            const user = createdUsers.get(usernameToEdit);
            if (!user) {
                showMessage(userGenMessage, "Erro: Usuário não encontrado para edição.", "error");
                return;
            }

            editingUser = { ...user }; // Cria uma cópia do usuário para edição
            const row = document.getElementById(`user-row-${usernameToEdit}`);

            const usernameCell = row.querySelector('[data-field="username"]');
            const passwordCell = row.querySelector('[data-field="password"]');
            const channelsCell = row.querySelector('[data-field="channels"]');
            const categoriesCell = row.querySelector('[data-field="categories"]');
            const creditsCell = row.querySelector('[data-field="credits"]'); // Nova célula para créditos
            const actionsCell = row.querySelector('td:last-child');

            // Armazena o conteúdo original para poder restaurar em caso de cancelamento
            const originalContent = {
                username: usernameCell.innerHTML,
                password: passwordCell.innerHTML,
                channels: channelsCell.innerHTML,
                categories: categoriesCell.innerHTML,
                credits: creditsCell.innerHTML, // Armazena o conteúdo original dos créditos
                actions: actionsCell.innerHTML
            };
            row.dataset.originalContent = JSON.stringify(originalContent);

            // Transforma células em inputs/selects editáveis
            usernameCell.innerHTML = `<input type="text" value="${user.username}" id="edit-username-${user.username}" class="editable-cell">`;
            passwordCell.innerHTML = `<input type="password" value="${user.password}" id="edit-password-${user.username}" class="editable-cell">`;
            creditsCell.innerHTML = `<input type="number" value="${user.credits || 1}" id="edit-credits-${user.username}" class="editable-cell" min="1">`; // Input para créditos

            // Cria o select de categorias (múltiplo)
            const editCategoriesSelect = document.createElement('select');
            editCategoriesSelect.id = `edit-categories-${user.username}`;
            editCategoriesSelect.multiple = true;
            editCategoriesSelect.className = 'editable-cell';
            uniqueCategories.forEach(category => {
                const option = document.createElement('option');
                option.value = category;
                option.textContent = category;
                if (user.categories && user.categories.includes(category)) {
                    option.selected = true;
                }
                editCategoriesSelect.appendChild(option);
            });
            categoriesCell.innerHTML = '';
            categoriesCell.appendChild(editCategoriesSelect);

            // Cria o select de canais (múltiplo)
            const editChannelsSelect = document.createElement('select');
            editChannelsSelect.id = `edit-channels-${user.username}`;
            editChannelsSelect.multiple = true;
            editChannelsSelect.className = 'editable-cell';
            channelsCell.innerHTML = '';
            channelsCell.appendChild(editChannelsSelect);

            // Popula os canais com base nas categorias atualmente selecionadas no modo de edição
            const currentSelectedCategories = Array.from(editCategoriesSelect.selectedOptions).map(opt => opt.value);
            populateChannelsDropdown(currentSelectedCategories, editChannelsSelect);

            // Seleciona os canais que o usuário já possuía
            if (user.channels && Array.isArray(user.channels)) {
                Array.from(editChannelsSelect.options).forEach(option => {
                    if (user.channels.some(c => c.id === option.value)) {
                        option.selected = true;
                    }
                });
            }

            // Adiciona listener para atualizar os canais quando a categoria é alterada na edição
            editCategoriesSelect.addEventListener('change', () => {
                const newSelectedCategories = Array.from(editCategoriesSelect.selectedOptions).map(opt => opt.value);
                populateChannelsDropdown(newSelectedCategories, editChannelsSelect);
                // Após repopular, tente re-selecionar os canais que eram do usuário e ainda estão disponíveis
                if (editingUser && editingUser.channels) {
                     Array.from(editChannelsSelect.options).forEach(option => {
                        if (editingUser.channels.some(c => c.id === option.value)) {
                            option.selected = true;
                        }
                    });
                }
            });


            // Altera os botões de ação para Salvar e Cancelar
            actionsCell.innerHTML = `
                <button class="save-button btn-success py-1 px-3 text-sm" data-username="${user.username}">Salvar</button>
                <button class="cancel-button btn-danger py-1 px-3 text-sm ml-2" data-username="${user.username}">Cancelar</button>
            `;
        }

        function saveEdit(originalUsername) {
            const user = createdUsers.get(originalUsername);
            if (!user) {
                showMessage(userGenMessage, "Erro: Usuário original não encontrado para salvar.", "error");
                return;
            }

            const row = document.getElementById(`user-row-${originalUsername}`);
            if (!row) {
                showMessage(userGenMessage, "Erro: Linha da tabela não encontrada para o usuário.", "error");
                // Reset editing state if row is gone
                editingUser = null;
                renderUsersTable();
                return;
            }

            const newUsernameInput = row.querySelector(`#edit-username-${originalUsername}`);
            const newPasswordInput = row.querySelector(`#edit-password-${originalUsername}`);
            const newCategoriesSelect = row.querySelector(`#edit-categories-${originalUsername}`);
            const newChannelsSelect = row.querySelector(`#edit-channels-${originalUsername}`);
            const newCreditsInput = row.querySelector(`#edit-credits-${originalUsername}`); // Novo input de créditos

            // Adicionado: Verifica se os elementos foram encontrados antes de acessar 'value'
            if (!newUsernameInput || !newPasswordInput || !newCategoriesSelect || !newChannelsSelect || !newCreditsInput) {
                showMessage(userGenMessage, "Erro: Os campos de edição não foram encontrados. Por favor, cancele e tente editar novamente.", "error", 5000);
                // Reseta o estado de edição e renderiza a tabela para limpar qualquer estado quebrado
                editingUser = null;
                renderUsersTable();
                return;
            }

            const newUsername = newUsernameInput.value.trim();
            const newPassword = newPasswordInput.value.trim();
            const newSelectedCategories = Array.from(newCategoriesSelect.selectedOptions).map(opt => opt.value);
            const newSelectedChannels = Array.from(newChannelsSelect.selectedOptions).map(opt => {
                return channelsData.find(c => c.id === opt.value);
            }).filter(Boolean); // Filter out any undefined if channel not found

            const newCredits = parseInt(newCreditsInput.value, 10); // Obter o valor dos créditos

            if (!newUsername) {
                showMessage(userGenMessage, "Nome de utilizador não pode ser vazio.", "error");
                return;
            }
            const passwordError = validatePassword(newPassword);
            if (passwordError) {
                showMessage(userGenMessage, `Erro na senha: ${passwordError}`, "error");
                return;
            }
            if (newSelectedChannels.length === 0) {
                showMessage(userGenMessage, "Por favor, selecione pelo menos um canal.", "error");
                return;
            }
            if (isNaN(newCredits) || newCredits < 1) { // Validação para créditos
                showMessage(userGenMessage, "Créditos devem ser um número inteiro positivo (mínimo 1).", "error");
                return;
            }

            if (newUsername !== originalUsername && createdUsers.has(newUsername)) {
                showMessage(userGenMessage, `Erro: O nome de utilizador '${newUsername}' já existe.`, "error");
                return;
            }

            // Atualiza os dados no Map
            if (newUsername !== originalUsername) {
                createdUsers.delete(originalUsername);
            }

            user.username = newUsername;
            user.password = newPassword;
            user.channels = newSelectedChannels;
            user.categories = newSelectedCategories;
            user.credits = newCredits; // Salva os novos créditos
            user.expiryDate = calculateExpiryDate(newCredits); // Recalcula a expiração

            createdUsers.set(newUsername, user);

            editingUser = null; // Reseta o estado de edição
            renderUsersTable(); // Renderiza a tabela novamente para refletir as mudanças
            showMessage(userGenMessage, `Usuário '${newUsername}' atualizado com sucesso!`, "success");
        }

        function cancelEdit() {
            if (!editingUser) return;

            const row = document.getElementById(`user-row-${editingUser.username}`);
            // Verifica se a linha ainda existe antes de tentar restaurar o conteúdo
            if (row && row.dataset.originalContent) {
                const originalContent = JSON.parse(row.dataset.originalContent);

                row.querySelector('[data-field="username"]').innerHTML = originalContent.username;
                row.querySelector('[data-field="password"]').innerHTML = originalContent.password;
                row.querySelector('[data-field="channels"]').innerHTML = originalContent.channels;
                row.querySelector('[data-field="categories"]').innerHTML = originalContent.categories;
                row.querySelector('[data-field="credits"]').innerHTML = originalContent.credits; // Restaura créditos
                row.querySelector('td:last-child').innerHTML = originalContent.actions;
            } else {
                // Se a linha ou o conteúdo original não existirem, simplesmente re-renderiza a tabela
                renderUsersTable();
            }


            editingUser = null; // Reseta o estado de edição
            showMessage(userGenMessage, "Edição cancelada.", "info");
        }


        async function deleteUser(usernameToDelete) {
            const confirmed = await showConfirmationModal(`Tem certeza que deseja apagar o utilizador '${usernameToDelete}'?`);

            if (confirmed) {
                if (createdUsers.delete(usernameToDelete)) {
                    showMessage(userGenMessage, `Utilizador '${usernameToDelete}' apagado com sucesso!`, "success");
                    renderUsersTable();
                } else {
                    showMessage(userGenMessage, `Erro: Utilizador '${usernameToDelete}' não encontrado.`, "error");
                }
            } else {
                showMessage(userGenMessage, `Exclusão do utilizador '${usernameToDelete}' cancelada.`, "info");
            }
        }

        // --- Funções de Login de Usuário ---
        function userLogin(username, password) {
            const user = createdUsers.get(username);
            if (user && user.password === password) {
                loggedInUser = user;
                sessionStorage.setItem('loggedInUserUsername', username);
                showUserChannelsPanel(user);
            } else {
                showMessage(userLoginMessage, "Nome de utilizador ou senha incorretos.", "error", 5000);
            }
        }

        function userLogout() {
            loggedInUser = null;
            sessionStorage.removeItem('loggedInUserUsername');
            showInitialSelection();
        }

        // --- Renderização de Canais para Usuário ---
        function renderUserChannels(user) {
            userChannelsTableBody.innerHTML = '';
            if (!user || !user.channels || user.channels.length === 0) {
                userChannelsTableBody.innerHTML = `<tr><td colspan="3" class="text-center text-gray-500 py-4">Nenhum canal associado a este usuário.</td></tr>`;
                return;
            }

            user.channels.forEach(channel => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${channel.name}</td>
                    <td>${channel.category.replace('Canais ', '')}</td>
                    <td>
                        <button class="watch-button btn-info py-1 px-3 text-sm" data-stream-url="${channel.streamUrl}">Assistir</button>
                    </td>
                `;
                userChannelsTableBody.appendChild(row);
            });
        }

        // --- Event Listeners ---

        // Seleção Inicial
        adminLoginButton.addEventListener('click', showAdminLogin);
        userLoginButton.addEventListener('click', showUserLogin);

        // Voltar da tela de login para seleção inicial
        backToInitialSelectionFromAdmin.addEventListener('click', showInitialSelection);
        backToInitialSelectionFromUser.addEventListener('click', showInitialSelection);

        // Login do Administrador
        adminLoginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            hideMessage(adminLoginMessage);

            const username = adminUsernameInput.value.trim();
            const password = adminPasswordInput.value.trim();

            if (username === ADMIN_USERNAME && password === ADMIN_PASSWORD) {
                sessionStorage.setItem('isAdminLoggedIn', 'true');
                showAdminPanel();
            } else {
                showMessage(adminLoginMessage, "Nome de utilizador ou senha incorretos.", "error", 5000);
            }
        });

        // Login do Usuário
        userLoginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            hideMessage(userLoginMessage);

            const username = userUsernameInput.value.trim();
            const password = userPasswordInput.value.trim();

            userLogin(username, password);
        });

        // Adicionar Canal
        addChannelForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            hideMessage(channelMessage);
            const channelName = channelNameInput.value.trim();
            const channelCategory = channelCategoryInput.value;

            if (!channelName || !channelCategory) {
                showMessage(channelMessage, "Por favor, insira o nome e selecione a categoria do canal.", "error", 3000);
                return;
            }
            await addChannel(channelName, channelCategory);
        });

        // Event listener para o select de categoria do formulário manual
        manualSelectCategory.addEventListener('change', () => {
            const selectedOptions = Array.from(manualSelectCategory.selectedOptions);
            const selectedCategories = selectedOptions.map(option => option.value);
            populateChannelsDropdown(selectedCategories, manualSelectChannel);
            // Ao mudar a categoria, limpa qualquer seleção prévia de canais
            Array.from(manualSelectChannel.options).forEach(option => {
                option.selected = false;
            });
        });

        // Event listener para o select de categoria do formulário de geração automática
        genSelectCategory.addEventListener('change', () => {
            const selectedCategory = genSelectCategory.value;
            populateChannelsDropdown(selectedCategory, selectChannel);
        });

        // Gerar Utilizador Automaticamente
        generateUserForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            hideMessage(userGenMessage);
            generatedCredentials.classList.add('hidden');

            const selectedOption = selectChannel.options[selectChannel.selectedIndex];
            // Verifica se a opção padrão "Selecione o canal" ou "Nenhum canal..." está selecionada
            if (!selectedOption || selectedOption.value === "") {
                showMessage(userGenMessage, "Por favor, selecione um canal válido para geração.", "error", 3000);
                return;
            }
            const selectedChannelId = selectedOption.value;


            const selectedChannel = channelsData.find(channel => channel.id === selectedChannelId);

            if (!selectedChannel) {
                showMessage(userGenMessage, "Erro: Canal selecionado não encontrado.", "error", 3000);
                return;
            }

            const username = generateUsername();
            const password = generatePassword();
            const credits = 1; // Default 1 credit for auto-generated users
            const expiryDate = calculateExpiryDate(credits);

            const userData = {
                username: username,
                password: password,
                channels: [{ id: selectedChannel.id, name: selectedChannel.name, category: selectedChannel.category, streamUrl: selectedChannel.streamUrl }],
                categories: [selectedChannel.category],
                expiryDate: expiryDate,
                credits: credits, // Store credits
            };

            await addUser(userData, false);
            genSelectCategory.value = ""; // Reseta o campo de categoria
            selectChannel.innerHTML = '<option value="">Selecione uma categoria primeiro</option>'; // Reseta o campo de canal
            selectChannel.disabled = true; // Desabilita o campo de canal
        });

        // Adicionar Utilizador Manualmente
        addManualUserForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            hideMessage(manualUserMessage);

            const manualUsername = manualUsernameInput.value.trim();
            const manualPassword = manualPasswordInput.value.trim();
            const manualCredits = parseInt(manualCreditsInput.value, 10); // Get credits
            const selectedChannelsOptions = Array.from(manualSelectChannel.selectedOptions);

            if (!manualUsername) {
                showMessage(manualUserMessage, "Por favor, insira um nome de utilizador.", "error", 3000);
                return;
            }

            const passwordError = validatePassword(manualPassword);
            if (passwordError) {
                showMessage(manualUserMessage, `Erro na senha: ${passwordError}`, "error", 5000);
                return;
            }

            if (selectedChannelsOptions.length === 0) {
                showMessage(manualUserMessage, "Por favor, selecione pelo menos um canal.", "error", 3000);
                return;
            }

            if (isNaN(manualCredits) || manualCredits < 1) { // Validate credits
                showMessage(manualUserMessage, "Créditos devem ser um número inteiro positivo (mínimo 1).", "error", 5000);
                return;
            }

            const associatedChannels = selectedChannelsOptions.map(option => {
                return channelsData.find(channel => channel.id === option.value);
            }).filter(Boolean); // Filter out any undefined if channel not found

            const associatedCategories = [...new Set(associatedChannels.map(c => c.category))];

            const userData = {
                username: manualUsername,
                password: manualPassword,
                channels: associatedChannels,
                categories: associatedCategories,
                expiryDate: calculateExpiryDate(manualCredits), // Calculate expiry with credits
                credits: manualCredits, // Store credits
            };

            await addUser(userData, true);
        });

        // Event Listener para a tabela de usuários (delegação de eventos) - Admin Panel
        userTableBody.addEventListener('click', (event) => {
            const target = event.target;
            const username = target.dataset.username; // Pega o nome de usuário do botão

            if (target.classList.contains('edit-button')) {
                editUser(username);
            } else if (target.classList.contains('delete-button')) {
                deleteUser(username);
            } else if (target.classList.contains('save-button')) {
                // Ao clicar em salvar, usa o username do `editingUser` que foi salvo no início da edição
                saveEdit(editingUser.username);
            } else if (target.classList.contains('cancel-button')) {
                cancelEdit();
            }
        });

        // Event Listener para a tabela de canais do usuário (delegação de eventos) - User Panel
        userChannelsTableBody.addEventListener('click', (event) => {
            const target = event.target;
            if (target.classList.contains('watch-button')) {
                const streamUrl = target.dataset.streamUrl;
                if (streamUrl) {
                    alert(`Simulando reprodução de: ${streamUrl}\n(Este é um URL de demonstração, o vídeo real não será reproduzido.)`);
                    // window.open(streamUrl, '_blank'); // Para abrir o link real em uma nova aba
                } else {
                    alert('URL de stream não disponível para este canal.');
                }
            }
        });

        // Copiar para a área de transferência
        document.querySelectorAll('.copy-button').forEach(button => {
            button.addEventListener('click', (event) => {
                const targetId = event.target.dataset.target;
                const targetElement = document.getElementById(targetId);
                if (targetElement) {
                    const textToCopy = targetElement.textContent;
                    const textarea = document.createElement('textarea');
                    textarea.value = textToCopy;
                    document.body.appendChild(textarea);
                    textarea.select();
                    try {
                        document.execCommand('copy');
                        showMessage(userGenMessage, "Copiado para a área de transferência!", "success", 2000);
                    } catch (err) {
                        console.error('Falha ao copiar: ', err);
                        showMessage(userGenMessage, "Erro ao copiar. Por favor, copie manualmente.", "error", 3000);
                    } finally {
                        document.body.removeChild(textarea);
                    }
                }
            });
        });

        // Botões de Sair
        adminLogoutButton.addEventListener('click', () => {
            sessionStorage.removeItem('isAdminLoggedIn');
            showInitialSelection();
        });

        userLogoutButton.addEventListener('click', userLogout);

        // Verificar estado de login ao carregar a página
        window.onload = () => {
            if (sessionStorage.getItem('isAdminLoggedIn') === 'true') {
                showAdminPanel();
            } else if (sessionStorage.getItem('loggedInUserUsername')) {
                const username = sessionStorage.getItem('loggedInUserUsername');
                const user = createdUsers.get(username);
                if (user) {
                    loggedInUser = user;
                    showUserChannelsPanel(user);
                } else {
                    // Usuário logado mas não encontrado no mapa (recarregou a página sem dados persistentes)
                    // Voltar para seleção inicial
                    showInitialSelection();
                }
            }
            else {
                showInitialSelection();
            }
        };

        // Adiciona um usuário de demonstração para facilitar o teste da interface de usuário
        // Isso simula um usuário pré-existente
        const demoUser = {
            id: "demo-user-123",
            username: "demouser",
            password: "demopass",
            channels: [
                channelsData.find(c => c.id === "globo-hd"),
                channelsData.find(c => c.id === "espn"),
                channelsData.find(c => c.id === "discovery-kids")
            ].filter(Boolean), // Filter out any undefined if channel not found
            categories: ["Canais HD", "Canais Esportivos", "Canais Infantis"],
            credits: 5, // Demo user with 5 credits
            expiryDate: calculateExpiryDate(5), // Calculate based on credits
            createdAt: new Date(),
        };
        createdUsers.set(demoUser.username, demoUser);
    </script>
</body>
</html>
