# guias.aiudalabs.com

Guías interactivas de estudio — static site on Vercel.

## Estructura

```
public/
├── index.html              ← Landing con lista de guías
└── utp/
    └── edo/
        └── index.html      ← EDO 1er Orden
```

## Deploy

```bash
# 1. Init + push
cd ~/projects/aiudalabs.com/guias
git init
git add .
git commit -m "feat: EDO 1er orden guide + landing"
gh repo create aiudalabs/guias --public --source=. --push

# 2. Vercel (opción CLI)
vercel
# Framework: Other | Output: public | Deploy

# 3. Dominio
# Vercel dashboard → Settings → Domains → guias.aiudalabs.com
# DNS: CNAME guias → cname.vercel-dns.com

# 4. GA: reemplazar G-XXXXXXXXXX en ambos HTMLs
sed -i '' 's/G-XXXXXXXXXX/G-TU-ID/g' public/index.html public/utp/edo/index.html
```

## Agregar guía nueva

1. `mkdir -p public/utp/{materia}`
2. Copiar template HTML, cambiar datos
3. Actualizar card en `public/index.html`
4. `git push` → Vercel redeploy automático
