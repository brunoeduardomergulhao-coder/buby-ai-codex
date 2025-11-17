# BubbyAI

Monorepo simples com backend em Node/TypeScript e frontend em React/Vite. O deploy recomendado (produção) é do frontend na Vercel.

## Requisitos
- Node 18+
- npm

## Backend (opcional/local)
```bash
npm install
npm run dev          # http://localhost:3000
npm run build        # gera dist/
npm start            # roda dist/
npm run check        # checa tipos
```
Ambiente base: copie `.env.example` para `.env` se necessário.

## Frontend (landing)
```bash
cd frontend
npm install
npm run dev          # http://localhost:5173
npm run build        # gera frontend/dist
```

## Deploy na Vercel (frontend)
1. Crie o repo no GitHub e faça push deste diretório.
2. Na Vercel, importe o repo e selecione a pasta `frontend` como root (ajuda via `vercel.json`).
3. Build command: `npm run build`
4. Output directory: `dist`
5. Deploy.

_Nota:_ o backend não está configurado para Vercel; use outra infra (Railway/Fly/Docker) se quiser expor a API.

## Subir para GitHub (exemplo)
```bash
git init
git add .
git commit -m "chore: preparar deploy"
git branch -M main
git remote add origin https://github.com/<seu-usuario>/<repo>.git
git push -u origin main
```

## Estrutura
- `src/` - backend (Fastify + TS)
- `frontend/` - landing React/Vite
- `vercel.json` - aponta root `frontend` e build/output `dist`
- `.gitignore` - ignora node_modules, dist, envs, .vercel

## Próximos passos
- Ligar backend a um provedor de imagens.
- Ajustar CORS do backend se for expor a API.
- Se precisar de backend online, deploy em provider próprio.
