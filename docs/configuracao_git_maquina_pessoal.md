# Guia de Configuração do Git com GitHub Personal Access Token

## 🎯 Objetivo

Este guia ajuda você a configurar o Git em sua **máquina pessoal** para trabalhar com repositórios do GitHub usando um Personal Access Token (PAT) ou GitHub Desktop.

## ⚠️ AVISOS IMPORTANTES DE SEGURANÇA

### ❌ NUNCA execute este script em:
- Computadores do laboratório da universidade
- Computadores compartilhados
- Computadores públicos
- Máquinas de outras pessoas

### ✅ EXECUTE APENAS em:
- Seu computador pessoal
- Sua máquina virtual pessoal
- Seu notebook pessoal

### 🔐 Sobre o Token:
- O token dá acesso total aos seus repositórios
- NUNCA compartilhe seu token com ninguém
- NUNCA poste seu token em fóruns ou grupos
- NUNCA commite seu token em repositórios

## 📋 Pré-requisitos

1. **Conta no GitHub**: Você precisa ter uma conta ativa
2. **Git instalado**: O Git deve estar instalado em sua máquina
   ```bash
   # Verificar se o Git está instalado
   git --version
   
   # Se não estiver instalado:
   # Ubuntu/Debian:
   sudo apt install git
   
   # Fedora:
   sudo dnf install git
   
   # macOS:
   brew install git
   
   # Windows:
   # Baixe de https://git-scm.com/download/win
   ```

## 📱 Opção 1: GitHub Desktop (Recomendado para Iniciantes)

### Windows/Mac:
1. **Baixe o GitHub Desktop**: https://desktop.github.com/
2. **Instale e abra** o aplicativo
3. **Faça login** com sua conta GitHub
4. **Clone seu repositório**:
   - Clique em "Clone a repository from the Internet"
   - Procure por `lab1-introducao-SEU_USUARIO`
   - Escolha onde salvar
5. **Pronto!** Use o botão "Open in Visual Studio Code" para editar

### Fazendo commits com GitHub Desktop:
1. Faça suas alterações nos arquivos
2. No GitHub Desktop, veja as mudanças na aba "Changes"
3. Escreva uma mensagem de commit
4. Clique em "Commit to main"
5. Clique em "Push origin" para enviar

## 🔧 Opção 2: Configuração Manual com Token

### Passo 1: Criar o Token no GitHub

1. **Acesse**: https://github.com/settings/tokens/new
2. **Faça login** no GitHub
3. **Configure o token**:
   - Nome: `Git Lab SO 2025`
   - Expiração: `90 days`
   - Escopo: Marque apenas `☑️ repo`
4. **Gere o token** clicando em "Generate token"
5. **COPIE O TOKEN IMEDIATAMENTE** (começa com `ghp_`)

### Passo 2: Configurar o Git

```bash
# Configure nome e email
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"

# Configure o credential helper
git config --global credential.helper store
```

### Passo 3: Usar o Token

Quando fizer o primeiro push, o Git pedirá suas credenciais:
- **Username**: seu usuário do GitHub
- **Password**: cole o TOKEN (não sua senha!)

## 🎉 Após a Configuração

### Você poderá:
- Clonar repositórios privados sem pedir senha
- Fazer push/pull sem autenticação adicional
- Usar todos os comandos Git normalmente

### Exemplo de uso:
```bash
# Clonar seu repositório do laboratório
git clone https://github.com/disciplina-so/lab1-introducao-SEU_USUARIO.git

# Fazer suas alterações
cd lab1-introducao-SEU_USUARIO
# ... executar exercícios ...

# Enviar para o GitHub
git add .
git commit -m "Completei exercícios do laboratório 1"
git push
```

## 🔧 Solução de Problemas

### Erro: "Token inválido"
- Verifique se copiou o token completo
- O token deve começar com `ghp_`
- Certifique-se de que marcou o escopo `repo`

### Erro: "Permission denied" ao fazer push
- Execute o script novamente
- Gere um novo token se necessário
- Verifique se o token não expirou

### Como verificar se está configurado:
```bash
# Ver configuração atual
git config --global --list | grep url

# Deve mostrar algo como:
# url.https://ghp_XXXXX@github.com/.insteadof=https://github.com/
```

## 🗑️ Como Remover/Revogar o Token

### No GitHub:
1. Acesse: https://github.com/settings/tokens
2. Encontre o token "Git Lab SO 2025"
3. Clique em "Delete"

### Na sua máquina:
```bash
# Remover configuração do token
git config --global --unset url."https://github.com/".insteadOf

# Limpar credenciais salvas
rm ~/.git-credentials

# Verificar que foi removido
git config --global --list | grep url
```

## 📅 Renovação do Token

Tokens expiram após o período configurado (recomendamos 90 dias).

### Quando renovar:
- Antes do token expirar
- Se receber erro de autenticação
- No início de um novo semestre

### Como renovar:
1. Revogue o token antigo no GitHub
2. Execute o script novamente
3. Crie um novo token

## 🆘 Suporte

### Documentação Adicional:
- [Documentação oficial do GitHub sobre PATs](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- [Guia do Git](docs/guia_git.md)

### Problemas Comuns:

**P: Posso usar o mesmo token em múltiplas máquinas?**
R: Tecnicamente sim, mas não é recomendado por segurança. Crie um token para cada máquina.

**P: O que fazer se perdi meu token?**
R: Tokens não podem ser recuperados. Revogue o antigo e crie um novo.

**P: É seguro salvar o token no Git config?**
R: Sim, quando usado apenas em sua máquina pessoal. O token fica em arquivos de configuração locais com permissões restritas.

**P: Posso usar SSH em vez de token?**
R: Sim, SSH é uma alternativa. Veja a documentação do GitHub sobre configuração de chaves SSH.

## 🔑 Opção 3: SSH (Avançado)

Para usuários mais experientes:

```bash
# 1. Gerar chave SSH
ssh-keygen -t ed25519 -C "seu.email@exemplo.com"

# 2. Adicionar chave ao ssh-agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# 3. Copiar chave pública
cat ~/.ssh/id_ed25519.pub

# 4. Adicionar no GitHub:
# Settings > SSH and GPG keys > New SSH key

# 5. Testar conexão
ssh -T git@github.com

# 6. Clonar usando SSH
git clone git@github.com:disciplina-so/lab1-introducao-SEU_USUARIO.git
```

## 📝 Notas Finais

- **GitHub Desktop** é mais fácil para iniciantes
- **Token** é útil para linha de comando
- **SSH** é mais seguro para uso avançado
- O token é salvo em `~/.git-credentials` (nunca compartilhe este arquivo)
- As configurações são globais e afetam todos os repositórios Git em sua máquina

---

**Lembre-se**: A segurança do seu token é sua responsabilidade. Trate-o como uma senha!