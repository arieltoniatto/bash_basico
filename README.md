# 🐚 Bash Cheat Sheet

-  ## Navegação no Sistema de Arquivos
    
    ### 📂 `pwd`
    
    **Função:** Mostra o diretório atual.
    
    **Sintaxe:**
    
    ```bash
    pwd
    
    ```
    
    **Exemplo:**
    
    ```bash
    $ pwd
    /home/usuario/projetos
    
    ```
    
    ---
    
    ### 📂 `ls`
    
    **Função:** Lista arquivos e diretórios.
    
    **Sintaxe:**
    
    ```bash
    ls [opções] [caminho]
    
    ```
    
    **Exemplos:**
    
    ```bash
    ls               # Lista arquivos no diretório atual
    ls -l            # Lista em formato detalhado
    ls -a            # Lista incluindo arquivos ocultos
    ls /etc          # Lista o conteúdo de /etc
    
    ```
    
    ---
    
    ### 📂 `cd`
    
    **Função:** Navegar entre diretórios.
    
    **Sintaxe:**
    
    ```bash
    cd [caminho]
    
    ```
    
    **Exemplos:**
    
    ```bash
    cd /home/usuario      # Vai para o diretório /home/usuario
    cd ..                 # Volta um diretório
    cd -                  # Volta para o último diretório acessado
    cd                    # Vai para a home do usuário (~)
    
    ```    
   
    ---
    
    ### 📂 `find`
    
    **Função:** Localiza arquivos/diretórios em uma hierarquia.
    
    **Sintaxe:**
    
    ```bash
    find [caminho] [opções] [expressão]
    
    ```
    
    **Exemplos:**
    
    ```bash
    find . -name "*.txt"       # Busca arquivos .txt no diretório atual
    find /var -type d -name log # Busca diretórios chamados "log"
    
    ```
    
    ---
    
    ### 📂 `du`
    
    **Função:** Mostra uso de espaço em disco por arquivos/diretórios.
    
    **Sintaxe:**
    
    ```bash
    du [opções] [caminho]
    
    ```
    
    **Exemplos:**
    
    ```bash
    du -h              # Mostra uso em formato legível (KB, MB, GB)
    du -sh *           # Mostra tamanho de cada item no diretório atual
    
    ```
    
    ---
    
    ### 📂 `df`
    
    **Função:** Mostra o uso de espaço em disco das partições.
    
    **Sintaxe:**
    
    ```bash
    df [opções]
    
    ```
    
    **Exemplos:**
    
    ```bash
    df -h              # Mostra espaço usado/livre em formato legível
    df -T              # Mostra também o tipo do sistema de arquivos
    
    ```
    
