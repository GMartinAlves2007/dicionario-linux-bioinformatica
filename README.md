# Dicionario-Linux-Bioinformatica

# NAVEGAÇÃO E ARQUIVOS

## ls
**descrição :** lista os arquivos e pastas que você esta no momento. chamado como comando "olhadinha". inclusive com ele é possivel observar os arquivos que estão escondidos.
**exemplo:** para fazer uma chegagem por exemplo , se o arquivo de uma ressonância magnética acabou de ser salvo em uma pasta de exames.
`ls`
`ls -a` 
`ls -l`

## cd
**descrição:** Abreviação de Change Directory. É o comando que você usa para entrar em uma pasta ou voltar para uma pasta anterior.tendo assim varaições dele que serão citadas , com função de voltar para a "home" , voltar para a pasta anterior , ir para um diretório especifico , etc...
**exemplo:** por exemplo serve para entrar em uma pasta de um paciente para observar seus dados em um eletrocardiograma.
`cd -`
`cd documentos`
`cd`

## pwd
**descrição:** ele servirá para mostrar o caminho para poder encontrar o local da pasta em que você esta no momento ou de alguma outra pasta, pode ser bastante útil pois nem sempre o nome da pasta estará completo na linha de comando.
**exemplo:** para encontrar um arquivo onde você esta analisando proteinas , assim retirando o tão conhecido erro que pode ocorrer "arquivo não encontrado".
`pwd`
`pwd -L`
`pwd -P`

## mkdir
**descrição:** criará novos diretórios , ajuda a organizar seus arquivos de forma com que siga a hierariquia deles, apenas pelo terminal sem precisar usar mouse.
**exemplo:** em uma situação na qual tem uma lista de 40 pacientes para estudar , você utiliza ele para garantir que o nome dos pacientes gerem um padrão de nomes no seu banco de dados.
`mkdir pasta1`
`mkdir nomes estudos pesquisas`
`mkdir "nomes pacientes"`
`mkdir -p /home/usuario/documentos/pacientes`

## rm 
**descrição:** Significa Remove. É utilizado para excluir arquivos. Por padrão, o rm não remove pastas (diretórios) vazias nem move arquivos para a lixeira; a exclusão é permanente e imediata através do terminal.
**exemplo:** ao ser criado muitos arquivos de cache durante uma microtomografia , após gerar a imagem você pode utilizar este comando para deletar estes arquivos temporarios
`rm -f`
`rm -i`
`rm -r`

## cp
**descrição:** significa copy. Como seu próprio nome diz serve para copiar arquivos que estão em uma pasta em outra , um diretório para um novo local 
**exemplo:** você pode utilizar este comando quando for fazer algum teste em um script que ira mudar algum dado importante , então você ira fazer o teste na cópia tendo assim uma segurança se der errado.
`cp -r /pasta_origem /pasta_destino`
`cp -p arquivo.txt arquivo_backup.txt`
`cp -i`

## mv
**descrição:** significa move. além da função principal que é mover o arquivo ou pastas de um diretório , ele também pode ter a função de renomear estes arquivos, sendo assim a forma mais rápida para organizar seus dados sem criar cópias.
**exemplo:** para organizar e renomear nomes de arquivos que são gerados com nomes genéricos em algum laboratório por exemplo, um arquivo chamado daa_0012020.csv , você muda ele para paciente_joao_sangue.csv
`mv antigo.txt novo.txt`
`mv arquivo.txt /caminho/do/diretorio/`
`mv -f arquivo.txt /destino/`

## touch 
**descrição:** é a forma mais rápida de criar um arquivo vazio no Linux , serve para atualizar a data de um arquivo ja criado também , sem fazer alteração no que tem dentro deste arquivo.
**exemplo:** no laboratório , você pode usar este comando para criar um arquivo antes de iniciar uma coleta de dados de um sensor , deixando ja o arquivo pronto para receber anotações e dados.
`touch arquivo.txt`
`touch -a arquivo.txt`
`touch -c --no-create arquivo.txt`

# LEITURA E FILTROS

## cat
**descriação:** esta sigla na verdade é a abreviação de concatenate. ele exibe todo conteudo de um arquivo direto no terminal, é bem útil se quiser ler um texto que está dentro de um arquivo todo de uma vez.
**exemplo:** se precisar no laboratório ver se algum paramêtro esta carregado corretamente, em vez de utilizar qualquer editor pesado de texto , é bem mais prático utilizar este comando.
`cat arquivo.txt`
`cat -n arquivo.txt`
`cat arquivo1.txt arquivo2.txt`

## head
**descrição:** ele exibe as primeiras linhas de um arquivo , funcionando assim para verificar a estrutura de grandes arquivos , porém com este mesmo comando você pode escolher quantas linhas ele irá exibir
**exemplo:** antes de um processamento de um arquivo pesado em um laboratório como um de alinhamento genético , pode utilizar o head para ele ver se o fastq não esta corrompido e se o arquivo esta no formato correto.
`head arquivo.txt`
`head -n 20 arquivo.txt`
`head -n 3 arquivo1.txt arquivo2.txt`

## tail
**descrição:** serve como o oposto do head. se o head exibe as primeiras linhas , o tail exibe as últimas linhas de um arquivo. Serve muito bem para monitorar os arquivos de log que crescem durante a execução do programa.
**exemplo:** em um arquivo pesado de uma tomografia , você pode utilizar ele para ver se nas ultimas linhas apareceu " programa executado com sucesso" ou um erro qualquer.
`tail arquivo.txt`
`tail -n 20 arquivo.txt`
`tail -f /var/log/syslog`

