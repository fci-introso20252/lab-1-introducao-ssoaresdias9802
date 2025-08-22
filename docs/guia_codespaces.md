# ☁️ Guia do GitHub Codespaces

## 🤔 O que é GitHub Codespaces?

GitHub Codespaces é um ambiente de desenvolvimento baseado em nuvem que permite usar Linux diretamente no navegador. É ideal para este laboratório pois garante que todos tenham acesso ao mesmo ambiente Linux, independente do sistema operacional do seu computador.

## 📊 Limites da Versão Gratuita

- **120 core hours por mês**: Equivale a 60 horas em uma máquina de 2 cores
- **15 GB de armazenamento**: Suficiente para este laboratório e todos os labs futuros
- **Renovação mensal**: Os limites resetam no início de cada mês

## 🚀 Iniciando com Codespaces

### 🏭 Criando seu Codespace

1. Acesse o repositório do laboratório no GitHub
2. Clique no botão verde **Code**
3. Selecione a aba **Codespaces**
4. Clique em **Create codespace on main**
5. Aguarde o ambiente ser provisionado (1-2 minutos)

O Codespace virá automaticamente configurado com:
- Terminal Linux completo
- Todos os comandos básicos do Linux
- Editor de texto integrado
- Git para versionamento

## 🔄 Fluxo de Desenvolvimento

### 🖥️ Interface do VS Code

O Codespaces usa uma versão web do VS Code com:
- **Explorer** (esquerda): Navegação de arquivos
- **Editor** (centro): Edição de código
- **Terminal** (inferior): Execução de comandos
- **Source Control** (esquerda): Gerenciamento do Git

### 💻 Executando Comandos Linux

No terminal integrado, você pode executar todos os comandos Linux:

```bash
# Navegação
pwd
ls
cd diretório

# Manipulação de arquivos
touch arquivo.txt
mkdir novo_diretorio
cp origem destino
mv arquivo novo_nome
```

### 📝 Salvando Outputs dos Comandos

Redirecione saídas de comandos para arquivos:

```bash
# Salvar output em arquivo
ls > outputs/lista.txt

# Adicionar ao final do arquivo
echo "Nova linha" >> outputs/arquivo.txt

# Ver conteúdo de arquivo
cat arquivo.txt
```

## 📁 Gerenciamento de Arquivos

### 📂 Estrutura de Diretórios

```
lab1-introducao/
├── exemplos/     # Arquivos de exemplo
├── outputs/      # Seus outputs dos exercícios
├── docs/         # Documentações
├── EXERCICIOS.md # Instruções dos exercícios
└── RELATORIO.md  # Seu relatório
```

### 📝 Criando e Organizando Arquivos

1. **Criar arquivo**: Clique direito na pasta → New File
2. **Criar pasta**: Clique direito → New Folder
3. **Upload de arquivo**: Arraste e solte no Explorer
4. **Download**: Clique direito no arquivo → Download

### 💾 Salvando Outputs

Sempre salve os outputs dos comandos na pasta `outputs/`:

```bash
# Criar pasta se não existir
mkdir -p outputs

# Salvar outputs dos comandos
pwd > outputs/ex1_pwd.txt
ls -la > outputs/ex2_ls.txt
```

## 🌳 Operações Git no Codespaces

### 🎨 Usando a Interface Gráfica

1. **Source Control** (ícone de branch na barra lateral)
2. Adicione os arquivos no staging clicando no **+**
3. Digite a mensagem de commit
4. Clique no **✓** para commitar
5. Use **...** → Push para enviar para o repositório remoto

### 💻 Usando o Terminal

```bash
# Verificar status
git status

# Adicionar arquivos
git add RELATORIO.md
git add outputs/

# Commitar
git commit -m "Completei exercícios de comandos básicos"

# Enviar para GitHub
git push
```

Para comandos Git detalhados, consulte o [Guia Git](guia_git.md).

## ✅ Boas Práticas

### ⏱️ Economizando Core Hours

1. **Pare o Codespace quando não estiver usando**:
   - Codespaces → ⋮ → Stop codespace
   - Ou deixe parar automaticamente após 30 min de inatividade

2. **Verifique seu uso**:
   - Settings → Billing → Codespaces
   - Monitore suas core hours restantes

### 💾 **Commite e push frequentemente**
- O Codespace pode ser interrompido e você não quer perder progresso.

### ⚡ Performance

- Use máquina de **2 cores** para este lab (padrão)
- Evite abrir múltiplos Codespaces simultaneamente
- Feche abas desnecessárias no navegador

## 🔧 Troubleshooting

### ⚠️ Problemas Comuns

**Codespace não inicia:**
- Verifique se não excedeu o limite mensal
- Tente deletar e recriar o Codespace

**Comando não encontrado:**
- O ambiente pode ainda estar carregando
- Tente: `sudo apt update && sudo apt install [pacote]`

**Permissão negada:**
- Use `chmod +x programa` para tornar executável
- Para traces: verifique se a pasta existe

**Git push falha:**
- Verifique se está autenticado
- Use o terminal se a interface gráfica falhar

### 🔄 Instalando Ferramentas Adicionais

Se alguma ferramenta estiver faltando:

```bash
# Atualizar pacotes
sudo apt update

# Instalar tree (visualizar estrutura de diretórios)
sudo apt install tree

# Instalar nano (editor de texto simples)
sudo apt install nano

# Instalar htop (monitor de processos)
sudo apt install htop
```

## 🔄 Alternativa ao Codespaces

Se atingir o limite mensal, considere um **desenvolvimento local**. Veja como configurar na sua máquina pessoal [aqui](docs/configuracao_git_maquina_pessoal.md)

## 📚 Recursos Adicionais

- [Documentação oficial do Codespaces](https://docs.github.com/en/codespaces)
- [Atalhos de teclado do VS Code](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)
- [Guia de Git](guia_git.md) para comandos detalhados

## ✔️ Checklist Rápido

Antes de começar os exercícios:
- [ ] Codespace criado e rodando
- [ ] Terminal aberto e funcionando
- [ ] Comando `pwd` mostra o diretório atual
- [ ] Comando `ls` lista arquivos
- [ ] Pasta `outputs/` criada
- [ ] Git configurado (nome e email)