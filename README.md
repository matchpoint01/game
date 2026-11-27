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
8. Tickets: só se ganham ao subir de nível (1 por nível); para dares tickets manualmente, Firestore → coleção `users` → documento do jogador → campo `tickets`.

## Segurança
- A `apiKey` Web do Firebase não é secreta; a proteção são as regras. Recomendado: Google Cloud → Credenciais → restringir a chave a `https://O-TEU-USER.github.io/*`.
- Nunca ponhas no repositório chaves de conta de serviço (`private_key`).
- O `firebase-config.js` já traz as chaves do projeto matchpoint01-db.

## Admin e comandos
Cada conta nova é criada com `admin: false` (aparece "Admin: OFF" no perfil). Só tu podes ligar: Firebase → Firestore → `users` → documento do jogador → adiciona/edita o campo `admin` (boolean) = `true`. Só com admin ligado funcionam os comandos (`/pen`, `/bar 40`, `/verrival`). As regras impedem que um jogador altere o próprio `admin`.
Contas antigas sem o campo ficam como OFF; para te ligares a ti, cria o campo `admin = true` à mão.

## Limites de escrita
Os packs são abertos no browser e gravados de uma só vez ao sair do menu de packs (1 escrita, sem leituras). As regras permitem no máximo 1 gravação de packs a cada 5 s e 1 resultado de jogo a cada 90 s.
