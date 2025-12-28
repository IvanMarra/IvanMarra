# 🔑 Como Configurar o Token PAT_1 no Vercel

## ⚠️ Erro Atual
```
No GitHub API tokens found
Please add an env variable called PAT_1 with your GitHub API token in vercel
```

## ✅ Solução Passo a Passo

### Passo 1: Criar Token do GitHub

1. **Acesse:** https://github.com/settings/tokens
2. Clique em **"Generate new token"** > **"Generate new token (classic)"**
3. Preencha:
   - **Note:** `Vercel GitHub Readme Stats` (ou qualquer nome que você quiser)
   - **Expiration:** Escolha um período (recomendo 90 dias ou No expiration)
   - **Scopes (permissões):** Marque:
     - ✅ **`repo`** - Acesso completo a repositórios
     - ✅ **`user`** - Informações do usuário
4. Clique em **"Generate token"** (no final da página)
5. **⚠️ IMPORTANTE:** Copie o token imediatamente! Você só verá ele uma vez.
   - O token será algo como: `ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`

### Passo 2: Configurar no Vercel

1. **Acesse:** https://vercel.com/dashboard
2. Clique no projeto **"github-readme-stats"**
3. Vá em **"Settings"** (no topo)
4. Clique em **"Environment Variables"** (no menu lateral esquerdo)
5. Clique em **"Add New"** ou **"Add"**
6. Preencha:
   - **Key (Nome):** `PAT_1`
   - **Value (Valor):** Cole o token que você copiou (começa com `ghp_`)
   - **Environment:** Marque TODAS as opções:
     - ✅ Production
     - ✅ Preview  
     - ✅ Development
7. Clique em **"Save"**

### Passo 3: Fazer Redeploy (OBRIGATÓRIO!)

⚠️ **MUITO IMPORTANTE:** Após adicionar a variável, você DEVE fazer um redeploy!

1. No Vercel, vá em **"Deployments"** (no topo)
2. Encontre o último deployment
3. Clique nos **3 pontinhos** (⋮) ao lado do deployment
4. Clique em **"Redeploy"**
5. Aguarde o deploy terminar (alguns segundos/minutos)

### Passo 4: Verificar se Funcionou

1. Aguarde alguns minutos após o redeploy
2. Teste a URL diretamente no navegador:
   ```
   https://github-readme-stats-cyan-five-75.vercel.app/api?username=IvanMarra
   ```
3. Se aparecer a imagem das estatísticas, está funcionando! ✅
4. Se ainda aparecer erro, verifique:
   - Se o token está correto
   - Se fez o redeploy
   - Se aguardou alguns minutos

## 📋 Resumo das Variáveis

| Nome | Valor | Onde Configurar |
|------|-------|-----------------|
| `PAT_1` | Seu token do GitHub (ghp_...) | Vercel > Settings > Environment Variables |

## 🔍 Verificação Rápida

### ✅ Checklist:
- [ ] Token criado no GitHub com permissões `repo` e `user`
- [ ] Token copiado (começa com `ghp_`)
- [ ] Variável `PAT_1` adicionada no Vercel
- [ ] Valor da variável = token do GitHub
- [ ] Todas as environments marcadas (Production, Preview, Development)
- [ ] Redeploy feito após adicionar a variável
- [ ] Aguardou alguns minutos após o redeploy

## ❌ Troubleshooting

### Token não funciona?
- Verifique se o token tem permissões `repo` e `user`
- Verifique se o token não expirou
- Gere um novo token se necessário
- Faça redeploy após atualizar o token

### Ainda aparece erro?
- Aguarde 2-3 minutos após o redeploy (cache)
- Verifique se o nome da variável está exatamente: `PAT_1` (maiúsculas)
- Verifique se o token está completo (não cortado)
- Tente limpar o cache do navegador (Ctrl+F5)

### Como verificar se o token está configurado?
1. Vercel > Settings > Environment Variables
2. Você deve ver `PAT_1` na lista
3. O valor deve estar mascarado (aparece como `••••••••`)

## 🎯 Próximos Passos

Após configurar o token e fazer o redeploy:
1. Aguarde 2-3 minutos
2. Atualize a página do seu README no GitHub
3. As estatísticas devem aparecer automaticamente!

