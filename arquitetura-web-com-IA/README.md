# Alura Album - Copa do Mundo Tech 🚀

Este projeto é uma aplicação web interativa que simula um álbum de figurinhas com as maiores celebridades e pioneiros da tecnologia no Brasil e no mundo.

O projeto está dividido em duas partes principais:
1. **Frontend**: Uma interface web rica em animações, sons interativos e design premium que simula a experiência de folhear um álbum físico (utilizando a biblioteca `PageFlip`).
2. **Backend**: Uma API construída em **FastAPI** (Python) que gerencia as figurinhas disponíveis e serve as imagens correspondentes dinamicamente.

---

## 🛠️ Tecnologias Utilizadas

### Frontend
- **HTML5 & CSS3**: Estrutura semântica e estilização customizada com efeitos modernos (efeito glitch, glassmorphism e responsividade).
- **JavaScript (Vanilla)**: Lógica de carregamento de dados a partir do backend e controle de eventos.
- **Web Audio API**: Geração de sons realistas de virada de página de forma sintética (ruído branco dinâmico).
- **St.PageFlip**: Biblioteca Javascript para simulação 3D realista de virar páginas.

### Backend
- **Python 3**
- **FastAPI**: Framework web moderno e de alta performance.
- **Uvicorn**: Servidor ASGI de produção para rodar a aplicação.
- **CORS Middleware**: Liberado para permitir a comunicação com qualquer frontend.
- **Glob**: Mecanismo de busca de arquivos dinâmico por correspondência de padrões.

---

## ⚙️ O que foi feito no Backend

O servidor está localizado na pasta `backend/` e foi implementado no arquivo [main.py](file:///c:/Users/bea47/Documents/i-arq-ia-alura-album-main/backend/main.py):

1. **Configuração CORS**: Adicionado middleware CORS para aceitar requisições de qualquer origem, possibilitando a integração fluida com o frontend.
2. **Resolução de Caminhos Absolutos**: Utilização do módulo `os` para mapear dinamicamente o local absoluto da pasta contendo as imagens das figurinhas (`backend/figurinhas/`).
3. **Catálogo de Figurinhas**: Uma lista com 30 figurinhas catalogadas divididas por categorias (IA, Python, Banco de Dados, Sistemas Operacionais e Brasil). A figurinha número 30 ("Você") está comentada pois sua imagem correspondente não está disponível na pasta ainda.
4. **Endpoints**:
   - `GET /figuras` e `GET /figurinhas`: Retornam a lista contendo os metadados das figurinhas ativas.
   - `GET /figurinhas/{id}/imagem`: Busca o arquivo da imagem correspondente na pasta de figurinhas usando padrão `glob` (ex: `01[!0-9]*` para evitar colisão com IDs de dois dígitos como `10` ou `11`) e a envia como uma resposta de arquivo (`FileResponse`), gerando erro `404` caso não exista.

---

## 🚀 Como Executar o Projeto

### 1. Executar o Backend (FastAPI)

Navegue até a pasta do backend, instale as dependências necessárias e inicie o servidor:

```bash
cd backend
# Se possuir um ambiente virtual configurado, ative-o antes:
# .venv\Scripts\activate

# Instale os pacotes necessários:
pip install fastapi uvicorn

# Execute o servidor:
uvicorn main:app --reload
```

O backend estará rodando em: `http://localhost:8000`

### 2. Executar o Frontend

Abra o arquivo [index.html](file:///c:/Users/bea47/Documents/i-arq-ia-alura-album-main/frontend/index.html) diretamente no seu navegador ou utilize a extensão **Live Server** do VS Code para executá-lo a partir de um servidor local.