- ## Manipulação de Arquivos e Diretórios
    
    ### 📄 `touch`
    
    **Função:** Cria arquivos vazios ou atualiza a data de modificação de um arquivo.
    
    **Sintaxe:**
    
    ```bash
    touch [arquivo]
    
    ```
    
    **Exemplos:**
    
    ```bash
    touch notas.txt          # Cria um arquivo vazio chamado notas.txt
    touch a.txt b.txt c.txt  # Cria múltiplos arquivos
    
    ```
    
    ---
    
    ### 📄 `cat`
    
    **Função:** Exibe o conteúdo de arquivos ou concatena arquivos.
    
    **Sintaxe:**
    
    ```bash
    cat [arquivo]
    
    ```
    
    **Exemplos:**
    
    ```bash
    cat notas.txt            # Mostra o conteúdo de notas.txt
    cat a.txt b.txt > c.txt  # Junta a.txt e b.txt em c.txt
    
    ```
    
    ---
    
    ### 📄 `less`
    
    **Função:** Visualiza arquivos de forma paginada (melhor para arquivos grandes).
    
    **Sintaxe:**
    
    ```bash
    less [arquivo]
    
    ```
    
    **Exemplos:**
    
    ```bash
    less /var/log/syslog     # Visualiza log do sistema
    
    ```
    
    📌 Atalhos úteis dentro do `less`:
    
    - `q` → sair
    - `Espaço` → próxima página
    - `/palavra` → buscar palavra
    
    ---
    
    ### 📄 `head` e `tail`
    
    **Função:** Mostra o início (`head`) ou final (`tail`) de um arquivo.
    
    **Sintaxe:**
    
    ```bash
    head [arquivo]
    tail [arquivo]
    
    ```
    
    **Exemplos:**
    
    ```bash
    head -n 5 notas.txt      # Mostra as 5 primeiras linhas
    tail -n 10 notas.txt     # Mostra as 10 últimas linhas
    tail -f /var/log/syslog  # Acompanha em tempo real o log
    
    ```
    
    ---
    
    ### 📄 `cp`
    
    **Função:** Copia arquivos e diretórios.
    
    **Sintaxe:**
    
    ```bash
    cp [opções] origem destino
    
    ```
    
    **Exemplos:**
    
    ```bash
    cp arquivo.txt backup.txt    # Copia arquivo.txt para backup.txt
    cp arquivo.txt /tmp/         # Copia para outro diretório
    cp -r pasta/ /tmp/           # Copia diretório recursivamente
    
    ```
    
    ---
    
    ### 📄 `mv`
    
    **Função:** Move ou renomeia arquivos/diretórios.
    
    **Sintaxe:**
    
    ```bash
    mv origem destino
    
    ```
    
    **Exemplos:**
    
    ```bash
    mv notas.txt /tmp/           # Move arquivo para /tmp
    mv notas.txt resumo.txt      # Renomeia arquivo
    mv pasta/ /home/usuario/     # Move diretório
    
    ```
    
    ---
    
    ### 📄 `rm`
    
    **Função:** Remove arquivos ou diretórios.
    
    ⚠️ **Cuidado!** Exclusão é permanente.
    
    **Sintaxe:**
    
    ```bash
    rm [opções] arquivo
    
    ```
    
    **Exemplos:**
    
    ```bash
    rm notas.txt                 # Remove arquivo
    rm -i notas.txt              # Pergunta antes de excluir
    rm -r pasta/                 # Remove diretório recursivamente
    rm -rf pasta/                # Força remoção sem perguntar
    
    ```
    
    ---
    
    ### 📄 `mkdir`
    
    **Função:** Cria diretórios.
    
    **Sintaxe:**
    
    ```bash
    mkdir [opções] nome_diretorio
    
    ```
    
    **Exemplos:**
    
    ```bash
    mkdir projetos               # Cria diretório
    mkdir -p pasta/subpasta      # Cria estrutura de diretórios
    
    ```
    
    ---
    
    ### 📄 `rmdir`
    
    **Função:** Remove diretórios vazios.
    
    **Sintaxe:**
    
    ```bash
    rmdir [diretorio]
    
    ```
    
    **Exemplos:**
    
    ```bash
    rmdir projetos               # Remove se estiver vazio
    
    ```
    
- ## Visualização e Edição de Conteúdo
    
    ### 🔍 `grep`
    
    **Função:** Busca por padrões em arquivos.
    
    **Sintaxe:**
    
    ```bash
    grep [opções] "padrão" arquivo
    
    ```
    
    **Exemplos:**
    
    ```bash
    grep "erro" syslog.txt         # Busca a palavra "erro" no arquivo
    grep -i "erro" syslog.txt      # Busca sem diferenciar maiúsculas/minúsculas
    grep -r "senha" /etc/          # Busca recursiva em diretórios
    grep -n "http" acesso.log      # Mostra número da linha junto
    
    ```
    
    ---
    
    ### 🔍 `wc`
    
    **Função:** Conta linhas, palavras e caracteres.
    
    **Sintaxe:**
    
    ```bash
    wc [opções] arquivo
    
    ```
    
    **Exemplos:**
    
    ```bash
    wc arquivo.txt                 # Mostra linhas, palavras e caracteres
    wc -l arquivo.txt              # Conta apenas linhas
    wc -w arquivo.txt              # Conta apenas palavras
    
    ```
    
    ---
    
    ### 🔍 `sort`
    
    **Função:** Ordena linhas de arquivos/texto.
    
    **Sintaxe:**
    
    ```bash
    sort [opções] arquivo
    
    ```
    
    **Exemplos:**
    
    ```bash
    sort nomes.txt                 # Ordena em ordem alfabética
    sort -r nomes.txt              # Ordem inversa
    sort -n numeros.txt            # Ordena numericamente
    
    ```
    
    ---
    
    ### 🔍 `uniq`
    
    **Função:** Remove linhas duplicadas consecutivas.
    
    **Sintaxe:**
    
    ```bash
    uniq [opções] arquivo
    
    ```
    
    **Exemplos:**
    
    ```bash
    sort lista.txt | uniq          # Ordena e remove duplicatas
    uniq -c lista.txt              # Mostra quantas vezes cada linha aparece
    
    ```
    
    ---
    
    ### 🔍 `cut`
    
    **Função:** Extrai colunas ou campos de texto.
    
    **Sintaxe:**
    
    ```bash
    cut [opções] arquivo
    
    ```
    
    **Exemplos:**
    
    ```bash
    cut -f1,3 -d"," dados.csv      # Mostra apenas colunas 1 e 3 (separador ",")
    cut -c1-5 texto.txt            # Mostra apenas os primeiros 5 caracteres de cada linha
    
    ```
    
    ---
    
    ### ✍️ `nano`
    
    **Função:** Editor de texto simples no terminal.
    
    **Sintaxe:**
    
    ```bash
    nano [arquivo]
    
    ```
    
    **Exemplo:**
    
    ```bash
    nano notas.txt
    
    ```
    
    📌 Atalhos úteis dentro do `nano`:
    
    - `Ctrl + O` → salvar
    - `Ctrl + X` → sair
    - `Ctrl + W` → buscar
    
    ---
    
    ### ✍️ `vim` (ou `vi`)
    
    **Função:** Editor de texto poderoso no terminal.
    
    **Sintaxe:**
    
    ```bash
    vim [arquivo]
    
    ```
    
    **Exemplo:**
    
    ```bash
    vim config.txt
    
    ```
    
    📌 Modos principais:
    
    - **Modo normal** (inicial) → navegação e comandos
    - **Modo inserção** → digitar texto (`i` para entrar, `Esc` para sair)
    - **Modo comando** → `:` seguido de instrução
    
    📌 Comandos úteis:
    
    - `:w` → salvar
    - `:q` → sair
    - `:wq` → salvar e sair
    - `:q!` → sair sem salvar