## grep
**descrição:** serve para busca baseada em padrões. ele irá buscar e exibir apenas linhas de um arquivo com uma palavra ou uma sequência específica de caracteres desejado.
**exemplo:** em um arquivo de mapeamento génetico por exemplo , para verificar se existe alguma mutação em algum gene especifico , você pode utilizar o grep para procurar especificadamente sobre o gene.
`grep "palavra" arquivo.txt`
`grep -i "linux" arquivo.txt`
`grep -r "funcao_teste" /home/usuario/projeto/`           

## more
**descrição:** serve para vizualizar textos , permitindo ler arquivos longos dividos em páginas , exibe uma tela por vez e avança ao clicar a barra de espaço.
**exemplo:** para verificar por exemplo, uma lista de compostos e medicamentos na qual você quer parar e analisar cada um para conferir o que deve ser conferido
`more arquivo.txt`
`more +[n] arquivo`
`more -[n] arquivo`

## less
**descrição:** serve para vizualizar arquivos de formas extremamente eficientes. Ele não lê o arquivo inteiro de uma vez , por conta disso permite prosseguir e retroceder em um arquivo de forma rapida
**exemplo:** em um EEG(Eletroencefalograma) que é gerado um arquivo muito extenso , o comando permite o engenheiro navegar pelas ondas cerebrais para indentificar picos de atividade sem travar nada.
`less arquivo.txt`
`less -N arquivo.txt`
`less -S arquivo.txt`

# Sistema e Info

## top
**Descrição:** Programa que mostra processos em execução, tanto programas parados quanto programas ativos, tempo de uso da CPU, memória RAM, etc. Parecido com o Gerenciador de Tarefas do Windows. Para sair do top, pressionar `q`.
**Exemplo:** Para monitorar apenas processos que o seu usuário abriu no servidor, use:
`top -u seu_nome_de_usuario`

## df
**Descrição:** Mostra o espaço livre/ocupado de cada partição do sistema.
**Exemplo:** Para verificar o espaço livre em seu disco antes de armazenar uma sequência de exames:
`df -h`

## du
**Descrição:** Mostra o espaço ocupado por arquivos e diretórios. É como ver as "Propriedades" de uma pasta de experimentos.
**Exemplo:** Para verificar o tamanho total de uma pasta de um paciente:
`du -sh /dados/paciente_01`

## ps
**Descrição:** Mostra o estado dos processos em um momento específico. Útil para ver se uma análise em segundo plano ainda está ativa.
**Exemplo:** Para ver todos os programas rodando no servidor com detalhes:
`ps aux`

## free
**Descrição:** Mostra detalhes sobre a utilização da memória RAM do sistema.
**Exemplo:** Para verificar se o computador aguenta rodar mais uma tarefa pesada sem travar:
`free -h`

## uptime
**Descrição:** Mostra há quanto tempo o computador está ligado e a carga de trabalho.
**Exemplo:** Para saber se o servidor não reiniciou durante o processamento de dados que ficou rodando ontem:
`uptime`

# REDES E DOWNLOAD

## ping
**Descrição:** Envia um sinal para verificar a conexão com outro IP ou equipamento.
**Exemplo:** Para testar a conexão com o computador que armazena os exames:
`ping 192.168.1.10`

## wget
**Descrição:** Ferramenta de download direto pelo terminal para baixar pacotes de dados da web.
**Exemplo:** Para baixar uma lista de proteínas disponibilizada em um site:
`wget https://link-do-site.com/arquivo.zip`

## curl
**Descrição:** Permite a comunicação com servidores e consultas de APIs de saúde ou equipamentos.
**Exemplo:** Para ler o status de um equipamento do laboratório via servidor:
`curl http://servidor-do-laboratorio.com/status-equipamento`

## ssh
**Descrição:** Faz a conexão segura para acessar o terminal de outro computador remotamente.
**Exemplo:** Para acessar o servidor potente do laboratório a partir do seu notebook:
`ssh seu_usuario@192.168.0.1`

## ifconfig
**Descrição:** Exibe informações de rede do dispositivo, como o endereço IP.
**Exemplo:** Para descobrir o IP da sua máquina para configurar um software de monitoramento:
`ifconfig`

# COMPACTAÇÃO E EDIÇÃO

## tar
**Descrição:** Útil para agrupar vários arquivos e pastas de sequenciamento em um único arquivo.
**Exemplo:** Para organizar arquivos pequenos em um pacote:
`tar -cvf sequenciamento.tar pasta_de_arquivos/`

## gzip
**Descrição:** Compressor que reduz o tamanho do arquivo para economizar espaço no disco.
**Exemplo:** Para comprimir um arquivo de resultados de exames pesado:
`gzip resultados_exames.txt`

## zip
**Descrição:** Compactador de arquivos e pastas para facilitar o compartilhamento com usuários de Windows.
**Exemplo:** Para juntar exames de diferentes pacientes em um único arquivo compactado:
`zip -r exames_2026.zip pasta_dos_exames/`

## nano
**Descrição:** Editor de texto simples que funciona diretamente dentro do terminal.
**Exemplo:** Para editar informações rápidas dentro de um arquivo de texto:
`nano arquivo_exame_gabriel.txt`

## chmod
**Define as permissões de quem pode ler, gravar ou executar arquivos e pastas.** 
**Exemplo:** Para dar permissão de execução a um script de análise que você criou:
`chmod +x meu_script.sh`
