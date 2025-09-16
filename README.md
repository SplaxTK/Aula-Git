<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Guia Git e GitHub - Davi Santana</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            background-color: #f0f2f5;
            color: #333;
            padding: 20px;
            max-width: 900px;
            margin: 0 auto;
            padding-bottom: 60px; /* espaço para o rodapé fixo */
        }

        h1 {
            color: #2c3e50;
            text-align: center;
            margin-bottom: 30px;
            border-bottom: 2px solid #34495e;
            padding-bottom: 15px;
        }

        .tab-container {
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .tab-header {
            display: flex;
            justify-content: space-around;
            border-bottom: 1px solid #ddd;
            margin-bottom: 20px;
            overflow-x: auto;
        }

        .tab-button {
            background: none;
            border: none;
            padding: 10px 15px;
            font-size: 1rem;
            cursor: pointer;
            color: #7f8c8d;
            transition: color 0.3s, border-bottom 0.3s;
            white-space: nowrap;
        }

        .tab-button.active {
            color: #34495e;
            border-bottom: 2px solid #3498db;
            font-weight: bold;
        }

        .tab-content {
            display: none;
            padding-top: 10px;
            animation: fadeIn 0.5s;
        }

        .tab-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        h2 {
            color: #2c3e50;
            margin-bottom: 10px;
        }

        ul, ol {
            margin-left: 20px;
        }

        code {
            background-color: #ecf0f1;
            padding: 2px 5px;
            border-radius: 4px;
            font-family: 'Courier New', Courier, monospace;
        }
        
        pre {
            background-color: #2c3e50;
            color: #ecf0f1;
            padding: 15px;
            border-radius: 6px;
            overflow-x: auto;
            margin-top: 10px;
        }

        .content {
            max-width: 900px;
            margin: 20px auto;
            padding: 20px;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        /* Rodapé Fixo */
        .fixed-footer {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background-color: #2c3e50; /* Cor escura */
            color: #ecf0f1; /* Cor do texto claro */
            text-align: center;
            padding: 15px 0;
            font-size: 1rem;
            font-weight: bold;
            box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
            z-index: 1000; /* Garante que o rodapé fica acima de outros elementos */
        }

        pre code {
            background: none;
            color: #ecf0f1;
        }

        a {
            color: #3498db;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        footer {
            margin-top: 40px;
            text-align: center;
            font-weight: bold;
            font-size: 1.2rem;
            color: #7f8c8d;
        }
    </style>
</head>
<body>
    <h1>Guia Git e GitHub</h1>

    <div class="tab-container">
        <div class="tab-header">
            <button class="tab-button active" onclick="openTab(event, 'conceitos')">Conceitos</button>
            <button class="tab-button" onclick="openTab(event, 'comandos')">Comandos Essenciais</button>
            <button class="tab-button" onclick="openTab(event, 'repositorio')">Criar Repositório</button>
            <button class="tab-button" onclick="openTab(event, 'fluxo')">Fluxo de Trabalho</button>
        </div>

        <div id="conceitos" class="tab-content active">
            <h2>O que é o Git</h2>
            <p>Git é um sistema de controle de versão distribuído que permite acompanhar alterações no código-fonte durante o desenvolvimento de software. Ele facilita o trabalho colaborativo e o gerenciamento de versões.</p>
            <hr>
            <h2>O que é o GitHub</h2>
            <p>GitHub é uma plataforma online que hospeda repositórios Git, permitindo colaboração, compartilhamento de código e integração com outras ferramentas, além de funcionalidades como issues, pull requests e muito mais.</p>
            <hr>
            <h2>Diferenças do Git e GitHub</h2>
            <ul>
                <li><strong>Git:</strong> Ferramenta local de controle de versão.</li>
                <li><strong>GitHub:</strong> Serviço online para hospedar repositórios Git.</li>
                <li>Git é o motor que gerencia versões, enquanto GitHub é a plataforma para colaboração e compartilhamento.</li>
            </ul>
        </div>

        <div id="comandos" class="tab-content">
            <h2>Principais comandos Git</h2>
            <p>Comandos úteis para o seu dia a dia.</p>
            <ul>
                <li><code>git init</code> – Inicializa um repositório Git.</li>
                <li><code>git clone &lt;url&gt;</code> – Clona um repositório remoto.</li>
                <li><code>git status</code> – Mostra o estado do repositório.</li>
                <li><code>git add &lt;arquivo&gt;</code> – Adiciona arquivos para stage.</li>
                <li><code>git commit -m "mensagem"</code> – Salva alterações com uma mensagem.</li>
                <li><code>git push</code> – Envia alterações para o repositório remoto.</li>
                <li><code>git pull</code> – Atualiza repositório local com mudanças remotas.</li>
                <li><code>git branch</code> – Lista ou cria branches.</li>
            </ul>
        </div>

        <div id="repositorio" class="tab-content">
            <h2>Como criar um repositório no GitHub</h2>
            <ol>
                <li>Acesse <a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a> e faça login.</li>
                <li>Clique no botão <strong>New repository</strong>.</li>
                <li>Informe o nome, descrição opcional e escolha se será público ou privado.</li>
                <li>Marque a opção para criar um <code>README.md</code> (opcional).</li>
                <li>Clique em <strong>Create repository</strong>.</li>
            </ol>
        </div>

        <div id="fluxo" class="tab-content">
            <h2>Como ligar em um projeto existente na máquina</h2>
            <p>Abra o terminal (Git Bash) na pasta do projeto local e execute:</p>
            <pre><code>git init
git remote add origin &lt;url_do_repositório&gt;</code></pre>
            <hr>
            <h2>Como gerar uma versão com git</h2>
            <p>Para salvar o estado atual do seu projeto com uma mensagem, faça:</p>
            <pre><code>git add .
git commit -m "Descrição da versão"</code></pre>
            <hr>
            <h2>Como enviar da máquina para o GitHub</h2>
            <p>Para enviar suas alterações locais para o GitHub, utilize:</p>
            <pre><code>git push origin main</code></pre>
        </div>
    </div>

    <!-- Rodapé fixo, fora do script -->
    <footer class="fixed-footer">
        &copy; Davi Santana 2025
    </footer>

    <script>
        function openTab(evt, tabName) {
            let i, tabcontent, tabbuttons;
            tabcontent = document.getElementsByClassName("tab-content");
            for (i = 0; i < tabcontent.length; i++) {
                tabcontent[i].style.display = "none";
                tabcontent[i].classList.remove("active");
            }
            tabbuttons = document.getElementsByClassName("tab-button");
            for (i = 0; i < tabbuttons.length; i++) {
                tabbuttons[i].classList.remove("active");
            }
            document.getElementById(tabName).style.display = "block";
            document.getElementById(tabName).classList.add("active");
            evt.currentTarget.classList.add("active");
        }
    </script>
</body>
</html>