- ## Permissões e Usuários
    
    ### 👥 `whoami`
    
    **Função:** Mostra o usuário atual.
    
    **Sintaxe:**
    
    ```bash
    whoami
    
    ```
    
    **Exemplo:**
    
    ```bash
    $ whoami
    usuario
    
    ```
    
    ---
    
    ### 👥 `id`
    
    **Função:** Exibe UID, GID e grupos do usuário.
    
    **Sintaxe:**
    
    ```bash
    id [usuário]
    
    ```
    
    **Exemplos:**
    
    ```bash
    id              # Mostra informações do usuário atual
    id root         # Mostra informações do usuário root
    
    ```
    
    ---
    
    ### 👥 `groups`
    
    **Função:** Lista os grupos de um usuário.
    
    **Sintaxe:**
    
    ```bash
    groups [usuário]
    
    ```
    
    **Exemplo:**
    
    ```bash
    groups usuario
    
    ```
    
    ---
    
    ### 🔑 `chmod`
    
    **Função:** Altera permissões de arquivos/diretórios.
    
    **Sintaxe:**
    
    ```bash
    chmod [opções] modo arquivo
    
    ```
    
    📌 Modos numéricos:
    
    - `r` = leitura (4)
    - `w` = escrita (2)
    - `x` = execução (1)
    
    **Exemplos:**
    
    ```bash
    chmod 644 arquivo.txt   # Dono rw-, grupo r--, outros r--
    chmod 755 script.sh     # Dono rwx, grupo r-x, outros r-x
    chmod u+x script.sh     # Dá permissão de execução ao dono
    
    ```
    
    ---
    
    ### 🔑 `chown`
    
    **Função:** Altera dono e grupo de arquivos/diretórios.
    
    **Sintaxe:**
    
    ```bash
    chown [usuário][:grupo] arquivo
    
    ```
    
    **Exemplos:**
    
    ```bash
    chown maria arquivo.txt        # Dono passa a ser maria
    chown maria:devs projeto/      # Dono = maria, grupo = devs
    
    ```
    
    ---
    
    ### 🔑 `chgrp`
    
    **Função:** Altera apenas o grupo de arquivos/diretórios.
    
    **Sintaxe:**
    
    ```bash
    chgrp [grupo] arquivo
    
    ```
    
    **Exemplo:**
    
    ```bash
    chgrp devs arquivo.txt
    
    ```
    
    ---
    
    ### 👤 `useradd`
    
    **Função:** Cria um novo usuário.
    
    **Sintaxe:**
    
    ```bash
    sudo useradd [opções] usuário
    
    ```
    
    **Exemplos:**
    
    ```bash
    sudo useradd joao -m          # Cria usuário joao com diretório home
    sudo useradd joao -s /bin/bash # Define shell do usuário
    
    ```
    
    ---
    
    ### 👤 `passwd`
    
    **Função:** Define ou altera senha de usuário.
    
    **Sintaxe:**
    
    ```bash
    passwd [usuário]
    
    ```
    
    **Exemplo:**
    
    ```bash
    passwd joao
    
    ```
    
    ---
    
    ### 👤 `usermod`
    
    **Função:** Modifica atributos de usuário.
    
    **Sintaxe:**
    
    ```bash
    sudo usermod [opções] usuário
    
    ```
    
    **Exemplos:**
    
    ```bash
    sudo usermod -aG sudo joao   # Adiciona joao ao grupo sudo
    sudo usermod -s /bin/zsh joao # Altera shell para zsh
    
    ```
    
    ---
    
    ### 👤 `deluser` / `userdel`
    
    **Função:** Remove um usuário.
    
    **Sintaxe:**
    
    ```bash
    sudo deluser usuário
    sudo userdel usuário
    
    ```
    
    **Exemplos:**
    
    ```bash
    sudo deluser joao            # Remove usuário
    sudo userdel -r joao         # Remove usuário e seu diretório home
    
    ```
    
