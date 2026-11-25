# Clásico 3D (GitHub Pages + Firebase)

## Ficheiros
- `index.html` – o jogo
- `firebase-config.js` – as tuas chaves Web do Firebase (preenche)
- `firestore.rules` – regras de segurança (colar no Firebase)
- `fotos/` – fotos dos jogadores (opcional)

## Passo a passo
1. **Firebase** (console.firebase.google.com): criar projeto → ícone Web `</>` → registar app → copiar o `firebaseConfig`.
2. Colar os 6 valores em `firebase-config.js` (substituir `COLA_AQUI`).
3. **Authentication** → Sign-in method → ativar **Email/palavra-passe**.
4. **Firestore Database** → criar (modo produção) → separador **Regras** → colar o conteúdo de `firestore.rules` → Publicar.
5. **GitHub**: novo repositório → carregar todos estes ficheiros → Settings → Pages → Branch `main`, pasta `/ (root)` → Save.
6. Firebase → Authentication → Settings → **Authorized domains** → adicionar `O-TEU-USER.github.io`.
7. Abrir `https://O-TEU-USER.github.io/NOME-DO-REPO/`, criar conta (nome de utilizador + palavra-passe).
8. Dar tickets: Firestore → coleção `users` → documento do jogador → campo `tickets`.

## Segurança
- A `apiKey` Web do Firebase não é secreta; a proteção são as regras. Recomendado: Google Cloud → Credenciais → restringir a chave a `https://O-TEU-USER.github.io/*`.
- Nunca ponhas no repositório chaves de conta de serviço (`private_key`).
- O `firebase-config.js` já traz as chaves do projeto matchpoint01-db.
