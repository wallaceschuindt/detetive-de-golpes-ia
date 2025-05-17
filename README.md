# 🕵️🤖 Detetive de Golpes IA 🚨

**Seu assistente virtual para ajudar a identificar mensagens e tentativas de golpes online!**

---

## 🌟 Contexto do Projeto
Este projeto foi desenvolvido como parte da **Imersão IA - Alura + Google (Maio/2025)**. O objetivo é aplicar os conhecimentos adquiridos durante a imersão para criar uma solução de Inteligência Artificial útil e com potencial de impacto.

---

## 🎯 O Problema
Os golpes online estão cada vez mais sofisticados e frequentes, afetando milhares de pessoas diariamente. Mensagens fraudulentas por SMS, WhatsApp, e-mail e redes sociais tentam enganar usuários para roubar dados pessoais, senhas bancárias ou aplicar fraudes financeiras. Muitas pessoas, especialmente as menos familiarizadas com tecnologia, têm dificuldade em identificar esses golpes.

---

## 💡 A Solução: Detetive de Golpes IA
O "Detetive de Golpes IA" é um chatbot projetado para ser uma primeira linha de análise e alerta contra mensagens suspeitas. O usuário pode colar o texto de uma mensagem recebida, e o chatbot, utilizando um conjunto de regras e padrões, analisa o conteúdo em busca de indícios comuns em fraudes digitais.

---

## ⚙️ Como Funciona (Versão Atual - MVP)
Esta versão inicial (MVP - Produto Mínimo Viável) do Detetive de Golpes IA opera com base em uma lógica de regras predefinidas:
* **Análise de Palavras-Chave:** Identifica termos e expressões frequentemente usados em comunicações fraudulentas (ex: "parabéns você ganhou", "clique aqui urgente", "sua conta foi bloqueada").
* **Verificação de Padrões de Links:** Busca por formatos de URL que são comumente associados a golpes (encurtadores de link usados de forma maliciosa, domínios de topo suspeitos, uso de HTTP em vez de HTTPS).
* **Detecção de Solicitação de Dados Sensíveis:** Alerta para pedidos diretos de informações como CPF, senhas, números de cartão, etc.
* **Análise de Frases Comuns:** Verifica a presença de frases completas que são conhecidas por fazerem parte de roteiros de golpes.
* **Alerta de Mensagens Suspeitas:** Se múltiplos indicadores são encontrados, o chatbot emite um alerta claro ao usuário, listando os pontos de atenção e fornecendo recomendações de segurança.

---

## 🚀 Como Rodar/Testar o Projeto
1.  **Acesse o Notebook:** Abra o arquivo `detetive_de_golpes_ia.ipynb` (ou o nome que você deu ao seu notebook) no [Google Colab](https://colab.research.google.com/).
2.  **Configure a API Key:**
    * No Google Colab, clique no ícone de chave 🔑 (Segredos) na barra lateral esquerda.
    * Clique em "+ Adicionar novo secret".
    * No campo "Nome", digite exatamente: `GOOGLE_API_KEY`
    * No campo "Valor", cole a sua chave de API do Google Gemini.
    * Ative o botão "Acesso do notebook".
3.  **Execute as Células:** Execute todas as células do notebook em ordem.
    * A primeira célula instala as bibliotecas necessárias.
    * A segunda configura a API Key.
    * A terceira inicializa o modelo Gemini (opcional para a lógica principal do MVP, mas configurado).
    * A quarta célula define a função principal do chatbot `chatbot_detetive_de_golpes()`.
    * A quinta célula chama a função `chatbot_detetive_de_golpes()` para iniciar a interação.
4.  **Interaja com o Chatbot:** Quando solicitado, digite ou cole a mensagem suspeita no campo de entrada e pressione Enter para ver a análise.

---

## 🛠️ Tecnologias Utilizadas
* **Python:** Linguagem de programação principal.
* **Google Colab:** Ambiente de desenvolvimento baseado em nuvem para notebooks Jupyter.
* **Google Generative AI SDK:** Para integração com a API do modelo Gemini (configurado para futuras evoluções).
* **Lógica baseada em Regras:** Para a análise de texto no MVP.

---

## ✨ Conexão com a Aula 05 da Imersão e Visão de Futuro: Evoluindo para um Sistema Multi-Agentes com ADK

A Aula 05 da Imersão IA ("Construindo agentes que resolvem tarefas por você") introduziu o conceito de Agentes de IA e o **Google Agent Development Kit (ADK)**. Embora o MVP atual do "Detetive de Golpes IA" utilize uma abordagem baseada em regras, ele serve como um excelente ponto de partida para um sistema de agentes mais sofisticado e inteligente.

**Próximos Passos e Evolução do Projeto:**

Inspirado pela Aula 05, o "Detetive de Golpes IA" poderia evoluir para um sistema multi-agentes utilizando o Google ADK, onde cada agente teria uma especialização:

1.  **Agente Analisador de Semântica (Usando LLM):**
    * **Função:** Receberia a mensagem do usuário e, utilizando um modelo de linguagem como o Gemini, faria uma análise mais profunda do significado, tom, urgência e possíveis táticas de engenharia social presentes no texto, indo além das palavras-chave.
    * **Tool (Opcional):** Poderia usar tools para identificar o idioma e traduzir, se necessário.

2.  **Agente Verificador de Reputação Online (Com GoogleSearch Tool):**
    * **Função:** Se a mensagem contiver links, endereços de e-mail ou números de telefone, este agente usaria a ferramenta `GoogleSearch()` (integrada via ADK) para pesquisar na web por relatos de fraudes, reputação do domínio, ou informações sobre o contato.
    * **Tool:** `GoogleSearch()`.

3.  **Agente Analisador de Imagens (OCR):**
    * **Função:** Permitiria ao usuário enviar prints de tela de mensagens. Este agente usaria técnicas de Reconhecimento Óptico de Caracteres (OCR) para extrair o texto da imagem, que seria então processado pelos outros agentes.
    * **Tool:** Uma API de OCR ou biblioteca Python.

4.  **Agente Consultor de Base de Conhecimento:**
    * **Função:** Consultaria uma base de dados (interna ou externa) de golpes já conhecidos, padrões de phishing, e listas negras de URLs/contatos.
    * **Tool:** Acesso à base de dados.

5.  **Agente Orquestrador e de Veredito:**
    * **Função:** Seria o "cérebro" do sistema, recebendo as informações e análises de todos os outros agentes. Com base em um conjunto de regras ponderadas ou até mesmo em outra chamada a um LLM, ele consolidaria os alertas, avaliaria o nível de risco e forneceria um parecer final claro e detalhado ao usuário, junto com recomendações personalizadas.

Essa arquitetura multi-agentes permitiria uma análise muito mais robusta, contextualizada e eficaz, aumentando significativamente a capacidade do "Detetive de Golpes IA" em proteger os usuários.

---

## 👨‍💻 Autor
**Wallace Schuindt**
* https://github.com/wallaceschuindt/
* https://www.linkedin.com/in/wallaceschuindt/
* https://www.instagram.com/wallaceschuindt/
* E-mail: wbsfriburgo@gmail.com

---
*Obrigado à Alura e ao Google pela oportunidade desta Imersão IA!*
