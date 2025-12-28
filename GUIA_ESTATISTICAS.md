# 📊 Guia: Como fazer as Estatísticas do GitHub funcionarem

## ⚠️ Problema Comum: Limitação de Taxa da API

Se as estatísticas **funcionavam antes** e agora não aparecem, o problema mais provável é:
- **Limitação de taxa da API pública** do GitHub Readme Stats
- Muitos usuários acessando simultaneamente a instância pública
- Problemas temporários nos servidores (Vercel/Heroku)

## ✅ Soluções Rápidas

### Solução 1: Simplificar URLs (JÁ APLICADO)
Removi parâmetros customizados que podem causar problemas. As URLs agora estão mais simples e confiáveis.

### Solução 2: Testar URLs Diretamente
Abra no navegador para verificar se funcionam:
- **GitHub Stats:** https://github-readme-stats.vercel.app/api?username=IvanMarra
- **GitHub Streak:** https://github-readme-streak-stats.herokuapp.com/?user=IvanMarra
- **Top Langs:** https://github-readme-stats.vercel.app/api/top-langs/?username=IvanMarra

**Se aparecerem no navegador:** O problema é cache do GitHub. Aguarde alguns minutos.

**Se NÃO aparecerem no navegador:** Problema nos servidores. Use URLs alternativas abaixo.

### Solução 3: URLs Alternativas (Backup)
Se a instância principal não funcionar, use estas alternativas:

```markdown
<!-- Alternativa 1: Servidor alternativo -->
<img src="https://github-readme-stats-git-main-anuraghazra.vercel.app/api?username=IvanMarra&show_icons=true&theme=tokyonight" />

<!-- Alternativa 2: Streak Stats alternativo -->
<img src="https://streak-stats.demolab.com/?user=IvanMarra&theme=tokyonight" />

<!-- Alternativa 3: Versão simplificada sem tema -->
<img src="https://github-readme-stats.vercel.app/api?username=IvanMarra&show_icons=true" />
```

### Solução 4: Aguardar e Limpar Cache
1. Aguarde 10-15 minutos (pode ser problema temporário)
2. Limpe o cache do GitHub: Ctrl+F5 ou Cmd+Shift+R
3. Tente em modo anônimo do navegador

## 🔧 Solução de Problemas

### ❌ Imagens não aparecem (funcionava antes)
**Causa mais provável:** Limitação de taxa da API pública

**Soluções em ordem de prioridade:**
1. ✅ **Simplificar URLs** (já feito - removidos parâmetros extras)
2. ✅ **Aguardar 10-15 minutos** (problema temporário)
3. ✅ **Testar URLs no navegador** (verificar se servidor está funcionando)
4. ✅ **Usar URLs alternativas** (ver seção acima)
5. ✅ **Limpar cache** (Ctrl+F5 no GitHub)

### ❌ Nunca funcionou
**Causas possíveis:**
1. Username incorreto
2. Sem commits no GitHub
3. Repositório privado (requer token)

**Solução:**
- Verifique o username: https://github.com/settings/profile
- Faça alguns commits no GitHub
- Se repositório for privado, use token pessoal (veja Solução Avançada)

### ❌ Wakatime não funciona
**Causa:** Requer configuração adicional

**Solução:**
1. Crie conta em: https://wakatime.com
2. Instale o plugin no seu editor (VS Code, Cursor, etc.)
3. Configure a API key
4. Use seu username do Wakatime (pode ser diferente do GitHub)

**Ou remova a linha do Wakatime** se não quiser usar:
```markdown
<!-- Remova esta linha se não usar Wakatime -->
<img height="180em" src="..." alt="Wakatime Stats" />
```

## 🎨 Personalizar Estatísticas

### Mudar tema:
- `theme=tokyonight` → `theme=dark`, `theme=radical`, `theme=merko`, etc.

### Mudar cores:
- `bg_color=1a1b27` (fundo)
- `title_color=36BCF7` (título)
- `icon_color=36BCF7` (ícones)
- `text_color=c9d1d9` (texto)

### Exemplos de temas:
- `theme=dark`
- `theme=radical`
- `theme=merko`
- `theme=gruvbox`
- `theme=tokyonight` (atual)

## 🚀 Solução Avançada: Instância Própria (Recomendado)

Para evitar problemas de limitação de taxa, crie sua própria instância:

### Passo 1: Criar Token do GitHub
1. Acesse: https://github.com/settings/tokens
2. Clique em "Generate new token (classic)"
3. Marque: `repo` e `user`
4. Copie o token gerado

### Passo 2: Deploy no Vercel
1. Acesse: https://vercel.com/new
2. Importe: https://github.com/anuraghazra/github-readme-stats
3. Adicione variável de ambiente:
   - Nome: `PAT_1`
   - Valor: seu token do GitHub
4. Deploy!

### Passo 3: Atualizar README.md
Substitua `github-readme-stats.vercel.app` pela URL da sua instância:
```markdown
<img src="https://sua-instancia.vercel.app/api?username=IvanMarra&show_icons=true&theme=tokyonight" />
```

**Vantagens:**
- ✅ Sem limitação de taxa
- ✅ Mais rápido e confiável
- ✅ Pode incluir repositórios privados
- ✅ Controle total

## 📝 URLs Alternativas (Backup)

### GitHub Stats:
```
https://github-readme-stats.vercel.app/api?username=IvanMarra
https://github-readme-stats-git-main-anuraghazra.vercel.app/api?username=IvanMarra
```

### GitHub Streak:
```
https://github-readme-streak-stats.herokuapp.com/?user=IvanMarra
https://streak-stats.demolab.com/?user=IvanMarra
```

## ✅ Verificação Final

1. ✅ Username correto no README.md
2. ✅ Pelo menos 1 commit no GitHub
3. ✅ URLs testadas no navegador
4. ✅ Aguardou alguns minutos para cache

Se ainda não funcionar, verifique:
- Se o repositório é público (estatísticas privadas requerem token)
- Se há algum bloqueador de imagens no navegador
- Se o GitHub não está bloqueado na sua rede

