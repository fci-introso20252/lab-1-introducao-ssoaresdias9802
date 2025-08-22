# 🌳 Guia Básico do Git

Este guia apresenta os comandos essenciais do Git para completar o laboratório.

## 🤔 O que é Git?

Git é um sistema de controle de versão que permite:
- Salvar diferentes versões do seu código
- Sincronizar trabalho com repositórios remotos (como GitHub)
- Colaborar com outras pessoas em projetos

## 📖 Conceitos Básicos

### 📁 Working Directory (Diretório de Trabalho)
É onde você edita seus arquivos. As mudanças aqui ainda não foram salvas no Git.

### 📦 Staging Area (Área de Preparação) 
Local temporário onde você prepara quais mudanças quer salvar. Use `git add` para mover arquivos para aqui.

### 🗄️ Repository (Repositório)
Onde o Git armazena todas as versões salvas do seu projeto. Use `git commit` para salvar mudanças definitivamente.

### ☁️ Envio para o GitHub
Depois de salvar suas mudanças com o `git commit`, você envia para o repositório remoto no GitHub com `git push`. Assim você mantém seu repositório remoto atualizado com suas alterações locais e pode acessá-lo de qualquer lugar.

## 🔧 Comandos Essenciais

### 1️⃣ Clonar o Repositório

No GitHub Classroom, você receberá um link. Depois de aceitar, clone assim:

```bash
# Substitua SEU_USUARIO pelo seu usuário do GitHub
git clone https://github.com/fci-introso20252/lab1-introducao-SEU_USUARIO.git

# Entre no diretório
cd lab1-introducao-SEU_USUARIO
```

**Obs.:** Se você utilizar o Github Codespaces não é necessário clonar o repositório, pois ele já estará disponível no ambiente.

### 2️⃣ Verificar Status

Sempre verifique o status antes de fazer qualquer operação:

```bash
# Ver quais arquivos foram modificados
git status
```

**Exemplo de saída:**
```
On branch main
Changes not staged for commit:
  modified:   RELATORIO.md

Untracked files:
  outputs/ex1_pwd.txt
  meu_diretorio/
```

### 3️⃣ Adicionar Arquivos (Staging)

Adicione os arquivos que você quer salvar:

```bash
# Adicionar arquivo específico
git add RELATORIO.md

# Adicionar todos os arquivos modificados
git add .

# Adicionar todos os arquivos de uma pasta
git add outputs/
```

### 4️⃣ Fazer Commit (Salvar)

Salve suas mudanças com uma mensagem descritiva do que você fez:

```bash
# Commit com mensagem
git commit -m "Completei exercícios de comandos básicos"

# Se quiser usar uma mensagem mais detalhada
git commit -m "Completei laboratório 1
- Exercícios de navegação
- Criação de arquivos e diretórios
- Relatório preenchido"
```

### 5️⃣ Enviar para o GitHub (Push)

Envie suas mudanças para o repositório remoto:

```bash
# Enviar para branch main
git push origin main

# Ou simplesmente (depois da primeira vez)
git push
```

## 🔄 Fluxo do Laboratório

Aqui está o fluxo típico que você seguirá:

```bash
# 1. Clone (só uma vez, no início) - Não precisa fazer no Codespaces
git clone https://github.com/fci-introso20252/lab1-introducao-SEU_USUARIO.git
cd lab1-introducao-SEU_USUARIO

# 2. Trabalhe nos exercícios
# (edite arquivos, compile, teste)

# 3. Veja o que mudou
git status

# 4. Adicione suas mudanças (o . vai adicionar todas as mudancas no staging)
git add .

# 5. Faça commit
git commit -m "Completei exercícios de comandos básicos"

# 6. Envie para o GitHub
git push

# Repita passos 2-6 conforme necessário
```

## 💻 Exemplo Prático

Vamos simular o fluxo de completar os exercícios:

```bash
# Ver estado atual
git status

# Executar exercícios de comandos
pwd > outputs/ex1_pwd.txt
ls > outputs/ex2_ls_simples.txt
mkdir meu_diretorio
touch meu_diretorio/arquivo1.txt

# Preencher relatório
# Se estiver no Codespaces, use o editor integrado
# Ou use um editor de linha de comando
vim RELATORIO.md

# Ver o que mudou
git status
# Saída: modified: RELATORIO.md
#        untracked: outputs/
#        untracked: meu_diretorio/

# Adicionar mudanças (você pode usar git add . para adicionar todas as mudanças)
git add RELATORIO.md
git add outputs/
git add meu_diretorio/

# Verificar que está pronto para commit
git status
# Saída: Changes to be committed:
#          modified: RELATORIO.md
#          new file: outputs/ex1_pwd.txt
#          new file: outputs/ex2_ls_simples.txt
#          new file: meu_diretorio/arquivo1.txt

# Fazer commit
git commit -m "Completei exercícios e relatório do laboratório 1"

# Enviar
git push
```

## ✨ Comandos Úteis Extras

### 📊 Ver Histórico de Commits
```bash
# Ver últimos commits
git log --oneline

# Ver com detalhes
git log
```

### 🔍 Ver Diferenças
```bash
# Ver o que mudou em arquivos modificados
git diff

# Ver diferenças de arquivo específico
git diff RELATORIO.md
```

### ⚠️ Desfazer Mudanças (CUIDADO!)
```bash
# Desfazer mudanças em arquivo específico (perde trabalho!)
git checkout -- RELATORIO.md

# Remover arquivo do staging
git reset RELATORIO.md
```

## 🔧 Problemas Comuns

### 🔒 "Permission denied" no push
Se você não conseguir fazer push, verifique se:
1. Aceitou o convite do GitHub Classroom
2. Está usando a URL correta do seu repositório
3. Está logado no GitHub (pode precisar configurar SSH ou token caso esteja na sua máquina pessoal).

### 💭 "Nothing to commit"
Se aparecer esta mensagem:
1. Verifique se salvou os arquivos editados
2. Use `git status` para ver se há mudanças
3. Use `git add` para adicionar arquivos ao staging

### 📝 Mensagem de commit obrigatória
Se esquecer da mensagem:
```bash
# Git vai abrir um editor. Digite a mensagem, salve e feche
git commit

# Ou sempre use -m
git commit -m "Sua mensagem aqui"
```

## ⚙️ Configuração Inicial (Opcional)

Se for a primeira vez usando Git na sua máquina pessoal:

```bash
# Configurar nome e email (aparece nos commits)
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"

# Editor padrão (opcional)
git config --global core.editor code
```

## 📝 Resumo dos Comandos

| Comando | O que faz |
|---------|-----------|
| `git clone <url>` | Baixa repositório do GitHub |
| `git status` | Mostra estado atual |
| `git add <arquivo>` | Adiciona arquivo ao staging |
| `git add .` | Adiciona todos os arquivos |
| `git commit -m "msg"` | Salva mudanças com mensagem |
| `git push` | Envia para GitHub |
| `git log` | Mostra histórico |
| `git diff` | Mostra diferenças |

## 📚 Para Saber Mais

- [Git - Guia Prático](https://rogerdudler.github.io/git-guide/index.pt_BR.html)
- [GitHub Docs](https://docs.github.com/pt)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)
- [Configuração da autenticação no Github na máquina pessoal](docs/configuracao_git_maquina_pessoal.md)


**Lembre-se:** No laboratório, você só precisa dos comandos básicos: `status`, `add`, `commit`, `push`. Não precisa complicar!