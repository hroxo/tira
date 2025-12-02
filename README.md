### 🗺️ O Roadmap "Fast-Pace" (Ciclo de 48h-72h)

#### 👥 Os Papéis (Squad 4)
1.  **Back & AI (AI & Backend Core):** O Cérebro. Foca em Django, Lógica de Negócio e Computer Vision.
2.  **DevOps (Infra & Deploy):** O Guardião. Foca em Docker, CI/CD e manter os custos a zero.
3.  **Frontend (React/UI):** A Cara. Foca em UX, Dashboards e interatividade.
4.  **Data Wrangler (O Novo Membro):** A Cola. Foca em Ingestão de Dados (Parsers de PDF/Excel), APIs e Testes com dados falsos.

---

### 🏁 Fase 1: Fundação e "Hello World" (As primeiras 6 horas)
**Objetivo:** Ter o ambiente pronto e o primeiro "pixel" no ecrã. Nada de complexidade ainda.

* **WebS:**
    * [ ] Iniciar projeto Django e configurar ambiente virtual.
    * [ ] **Micro-Objetivo:** Criar os `models.py` iniciais (Tabelas: `Produto`, `Fornecedor`, `Encomenda`). *Lembra-te: Define as relações (ForeignKey) agora para não sofreres depois.*
    * [ ] Instalar `Django Rest Framework` (DRF).

* **Data Wrangler (Dados):**
    * [ ] Criar um script Python simples (separado do Django) para testar a biblioteca `PyPDF2` ou `Tabula`.
    * [ ] **Micro-Objetivo:** Conseguir extrair texto de um PDF de fatura de exemplo e imprimir no terminal.
    * [ ] Gerar um ficheiro JSON com 50 produtos falsos para povoar a BD depois.

* **Frontend (React):**
    * [ ] `create-react-app` ou `vite`.
    * [ ] Instalar biblioteca de componentes (sugiro **ShadCN** ou **Chakra UI** para ser rápido).
    * [ ] **Micro-Objetivo:** Criar a "Navbar" e uma página "Dashboard" vazia.

* **DevOps (Infra):**
    * [ ] Configurar repositório Git (Monorepo ou separado).
    * [ ] Configurar conta no **Render** (Backend) e **Vercel** (Frontend).
    * [ ] **Micro-Objetivo:** Fazer o deploy de um "Hello World" para garantir que o pipeline funciona.

---

### ⚙️ Fase 2: O Motor Lógico (As próximas 12 horas)
**Objetivo:** O sistema já faz operações básicas (CRUD). É funcional, mas "burro" (sem AI).

* **Backend:**
    * [ ] Criar os Endpoints da API (GET/POST produtos).
    * [ ] Implementar a lógica de stock (ex: quando entra fatura, aumenta stock).
    * [ ] **Micro-Objetivo:** Conseguir criar um produto via Postman/Insomnia.

* **Data Wrangler (Integração):**
    * [ ] Integrar o script de PDF dentro do Django (criar uma função `utils.py`).
    * [ ] Criar o endpoint de upload de ficheiro.
    * [ ] **Micro-Objetivo:** O utilizador faz upload de um PDF e o sistema devolve o JSON dos itens encontrados.

* **Frontend (Conexão):**
    * [ ] Consumir a API (Axios/Fetch).
    * [ ] Criar Tabela de Inventário dinâmica.
    * [ ] **Micro-Objetivo:** Listar os produtos que vêm do Backend no ecrã.

* **DevOps (Docker):**
    * [ ] Criar `docker-compose.yml` para que todos rodem o mesmo ambiente localmente.
    * [ ] Configurar base de dados Postgres gratuita (Neon ou Supabase) e ligar ao Django.

---

### 🧠 Fase 3: A Magia da AI e "Taylor Made" (O stprint final)
**Objetivo:** Onde ganham o Hackathon. A AI entra em ação.

* **AI Vision:**
    * [ ] Implementar o `Tesseract` ou lógica de visão para ler fotos de etiquetas/faturas (caso o PDF falhe).
    * [ ] **Micro-Objetivo:** Funcionalidade "Snap & Add" (Tira foto ao produto, ele aparece na BD).

* **Data Wrangler (AI Prediction):**
    * [ ] Implementar a "Regressão Linear" simples (como falámos antes) para prever rutura de stock.
    * [ ] **Micro-Objetivo:** Adicionar um campo "Dias até acabar" na API de produtos.

* **Frontend (Wow Factor):**
    * [ ] Criar os alertas visuais (Vermelho = Stock Crítico).
    * [ ] Implementar gráficos de previsão (Chart.js ou Recharts).
    * [ ] **Micro-Objetivo:** O Dashboard parece vivo e inteligente.

* **DevOps (Performance):**
    * [ ] Garantir que o processamento de imagem/PDF não bloqueia o site (se conseguirem, usem **Celery** básico ou Python Threads).
    * [ ] Otimizar o build para a demo.

---

### 💎 Fase 4: Polish & Pitch (As últimas horas)
**Objetivo:** Eliminar bugs óbvios e preparar a história.

* **Wrangler:** Testar casos extremos (upload de ficheiro errado, imagem escura). Escrever mensagens de erro amigáveis.
* **Frontend:** Animações de loading (muito importante para disfarçar o tempo da AI).
* **DevOps:** Monitorizar se o servidor gratuito não está a dormir.
* **TODOS:** Ensaio da Demo. *O "caminho feliz" (happy path) tem de funcionar 100% das vezes.*

### 🛠️ Diagrama de Fluxo de Trabalho (High Level)



### 💡 Dica do Coach para o "Data Wrangler" (Membro 4)

Se ele não tiver muita experiência com Python, diz-lhe para começar por **Scripts Isolados**.
Em vez de tentar escrever logo dentro do Django, ele deve fazer um ficheiro `test_pdf.py`. Se funcionar lá, tu ( ) ajudas a copiar para dentro do Django. Isto evita que ele parta o servidor enquanto aprende.

**Next Step:** Querem que eu gere o esqueleto do `docker-compose.yml` para garantir que os 4 começam com o ambiente igual? Isso poupa-vos umas 2 horas de "na minha máquina funciona, na tua não".
