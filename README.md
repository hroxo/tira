### 🗺️ Roadmap Tático: Projeto "Nexus"

#### 👥 A Squad (4 Elementos)
1.  **Lead Dev (Tu):** Arquiteto do Django, OOP e Lógica de Negócio (O "Cérebro").
2.  **Data Wrangler:** Especialista em Ingestão de Ficheiros, RAG e Scripts de AI (A "Memória").
3.  **Frontend:** UX/UI Dinâmico e Visualização de Dados (A "Cara").
4.  **DevOps:** Infraestrutura, Docker e Bases de Dados (A "Espinha Dorsal").

---

### 🏁 Fase 1: Fundação e Estrutura (0h - 6h)
**Objetivo:** Ter o ambiente unificado a correr em todas as máquinas. "Hello World" funcional.

* **Lead Dev (Backend Core):**
    * [ ] Iniciar projeto Django + Django Rest Framework.
    * [ ] **Micro-Objetivo (Crucial):** Criar o modelo `EmpresaProfile` com um campo `tipo_negocio` (Ex: 'retalho', 'servicos', 'restauracao'). É isto que define o comportamento polimórfico.
    * [ ] Definir os modelos base `Documento` e `Transacao`.

* **Data Wrangler (Setup AI Local):**
    * [ ] Configurar script isolado para testar `LangChain` ou `ChromaDB` (Base de dados vetorial para guardar o conhecimento dos documentos).
    * [ ] **Micro-Objetivo:** Criar um script que lê um PDF e devolve o texto limpo ("print text").

* **Frontend (Shell):**
    * [ ] Setup React (Vite).
    * [ ] **Micro-Objetivo:** Criar o "Wizard de Onboarding". Uma tela simples onde o utilizador diz o nome da empresa e escolhe o tipo.

* **DevOps (Ambiente):**
    * [ ] Criar `docker-compose.yml` com: Django, Postgres e (opcionalmente) ChromaDB.
    * [ ] **Micro-Objetivo:** Garantir que todos fazem `docker-compose up` e veem a página de boas-vindas do Django sem erros.

---

### ⚙️ Fase 2: O Motor Polimórfico (6h - 18h)
**Objetivo:** O sistema distingue tipos de negócio e aceita dados.

* **Lead Dev (Lógica OOP):**
    * [ ] Implementar o **Factory Pattern** (como falámos). Se o user é 'Retalho', o sistema carrega os módulos de Stock. Se é 'Serviços', carrega Agenda.
    * [ ] Criar API Endpoints: `/api/🗺️ O Roadmap "Fast-Pace" (Ciclo de 48h-72h)upload-documento` e `/api/dashboard-data`.
    * [ ] **Micro-Objetivo:** Testar via Postman: criar uma empresa "Oficina" e ver se a API responde com estrutura de dados correta.

* **Data Wrangler (Ingestão):**
    * [ ] Ligar o script de PDF ao Django.
    * [ ] **Micro-Objetivo:** Quando o user faz upload de uma "Fatura.pdf", o sistema extrai o texto, identifica a data e o valor total (usando Regex ou AI simples) e guarda na BD.

* **Frontend (Contexto):**
    * [ ] Criar Dashboard Condicional.
    * [ ] **Micro-Objetivo:** Se a API devolver `type: retail`, renderizar componente "Tabela de Stock". Se `type: services`, renderizar "Lista de Agendamentos".

* **DevOps (Persistência):**
    * [ ] Configurar volumes do Docker para que os PDFs não desapareçam quando reiniciam o contentor.
    * [ ] Preparar o deploy num serviço gratuito (Render/Railway) para testes iniciais.

---

### 🧠 Fase 3: A Inteligência "Taylor Made" (18h - 36h)
**Objetivo:** O "Wow Factor". O sistema dá conselhos baseados nos dados.

* **Lead Dev (O Consultor):**🗺️ O Roadmap "Fast-Pace" (Ciclo de 48h-72h)
    * [ ] Criar a lógica do Agente: Comparar receitas vs despesas.
    * [ ] **Micro-Objetivo:** Endpoint `/api/conselho-do-dia`. Exemplo de resposta JSON: `{"alerta": "Gastos altos", "mensagem": "A conta de luz subiu 20%. Verifica os equipamentos."}`.

* **Data Wrangler (O Oráculo - RAG):**
    * [ ] Implementar busca semântica.
    * [ ] **Micro-Objetivo:** Permitir que o Frontend pergunte: "Quanto gastei em fornecedores?" e o Backend procura nos vetores dos PDFs e responde. (Usa a API da Groq aqui para gerar a resposta final).

* **Frontend (Interatividade):**
    * [ ] Criar o componente "Chat com o Consultor".
    * [ ] **Micro-Objetivo:** Mostrar notificações proativas ("Tens 3 faturas em atraso").

* **DevOps (Otimização):**
    * [ ] Garantir que as chaves de API (Groq/OpenAI) estão seguras nas variáveis de ambiente.
    * [ ] Teste de carga: O que acontece se 2 pessoas fizerem upload ao mesmo tempo?🗺️ O Roadmap "Fast-Pace" (Ciclo de 48h-72h)

---

### 💎 Fase 4: Polimento e Demo (36h - 48h)
**Objetivo:** Vender a ideia. Tudo tem de parecer mágico.

* **Lead Dev & Wrangler:** Criar **Dados Falsos Realistas** (Seed Data). A demo não pode ter tabelas vazias. Criar 2 perfis completos: "Café Central" e "Oficina do Zé".
* **Frontend:** Animações de loading (importante quando a AI está a "pensar").
* **DevOps:** Deploy final e verificação de domínios.

---

### 🧩 Arquitetura Visual do MVP



### 💡 Conselho do Coach para o Capitão

Nesta arquitetura, o maior risco é o **Data Wrangler** ficar preso na complexidade de ler PDFs imperfeitos.
**Plano B:** Se a leitura automática falhar, implementem um botão "Edição Manual" no Frontend. Nunca deixem a Demo crashar porque o PDF estava torto. Mais vale o sistema dizer "Não consegui ler tudo, ajuda-me?" do que dar Erro 500.

Vamos a isto, Squad? Qual é a primeira tarefa que queres atacar? 🚀 ficheiro `test_pdf.py`. Se funcionar lá, tu ( ) ajudas a copiar para dentro do Django. Isto evita que ele parta o servidor enquanto aprende.

**Next Step:** Querem que eu gere o esqueleto do `docker-compose.yml` para garantir que os 4 começam com o ambiente igual? Isso poupa-vos umas 2 horas de "na minha máquina funciona, na tua não".