- ## Processos e Monitoramento
    
    ### ⚙️ `ps`
    
    **Função:** Mostra processos em execução.
    
    **Sintaxe:**
    
    ```bash
    ps [opções]
    
    ```
    
    **Exemplos:**
    
    ```bash
    ps                     # Mostra processos do shell atual
    ps -e                  # Lista todos os processos
    ps -ef                 # Lista com informações detalhadas
    ps aux                 # Formato comum: usuário, PID, uso de CPU/memória
    
    ```
    
    ---
    
    ### ⚙️ `top`
    
    **Função:** Mostra processos em tempo real (consumo de CPU/memória).
    
    **Sintaxe:**
    
    ```bash
    top
    
    ```
    
    **Atalhos dentro do `top`:**
    
    - `q` → sair
    - `k` → matar processo (inserindo PID)
    - `h` → ajuda
    
    ---
    
    ### ⚙️ `htop` *(pode precisar instalar)*
    
    **Função:** Versão melhorada do `top`, com interface colorida e navegação interativa.
    
    **Sintaxe:**
    
    ```bash
    htop
    
    ```
    
    ---
    
    ### ⚙️ `jobs`
    
    **Função:** Lista processos em segundo plano do shell atual.
    
    **Sintaxe:**
    
    ```bash
    jobs
    
    ```
    
    **Exemplo:**
    
    ```bash
    jobs
    [1]+  Running   script.sh &
    
    ```
    
    ---
    
    ### ⚙️ `bg`
    
    **Função:** Continua execução de um processo parado em segundo plano.
    
    **Sintaxe:**
    
    ```bash
    bg [número_do_job]
    
    ```
    
    **Exemplo:**
    
    ```bash
    bg %1
    
    ```
    
    ---
    
    ### ⚙️ `fg`
    
    **Função:** Traz processo em segundo plano para o primeiro plano.
    
    **Sintaxe:**
    
    ```bash
    fg [número_do_job]
    
    ```
    
    **Exemplo:**
    
    ```bash
    fg %1
    
    ```
    
    ---
    
    ### ⚙️ `kill`
    
    **Função:** Envia sinais para encerrar processos.
    
    **Sintaxe:**
    
    ```bash
    kill [sinal] PID
    
    ```
    
    **Exemplos:**
    
    ```bash
    kill 1234             # Envia sinal padrão (TERM) para o PID 1234
    kill -9 1234          # Mata processo à força (KILL)
    kill -15 1234         # Termina de forma mais “limpa” (TERM)
    
    ```
    
    ---
    
    ### ⚙️ `killall`
    
    **Função:** Encerra processos pelo nome.
    
    **Sintaxe:**
    
    ```bash
    killall [nome_processo]
    
    ```
    
    **Exemplo:**
    
    ```bash
    killall firefox
    
    ```
    
    ---
    
    ### ⚙️ `uptime`
    
    **Função:** Mostra tempo de atividade do sistema, número de usuários e carga do sistema.
    
    **Sintaxe:**
    
    ```bash
    uptime
    
    ```
    
    **Exemplo:**
    
    ```bash
    $ uptime
    14:32:01 up  2:15,  2 users,  load average: 0.25, 0.32, 0.18
    
    ```
    
    ---
    
    ### ⚙️ `free`
    
    **Função:** Mostra uso de memória RAM e swap.
    
    **Sintaxe:**
    
    ```bash
    free [opções]
    
    ```
    
    **Exemplos:**
    
    ```bash
    free         # Exibe em KB
    free -m      # Exibe em MB
    free -h      # Exibe em formato legível (GB/MB)
    
    ```
    
    ---
    
    ### ⚙️ `uptime`
    
    **Função:** Mostra tempo que o sistema está ligado e carga média.
    
    **Exemplo:**
    
    ```bash
    uptime
    
    ```
    
    ---
    
    ### ⚙️ `dmesg`
    
    **Função:** Mostra mensagens do kernel (logs de inicialização, hardware, etc.).
    
    **Sintaxe:**
    
    ```bash
    dmesg [opções]
    
    ```
    
    **Exemplos:**
    
    ```bash
    dmesg | less         # Visualizar com paginação
    dmesg | grep usb     # Filtrar mensagens relacionadas a USB
    
    ```
    
