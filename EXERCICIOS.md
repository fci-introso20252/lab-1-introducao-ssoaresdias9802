# 📝 Exercícios do Laboratório 1 - Comandos Básicos do Linux

Este arquivo contém instruções detalhadas para cada exercício. Siga os passos na ordem para completar o laboratório.

## 🎯 Objetivo

Aprender a usar os comandos básicos do Linux através de prática hands-on no terminal. Você executará comandos e salvará os resultados em arquivos para verificação.

## 🏁 Preparação Inicial

### 1. Verificar onde você está

```bash
# Mostrar diretório atual
pwd
```

### 2. Explorar a estrutura

```bash
# Listar conteúdo do diretório
ls

# Listar com detalhes
ls -la
```

---

## 📚 Parte 1: Comandos de Navegação

### Exercício 1.1 - Descobrindo onde estou

Execute os comandos abaixo e salve o resultado (com > ou >>).:

```bash
# Mostrar diretório atual
pwd > outputs/ex1_pwd.txt

# Mostrar usuário atual
whoami >> outputs/ex1_pwd.txt

# Mostrar data e hora
date >> outputs/ex1_pwd.txt
```

### Exercício 1.2 - Listando arquivos

```bash
# Listar arquivos do diretório atual
ls > outputs/ex2_ls_simples.txt

# Listar com detalhes (mostra permissões, tamanho, etc)
ls -la > outputs/ex2_ls_detalhado.txt

# Listar apenas o diretório exemplos
ls exemplos/ > outputs/ex2_ls_exemplos.txt
```

### Exercício 1.3 - Navegando entre diretórios

```bash
# Entrar no diretório exemplos
cd exemplos

# Verificar onde estou agora
pwd > ../outputs/ex3_navegacao.txt

# Voltar ao diretório anterior
cd ..

# Verificar novamente
pwd >> outputs/ex3_navegacao.txt

# Entrar no diretório docs
cd docs
pwd >> ../outputs/ex3_navegacao.txt

# Voltar para o diretório pai (lab1-introducao)
cd ..

# Entrar no diretório outputs
cd outputs
pwd >> ex3_navegacao.txt

# Voltar ao diretório do laboratório usando cd -
cd ..
cd exemplos
cd -  # Volta para o diretório anterior (lab1-introducao)
pwd >> outputs/ex3_navegacao.txt
```

---

## 📁 Parte 2: Criando e Manipulando Arquivos

### Exercício 2.1 - Criando arquivos e diretórios

```bash
# Criar um novo diretório
mkdir meu_diretorio

# Criar subdiretórios
mkdir -p meu_diretorio/subdir1/subdir2

# Criar arquivos vazios
touch meu_diretorio/arquivo1.txt
touch meu_diretorio/arquivo2.txt

# Verificar o que foi criado
ls -la meu_diretorio > outputs/ex4_criacao.txt
```

### Exercício 2.2 - Escrevendo em arquivos

```bash
# Escrever algum texto em arquivo
echo "Meu primeiro arquivo no Linux" > meu_diretorio/primeiro.txt

# Adicionar mais texto
echo "Segunda linha do arquivo" >> meu_diretorio/primeiro.txt

# Ver conteúdo do arquivo
cat meu_diretorio/primeiro.txt > outputs/ex5_escrita.txt

# Criar arquivo com múltiplas linhas
echo -e "Linha 1\nLinha 2\nLinha 3" > meu_diretorio/multiplas.txt
cat meu_diretorio/multiplas.txt >> outputs/ex5_escrita.txt
```

### Exercício 2.3 - Copiando arquivos

```bash
# Copiar arquivo individual
cp exemplos/teste1.txt meu_diretorio/

# Copiar com outro nome
cp exemplos/teste2.txt meu_diretorio/estrutura.txt

# Copiar múltiplos arquivos
cp exemplos/*.txt meu_diretorio/subdir1/

# Verificar cópias
ls -la meu_diretorio/ > outputs/ex6_copia.txt
ls -la meu_diretorio/subdir1/ >> outputs/ex6_copia.txt
```

### Exercício 2.4 - Movendo e renomeando

```bash
# Renomear arquivo
mv meu_diretorio/arquivo1.txt meu_diretorio/arquivo_renomeado.txt

# Mover arquivo para subdiretório
mv meu_diretorio/arquivo2.txt meu_diretorio/subdir1/

# Verificar mudanças
ls -la meu_diretorio/ > outputs/ex7_mover.txt
ls -la meu_diretorio/subdir1/ >> outputs/ex7_mover.txt
```

---

## 📖 Parte 3: Lendo e Processando Arquivos

### Exercício 3.1 - Visualizando conteúdo

