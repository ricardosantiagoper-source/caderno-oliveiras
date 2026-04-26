# 🫒 Caderno de Oliveiras

App de caderno de campo para gestão de parcelas de oliveiras, com sincronização em tempo real via Firebase.

## Ficheiros

- `index.html` — a app completa
- `manifest.json` — configuração PWA (para instalar no telemóvel)
- `README.md` — estas instruções

## Como publicar no GitHub Pages

### 1. Criar conta no GitHub
Vai a **github.com** e cria uma conta gratuita (se ainda não tens).

### 2. Criar um repositório
1. Clica em **"New repository"** (botão verde ou ícone "+" no topo)
2. Nome do repositório: `caderno-oliveiras`
3. Deixa como **Public**
4. Clica **"Create repository"**

### 3. Fazer upload dos ficheiros
1. Na página do repositório clica **"uploading an existing file"**
2. Arrasta os ficheiros `index.html` e `manifest.json` para a área de upload
3. Clica **"Commit changes"**

### 4. Ativar GitHub Pages
1. Vai a **Settings** (no menu do repositório)
2. No menu lateral clica **"Pages"**
3. Em "Source" seleciona **"Deploy from a branch"**
4. Em "Branch" seleciona **"main"** e pasta **"/ (root)"**
5. Clica **"Save"**

### 5. Aceder à app
Após 1-2 minutos a app fica disponível em:
`https://SEU-USERNAME.github.io/caderno-oliveiras`

Partilha este link com o teu irmão — os dois acedem ao mesmo caderno.

## Instalar como app no Android

1. Abre o link no Chrome do Android
2. Toca no menu (3 pontos) no canto superior direito
3. Seleciona **"Adicionar ao ecrã inicial"** ou **"Instalar app"**
4. Confirma — aparece um ícone no ecrã inicial como uma app normal

## Segurança Firebase (importante)

Após publicar, protege a base de dados:
1. Vai ao Firebase Console → Firestore → Rules
2. Substitui as regras por:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /caderno/main {
      allow read, write: if true; // Para uso familiar sem login
    }
  }
}
```

Para maior segurança no futuro, considera adicionar autenticação Firebase.