- ## Arquivos Compactados e Backups
    
    ### 📦 `tar`
    
    **Função:** Cria, extrai e manipula arquivos compactados (tarballs).
    
    **Sintaxe:**
    
    ```bash
    tar [opções] arquivo.tar [arquivos]
    
    ```
    
    **Opções principais:**
    
    - `c` → criar
    - `x` → extrair
    - `v` → modo verboso (mostrar arquivos)
    - `f` → especifica nome do arquivo
    - `z` → compactar/descompactar com gzip
    - `j` → compactar/descompactar com bzip2
    
    **Exemplos:**
    
    ```bash
    tar -cvf backup.tar pasta/        # Cria backup.tar com a pasta
    tar -xvf backup.tar               # Extrai arquivos de backup.tar
    tar -czvf backup.tar.gz pasta/    # Cria backup.tar.gz (com gzip)
    tar -xvzf backup.tar.gz           # Extrai backup.tar.gz
    
    ```
    
    ---
    
    ### 📦 `gzip` e `gunzip`
    
    **Função:** Compacta e descompacta arquivos individuais com gzip.
    
    **Sintaxe:**
    
    ```bash
    gzip [arquivo]
    gunzip [arquivo.gz]
    
    ```
    
    **Exemplos:**
    
    ```bash
    gzip notas.txt          # Gera notas.txt.gz
    gunzip notas.txt.gz     # Restaura notas.txt
    
    ```
    
    ---
    
    ### 📦 `zip` e `unzip`
    
    **Função:** Compacta e descompacta arquivos ZIP.
    
    **Sintaxe:**
    
    ```bash
    zip [arquivo.zip] [arquivos]
    unzip [arquivo.zip]
    
    ```
    
    **Exemplos:**
    
    ```bash
    zip backup.zip a.txt b.txt     # Cria backup.zip com dois arquivos
    zip -r projeto.zip pasta/      # Compacta diretório inteiro
    unzip backup.zip               # Extrai arquivos de backup.zip
    
    ```
    
    ---
    
    ### 📦 `bzip2` e `bunzip2`
    
    **Função:** Compacta e descompacta arquivos com bzip2 (melhor taxa que gzip, mas mais lento).
    
    **Sintaxe:**
    
    ```bash
    bzip2 [arquivo]
    bunzip2 [arquivo.bz2]
    
    ```
    
    **Exemplos:**
    
    ```bash
    bzip2 dados.txt        # Gera dados.txt.bz2
    bunzip2 dados.txt.bz2  # Restaura dados.txt
    
    ```
    
    ---
    
    ### 🔄 `rsync`
    
    **Função:** Sincroniza e copia arquivos/diretórios, útil para backups.
    
    **Sintaxe:**
    
    ```bash
    rsync [opções] origem destino
    
    ```
    
    **Opções principais:**
    
    - `a` → modo arquivo (preserva permissões, links, etc.)
    - `v` → verboso
    - `z` → compressão durante a transferência
    - `-delete` → remove arquivos no destino que não estão na origem
    
    **Exemplos:**
    
    ```bash
    rsync -avz /home/usuario/ /backup/          # Backup local
    rsync -avz /home/usuario/ user@server:/bkp  # Backup remoto via SSH
    rsync -av --delete /home/usuario/ /backup/  # Sincroniza removendo extras
    
    ```
    
    ---
    
    ### 📦 `scp`
    
    **Função:** Copia arquivos entre hosts via SSH.
    
    **Sintaxe:**
    
    ```bash
    scp [opções] origem destino
    
    ```
    
    **Exemplos:**
    
    ```bash
    scp arquivo.txt user@192.168.1.10:/home/user/  # Copia arquivo para servidor
    scp user@192.168.1.10:/home/user/arquivo.txt ./ # Copia do servidor para local
    
    ```