```bash
# Ver arquivo completo
cat exemplos/origem.txt > outputs/ex8_cat.txt

# Ver primeiras linhas
head -5 exemplos/origem.txt > outputs/ex8_head.txt

# Ver últimas linhas
tail -5 exemplos/origem.txt > outputs/ex8_tail.txt

# Contar linhas, palavras e caracteres
wc exemplos/origem.txt > outputs/ex8_wc.txt
```

### Exercício 3.2 - Buscando em arquivos

```bash
# Buscar palavra em arquivo
grep "Linux" exemplos/origem.txt > outputs/ex9_grep.txt

# Buscar com número da linha
grep -n "Diretório" exemplos/teste2.txt >> outputs/ex9_grep.txt

# Buscar em múltiplos arquivos
grep "comando" exemplos/*.txt >> outputs/ex9_grep.txt
```

### Exercício 3.3 - Redirecionamento e pipes

```bash
# Combinar comandos com pipe
ls -la | head -5 > outputs/ex10_pipe.txt

# Contar arquivos no diretório
ls | wc -l > outputs/ex10_count.txt

# Ordenar e mostrar únicos
ls exemplos/ | sort | uniq > outputs/ex10_sort.txt
```

---

## 💻 Parte 4: Informações do Sistema

### Exercício 4.1 - Sistema operacional

```bash
# Informações do kernel
uname -a > outputs/ex11_sistema.txt

# Versão do sistema
cat /etc/os-release >> outputs/ex11_sistema.txt

# Espaço em disco
df -h >> outputs/ex11_sistema.txt

# Memória disponível
free -h >> outputs/ex11_sistema.txt
```

### Exercício 4.2 - Processos

```bash
# Processos em execução
ps aux | head -10 > outputs/ex12_processos.txt

# Árvore de processos
pstree | head -20 >> outputs/ex12_processos.txt

# Uso de recursos
top -b -n 1 | head -20 >> outputs/ex12_processos.txt
```

---

## 🔍 Parte 5: Histórico e Ajuda

### Exercício 5.1 - Histórico de comandos

```bash
# Ver histórico
history | tail -20 > outputs/ex13_historico.txt

# Executar comando do histórico (exemplo)
!pwd

# Buscar no histórico
history | grep "mkdir" >> outputs/ex13_historico.txt
```

### Exercício 5.2 - Obtendo ajuda

```bash
# Manual do comando ls
man ls | head -20 > outputs/ex14_ajuda.txt

# Ajuda rápida
ls --help | head -20 >> outputs/ex14_ajuda.txt

# Informações sobre comando
which ls >> outputs/ex14_ajuda.txt
type ls >> outputs/ex14_ajuda.txt
```

---

## ✅ Verificação Final

### Conferir todos os arquivos criados

```bash
# Listar todos os outputs
ls -la outputs/ > outputs/verificacao_final.txt

# Contar quantos arquivos foram criados
ls outputs/ | wc -l >> outputs/verificacao_final.txt

# Verificar estrutura criada
tree meu_diretorio/ >> outputs/verificacao_final.txt 2>/dev/null || ls -R meu_diretorio/ >> outputs/verificacao_final.txt
```

---

## 📤 Entrega

Após completar todos os exercícios:

1. **Verifique se todos os arquivos foram criados:**
```bash
ls outputs/
```

Você deve ter pelo menos 19 arquivos de output (ex1 ao ex14) + verificacao_final.txt

2. **Preencha o relatório `RELATORIO.md`** com suas observações

3. **Verifique se ainda existe alguma lacuna no relatório a ser preenchida:**
```bash
cat RELATORIO.md | grep -i "Sua resposta aqui"  # Verifica se há lacunas
```
Se não retornar nada, você está pronto para enviar!

4. **Adicione e faça commit das alterações:**
```bash
git add .
git commit -m "Completei exercícios do laboratório 1"
git push
```

---

## 🆘 Problemas Comuns

### Diretório outputs não existe
```bash
# Criar o diretório
mkdir -p outputs
```

### Permissão negada
```bash
# Dar permissão de execução
chmod +x nome_do_arquivo
```

### Comando não encontrado
```bash
# Verificar se o comando existe
which nome_do_comando

# Instalar se necessário (exemplo)
sudo apt update
sudo apt install tree
```

### Arquivo não foi salvo
```bash
# Verificar se o redirecionamento funcionou
cat outputs/nome_do_arquivo.txt
```

---

## 💡 Dicas

- Use `Tab` para autocompletar nomes de arquivos e comandos
- Use `↑` e `↓` para navegar pelo histórico
- Use `Ctrl+C` para cancelar um comando em execução
- Use `clear` ou `Ctrl+L` para limpar a tela
- Use `man comando` para ver o manual de qualquer comando

**Lembre-se:** Se tiver dúvidas, consulte [`docs/guia_shell_basico.md`](docs/guia_shell_basico.md) para uma referência rápida dos comandos!