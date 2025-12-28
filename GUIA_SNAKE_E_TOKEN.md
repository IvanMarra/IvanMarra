# 🐍 Guia Completo: Snake Animation + Token do GitHub

## ✅ O que foi corrigido

### 1. **Snake Animation (snake.yml)**
- ✅ Arquivo movido para `.github/workflows/snake.yml` (local correto)
- ✅ Caminho de saída corrigido: `dist/github-contribution-grid-snake.svg`
- ✅ README atualizado para usar o caminho correto
- ✅ Permissões configuradas corretamente

### 2. **Token do GitHub**

**IMPORTANTE:** O token é necessário para **duas coisas diferentes**:

#### A) GitHub Readme Stats (Vercel) - PRECISA DE TOKEN
- **Onde:** Vercel Dashboard > Settings > Environment Variables
- **Nome da variável:** `PAT_1`
- **Valor:** Seu Personal Access Token do GitHub
- **Por quê:** Para acessar repositórios privados e evitar limitação de taxa

#### B) Snake Animation (GitHub Actions) - NÃO PRECISA DE TOKEN
- **Não precisa configurar nada!** 
- O GitHub Actions usa automaticamente `${{ secrets.GITHUB_TOKEN }}`
- Este token é gerado automaticamente pelo GitHub

## 🚀 Como fazer funcionar

### Passo 1: Snake Animation

1. **Commit e push o workflow:**
   ```bash
   git add .github/workflows/snake.yml
   git commit -m "Add snake animation workflow"
   git push origin main
   ```

2. **Execute manualmente (primeira vez):**
   - Vá em: https://github.com/IvanMarra/IvanMarra/actions
   - Clique em **Generate Snake**
   - Clique em **Run workflow** > **Run workflow**

3. **Aguarde alguns minutos** e verifique se o arquivo foi criado:
   - https://github.com/IvanMarra/IvanMarra/tree/main/dist
   - Deve aparecer: `github-contribution-grid-snake.svg`

4. **Verifique no README:**
   - A animação deve aparecer automaticamente
   - Se não aparecer, aguarde alguns minutos (cache do GitHub)

### Passo 2: Configurar Token no Vercel (GitHub Readme Stats)

1. **Criar Token do GitHub:**
   - Acesse: https://github.com/settings/tokens
   - Clique em **Generate new token (classic)**
   - Nome: `Vercel GitHub Stats`
   - Marque as permissões: ✅ `repo` e ✅ `user`
   - Clique em **Generate token**
   - **COPIE O TOKEN** (você só verá uma vez!)

2. **Configurar no Vercel:**
   - Acesse: https://vercel.com/dashboard
   - Clique no projeto **github-readme-stats**
   - Vá em **Settings** > **Environment Variables**
   - Clique em **Add New**
   - **Key:** `PAT_1`
   - **Value:** Cole o token que você copiou
   - **Environment:** Marque todas (Production, Preview, Development)
   - Clique em **Save**

3. **Fazer Redeploy:**
   - Vá em **Deployments**
   - Clique nos **3 pontinhos** do último deployment
   - Clique em **Redeploy**
   - Aguarde o deploy terminar

4. **Encontrar sua URL do Vercel:**
   - No Vercel, vá em **Settings** > **Domains**
   - Você verá algo como: `github-readme-stats-abc123.vercel.app`
   - **COPIE ESSA URL**

5. **Atualizar README.md:**
   - Abra o README.md
   - Substitua todas as ocorrências de `SUA_INSTANCIA_VERCEL` pela sua URL do Vercel
   - Exemplo: Se sua URL é `github-readme-stats-xyz789.vercel.app`
   - Substitua: `SUA_INSTANCIA_VERCEL` → `github-readme-stats-xyz789.vercel.app`

## 🔍 Verificação

### Snake Animation funcionando?
- ✅ Arquivo existe em: `dist/github-contribution-grid-snake.svg`
- ✅ Aparece no README
- ✅ Atualiza automaticamente todo dia

### GitHub Readme Stats funcionando?
- ✅ Token configurado no Vercel (`PAT_1`)
- ✅ Redeploy feito após adicionar token
- ✅ URL do Vercel atualizada no README
- ✅ Estatísticas aparecem no README

## ❌ Troubleshooting

### Snake não aparece
1. Verifique se o workflow rodou: https://github.com/IvanMarra/IvanMarra/actions
2. Verifique se o arquivo existe: https://github.com/IvanMarra/IvanMarra/tree/main/dist
3. Se não existir, execute o workflow manualmente
4. Aguarde alguns minutos (cache do GitHub)

### Estatísticas não aparecem
1. Verifique se o token está configurado no Vercel
2. Verifique se fez redeploy após adicionar o token
3. Teste a URL diretamente no navegador: `https://SUA_URL/api?username=IvanMarra`
4. Verifique se a URL do Vercel está correta no README

### Token não funciona
1. Verifique se o token tem permissões `repo` e `user`
2. Verifique se o token não expirou
3. Gere um novo token se necessário
4. Faça redeploy no Vercel após atualizar o token

## 📝 Resumo

| Item | Precisa Token? | Onde Configurar |
|------|----------------|-----------------|
| Snake Animation | ❌ Não | Nenhum lugar (automático) |
| GitHub Readme Stats | ✅ Sim | Vercel > Environment Variables |

## 🎯 Próximos Passos

1. ✅ Commit o workflow do snake
2. ✅ Execute o workflow manualmente
3. ✅ Configure o token no Vercel
4. ✅ Atualize a URL do Vercel no README
5. ✅ Aguarde alguns minutos
6. ✅ Verifique se tudo está funcionando!

