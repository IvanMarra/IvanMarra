# 🚀 Configurar Instância Própria no Vercel

## ✅ Passo 1: Encontrar sua URL do Vercel

1. Acesse: https://vercel.com/dashboard
2. Clique no seu projeto do **github-readme-stats**
3. Vá em **Settings** > **Domains** ou **Deployments**
4. Copie a URL (exemplo: `github-stats-abc123.vercel.app`)

**OU** se ainda não fez o deploy:

### Deploy Rápido:

1. Acesse: https://vercel.com/new
2. Clique em **Import Git Repository**
3. Cole: `https://github.com/anuraghazra/github-readme-stats`
4. Clique em **Deploy**

## ✅ Passo 2: Configurar Token do GitHub

1. No Vercel, vá em **Settings** > **Environment Variables**
2. Adicione:
   - **Name:** `PAT_1`
   - **Value:** seu token do GitHub (cole aqui)
   - **Environment:** Production, Preview, Development (marque todos)
3. Clique em **Save**
4. **IMPORTANTE:** Vá em **Deployments** e faça um **Redeploy** para aplicar a variável

## ✅ Passo 3: Atualizar README.md

Substitua `SUA_INSTANCIA_VERCEL` no README.md pela sua URL do Vercel.

**Exemplo:**
- Se sua URL é: `github-stats-xyz789.vercel.app`
- Substitua todas as ocorrências de `SUA_INSTANCIA_VERCEL` por `github-stats-xyz789.vercel.app`

## ✅ Passo 4: Testar

Abra no navegador para testar:
```
https://SUA_INSTANCIA_VERCEL/api?username=IvanMarra
```

Se aparecer a imagem, está funcionando! ✅

## 🔧 Troubleshooting

### Token não funciona?
- Verifique se o token tem permissões: `repo` e `user`
- Faça um redeploy após adicionar a variável

### URL não funciona?
- Verifique se o deploy foi concluído
- Aguarde alguns minutos após o deploy
- Teste a URL diretamente no navegador

### Ainda usando instância pública?
- Certifique-se de substituir TODAS as ocorrências de `github-readme-stats.vercel.app` pela sua URL
- Verifique se não há cache (Ctrl+F5)

   