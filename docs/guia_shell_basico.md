# 📘 Guia de Comandos Básicos do Shell Linux

Este guia apresenta os comandos essenciais do Linux para completar o laboratório.

## 🗂️ Navegação de Diretórios

### pwd - Print Working Directory
Mostra o diretório atual onde você está.
```bash
pwd
# Saída: /home/usuario/lab1-introducao
```

### ls - List
Lista arquivos e diretórios.
```bash
ls              # Lista simples
ls -l           # Lista detalhada com permissões
ls -la          # Lista todos, incluindo ocultos
ls -lh          # Lista com tamanhos legíveis
ls diretorio/   # Lista conteúdo de um diretório específico
```

### cd - Change Directory
Navega entre diretórios.
```bash
cd pasta           # Entra na pasta
cd ..              # Volta um nível
cd ~               # Vai para home
cd /               # Vai para raiz
cd -               # Volta ao diretório anterior
cd ../../../       # Volta 3 níveis
```

> **⚠️ IMPORTANTE - GitHub Codespaces:**
> - No Codespaces, o comando `cd ~` leva você para `/home/codespace`, que é FORA do seu repositório
> - **Arquivos criados fora do diretório do projeto NÃO serão salvos no GitHub!**
> - Sempre verifique que você está dentro do diretório do laboratório com `pwd`
> - O diretório do projeto geralmente está em `/workspaces/nome-do-repositorio`
> - Para voltar ao projeto após usar `cd ~`, use: `cd /workspaces/nome-do-repositorio/lab1-introducao`
> - Use caminhos relativos (`cd ..`, `cd exemplos/`) em vez de `cd ~` para evitar sair do projeto

## 📁 Manipulação de Arquivos e Diretórios

### mkdir - Make Directory
Cria novos diretórios.
```bash
mkdir pasta                    # Cria uma pasta
mkdir -p pasta/subpasta        # Cria estrutura completa
mkdir pasta1 pasta2 pasta3     # Cria múltiplas pastas
```

### touch
Cria arquivos vazios ou atualiza timestamp.
```bash
touch arquivo.txt              # Cria arquivo vazio
touch arq1.txt arq2.txt        # Cria múltiplos arquivos
```

### cp - Copy
Copia arquivos e diretórios.
```bash
cp origem.txt destino.txt      # Copia arquivo
cp -r pasta/ nova_pasta/       # Copia diretório completo
cp *.txt destino/              # Copia todos .txt
```

### mv - Move
Move ou renomeia arquivos e diretórios.
```bash
mv arquivo.txt novo_nome.txt   # Renomeia arquivo
mv arquivo.txt pasta/          # Move para pasta
mv pasta/ novo_nome/           # Renomeia diretório
```

### rm - Remove
Remove arquivos e diretórios (CUIDADO!).
```bash
rm arquivo.txt                 # Remove arquivo
rm -r pasta/                   # Remove diretório e conteúdo
rm -f arquivo.txt              # Força remoção
rm *.tmp                       # Remove todos .tmp
```

## 📖 Visualização de Conteúdo

### cat - Concatenate
Exibe conteúdo completo de arquivos.
```bash
cat arquivo.txt                # Mostra conteúdo
cat arq1.txt arq2.txt          # Mostra múltiplos arquivos
cat -n arquivo.txt             # Mostra com números de linha
```

### less / more
Visualiza arquivos grandes com paginação.
```bash
less arquivo.txt               # Navegue com setas, q para sair
more arquivo.txt               # Similar ao less, mais simples
```

### head / tail
Mostra início ou fim de arquivos.
```bash
head arquivo.txt               # Primeiras 10 linhas
head -n 5 arquivo.txt          # Primeiras 5 linhas
tail arquivo.txt               # Últimas 10 linhas
tail -n 20 arquivo.txt         # Últimas 20 linhas
tail -f arquivo.log            # Acompanha arquivo em tempo real
```

## ✏️ Criação e Edição de Conteúdo

### echo
Exibe texto ou cria conteúdo.
```bash
echo "Olá Mundo"                        # Exibe na tela
echo "Texto" > arquivo.txt              # Cria/sobrescreve arquivo
echo "Mais texto" >> arquivo.txt        # Adiciona ao arquivo
echo -e "Linha1\nLinha2"                # Múltiplas linhas
```

### Redirecionamento
Direciona entrada e saída de comandos.
```bash
comando > arquivo.txt           # Saída para arquivo (sobrescreve)
comando >> arquivo.txt          # Saída para arquivo (adiciona)
comando < arquivo.txt           # Entrada de arquivo
comando 2> erros.txt            # Erros para arquivo
comando &> tudo.txt             # Saída e erros para arquivo
```

### Pipe |
Conecta saída de um comando à entrada de outro.
```bash
ls | grep ".txt"                # Lista apenas arquivos .txt
cat arquivo | wc -l             # Conta linhas
ps aux | grep firefox           # Busca processo firefox
history | tail -20              # Últimos 20 comandos
```

## 🔍 Busca e Filtros

