[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/DEbGvfBP)
# 🐧 Laboratório 1 - Introdução ao Linux

**Professor:** Lucas Figueiredo  
**Email:** lucas.figueiredo@mackenzie.br

Aprenda os comandos básicos do Linux e explore as diferenças entre sistemas operacionais através de prática hands-on no terminal.

## 🚀 Quick Start

### ☁️ Opção 1: GitHub Codespaces (Recomendado ✅)
Use o ambiente cloud pré-configurado - sem necessidade de configuração!
Veja [`docs/guia_codespaces.md`](docs/guia_codespaces.md)

### 💻 Opção 2: Máquina Pessoal (Linux/WSL)
```bash
# Clone seu repositório (substitua SEU_USUARIO)
git clone https://github.com/disciplina-so/lab1-introducao-SEU_USUARIO.git
cd lab1-introducao-SEU_USUARIO

# Explore os comandos Linux
ls
pwd
```

⚠️ **APENAS para máquina pessoal**: Se precisar configurar autenticação Git/GitHub, veja [`docs/configuracao_git_maquina_pessoal.md`](docs/configuracao_git_maquina_pessoal.md)  
❌ **NUNCA** execute essa configuração em computadores do laboratório!

## 📚 O que Ler Primeiro

1. [`docs/guia_shell_basico.md`](docs/guia_shell_basico.md) - Comandos essenciais do Linux
2. [`EXERCICIOS.md`](EXERCICIOS.md) - Instruções detalhadas dos exercícios
3. [`docs/comparacao_windows_linux.md`](docs/comparacao_windows_linux.md) - Diferenças entre os sistemas
4. [`RELATORIO.md`](RELATORIO_.md) - Relatório do laboratório para preencher

## 📁 Estrutura do Projeto

```
lab1-introducao/
├── exemplos/              # Arquivos de exemplo para praticar os comandos
│   ├── origem.txt        # História e conceitos do Linux
│   ├── teste1.txt        # Lista de comandos básicos
│   └── teste2.txt        # Estrutura de diretórios
├── outputs/              # Seus outputs dos exercícios
├── docs/                 # Documentação completa
│   ├── guia_shell_basico.md
│   ├── comparacao_windows_linux.md
│   ├── guia_codespaces.md
│   ├── guia_git.md
│   └── configuracao_git_maquina_pessoal.md
├── EXERCICIOS.md         # Instruções dos exercícios
└── RELATORIO.md          # Seu relatório (a preencher)
```

## 🎯 Objetivos de Aprendizagem

Ao completar este laboratório, você será capaz de:
- ✅ Navegar no sistema de arquivos Linux usando comandos
- ✅ Criar, copiar, mover e remover arquivos e diretórios
- ✅ Entender a estrutura de diretórios do Linux
- ✅ Comparar Linux e Windows do ponto de vista gerencial
- ✅ Usar Git para versionamento de código
- ✅ Trabalhar com ambientes de desenvolvimento na nuvem

## 📖 Documentação

### 📋 Guias Principais
- [`docs/guia_shell_basico.md`](docs/guia_shell_basico.md) - Cheatsheet de comandos Linux
- [`docs/guia_codespaces.md`](docs/guia_codespaces.md) - Desenvolvimento na nuvem
- [`docs/guia_git.md`](docs/guia_git.md) - Comandos Git para submissão
- [`docs/comparacao_windows_linux.md`](docs/comparacao_windows_linux.md) - Windows vs Linux

### ⚙️ Configuração (Apenas Máquina Pessoal)
- [`docs/configuracao_git_maquina_pessoal.md`](docs/configuracao_git_maquina_pessoal.md) - Configurar Git/GitHub

## ⚡ Referência Rápida

### 🔍 Comandos Essenciais
```bash
pwd                  # Onde estou?
ls                   # O que tem aqui?
cd diretorio         # Entrar em diretório
cd ..                # Voltar um nível
mkdir novo_dir       # Criar diretório
touch arquivo.txt    # Criar arquivo
cat arquivo.txt      # Ver conteúdo
cp origem destino    # Copiar
mv origem destino    # Mover/renomear
rm arquivo           # Remover
```

### 📝 Salvando Outputs
```bash
# Salvar saída de comando em arquivo
ls -la > outputs/lista_arquivos.txt

# Adicionar ao final do arquivo
echo "Novo texto" >> outputs/anotacoes.txt
```

## 📤 Submissão

Após completar os exercícios e preencher o relatório:

```bash
git add .
git commit -m "Completei laboratório 1"
git push
```

## ✅ Checklist de Entrega

- [ ] Completei todos os exercícios em [`EXERCICIOS.md`](EXERCICIOS.md)
- [ ] Salvei os outputs dos comandos em `outputs/`
- [ ] Preenchi o relatório `RELATORIO.md`
- [ ] Fiz commit e push das alterações

## ❓ Ajuda

- Esqueceu um comando? Veja [`docs/guia_shell_basico.md`](docs/guia_shell_basico.md)
- Problemas com Git? Consulte [`docs/guia_git.md`](docs/guia_git.md)
- Dúvidas sobre Codespaces? Leia [`docs/guia_codespaces.md`](docs/guia_codespaces.md)