### grep
Busca padrões em arquivos ou saída.
```bash
grep "palavra" arquivo.txt      # Busca palavra
grep -i "palavra" arquivo.txt   # Busca sem case sensitive
grep -n "palavra" arquivo.txt   # Mostra número da linha
grep -r "palavra" pasta/        # Busca recursiva
grep -v "palavra" arquivo.txt   # Linhas SEM a palavra
```

### find
Busca arquivos e diretórios.
```bash
find . -name "*.txt"            # Busca todos .txt
find . -type d -name "teste"    # Busca diretórios "teste"
find . -size +1M                # Arquivos maiores que 1MB
find . -mtime -7                # Modificados nos últimos 7 dias
```

### wc - Word Count
Conta linhas, palavras e caracteres.
```bash
wc arquivo.txt                  # Linhas, palavras, bytes
wc -l arquivo.txt               # Apenas linhas
wc -w arquivo.txt               # Apenas palavras
wc -c arquivo.txt               # Apenas bytes
```

## 💻 Informações do Sistema

### whoami / id
Informações do usuário.
```bash
whoami                          # Nome do usuário
id                              # ID e grupos do usuário
```

### date / cal
Data e calendário.
```bash
date                            # Data e hora atual
date +%Y-%m-%d                  # Formato personalizado
cal                             # Calendário do mês
cal 2025                        # Calendário do ano
```

### uname
Informações do sistema.
```bash
uname                           # Nome do kernel
uname -a                        # Todas informações
uname -r                        # Versão do kernel
```

### df / du
Espaço em disco.
```bash
df -h                           # Espaço em disco (human readable)
du -sh pasta/                   # Tamanho de diretório
du -sh *                        # Tamanho de cada item
```

### free
Memória do sistema.
```bash
free -h                         # Memória em formato legível
free -m                         # Memória em MB
```

## 🔄 Processos

### ps
Lista processos.
```bash
ps                              # Processos do terminal atual
ps aux                          # Todos os processos
ps aux | grep nome              # Busca processo específico
```

### top / htop
Monitor de processos em tempo real.
```bash
top                             # Monitor de processos (q para sair)
htop                            # Versão melhorada (se instalado)
```

### kill
Encerra processos.
```bash
kill PID                        # Encerra processo pelo ID
kill -9 PID                     # Força encerramento
killall nome_processo           # Encerra por nome
```

## 📚 Histórico e Ajuda

### history
Histórico de comandos.
```bash
history                         # Lista todos comandos
history | tail -20              # Últimos 20 comandos
!100                            # Executa comando número 100
!!                              # Repete último comando
!cd                             # Repete último comando começando com 'cd'
```

### man / help
Manual e ajuda.
```bash
man comando                     # Manual completo
comando --help                  # Ajuda rápida
which comando                   # Localização do comando
type comando                    # Tipo do comando
```

## ⌨️ Atalhos Úteis do Terminal

| Atalho | Função |
|--------|--------|
| `Tab` | Autocompleta comandos e caminhos |
| `Tab Tab` | Mostra todas opções de autocompletar |
| `↑` / `↓` | Navega pelo histórico |
| `Ctrl + C` | Cancela comando em execução |
| `Ctrl + Z` | Suspende processo |
| `Ctrl + D` | Sai do terminal/EOF |
| `Ctrl + L` | Limpa tela (igual a `clear`) |
| `Ctrl + A` | Vai para início da linha |
| `Ctrl + E` | Vai para fim da linha |
| `Ctrl + R` | Busca reversa no histórico |

## 🔐 Permissões (Básico)

### chmod
Muda permissões de arquivos.
```bash
chmod +x script.sh              # Torna executável
chmod 755 arquivo               # rwxr-xr-x
chmod 644 arquivo               # rw-r--r--
```

### Entendendo Permissões
```
-rwxr-xr-x
│││││││││└─ Outros: execução
││││││││└── Outros: escrita
│││││││└─── Outros: leitura
││││││└──── Grupo: execução
│││││└───── Grupo: escrita
││││└────── Grupo: leitura
│││└─────── Dono: execução
││└──────── Dono: escrita
│└───────── Dono: leitura
└────────── Tipo (- arquivo, d diretório)
```

## 💡 Dicas Importantes

1. **Use Tab**: Sempre use Tab para autocompletar e evitar erros
2. **Cuidado com rm**: Não há lixeira! Arquivos deletados são perdidos
3. **Case sensitive**: Linux diferencia maiúsculas de minúsculas
4. **Espaços**: Use \ ou aspas para nomes com espaços
5. **Curingas**: * (qualquer coisa), ? (um caractere), [abc] (a, b ou c)

## 📝 Exemplos Práticos

```bash
# Criar estrutura de projeto
mkdir -p projeto/{src,docs,tests}
touch projeto/README.md
echo "# Meu Projeto" > projeto/README.md

# Backup de arquivos
cp -r projeto/ projeto_backup_$(date +%Y%m%d)

# Buscar e contar arquivos .txt
find . -name "*.txt" | wc -l

# Ver os 5 maiores arquivos
du -sh * | sort -rh | head -5

# Monitorar log em tempo real
tail -f /var/log/syslog

# Buscar comando no histórico
history | grep "git"
```

---

**Lembre-se**: A prática leva à perfeição! Experimente os comandos e não tenha medo de explorar.