# DevOps  
Repositório dedicado ao estudo sobre como trabalhar com o servidor Linux, construir scripts no shell, gerenciar e automatizar tarefas em um fluxo e monitorar recursos e agendamento de tarefas.

## Mundo DevOps  
> - Time de Dev: construção da aplicação.
> - DevOps: integra desenvolvimento e operações.
> - DevOps surge como uma cultura para integrar essas duas equipes que ficará responsaveis pela criação, manutenção, desempenho, segurança e eficiência da solução para os usuários.
>   
>  Abordagem de algumas práticas:
> - Melhoria da qualidade do software;
> - Automatização;
> - Monitoramento;
> - Realização de testes,
> - Modo contínuo.

> ### Virtual machine
> - É um software que emula o funcionamento de um sistema operacional sob um outro sistema operacional.
> - Alguns computadores podem apresentar certa lentidão e até mesmo bugs quando usamos máquinas virtuais (VMs) através de softwares de virtualização como o VirtualBox.
>   
> ### Alternativa:
> - Windows Subsystem for linux (WSL)
>  - O WSL é um recurso do Windows 10 e 11 que permite executar um ambiente linux diretamente no Windows, sem a necessidade de uma VM. Com o WSL, você pode instalar distribuições Linux (como Ubuntu, Debian, e outras) e utilizá-las como se fossem aplicativos nativos do Windows.
> - Abra o PowerShell como administrador e execute o comando wsl --install
>
> ### Distribuições do Linux
> - Linux é o núcleo (kernel) de diversas distribuições de sistemas operacionais de código aberto e uso livre.
> - Um sistema operacional é formado por um conjunto de diferentes programas estruturados em blocos funcionais (utilitários, drivers, ferramentas de gerenciamento, aplicativos, bibliotecas etc.) que operam de modo integrado no gerenciamento de um hardware.
>
## Acesso via SSH
> - O protocolo Secure Shell (SSH) é um método para enviar comandos com segurança a um computador em uma rede não segura. O SSH usa criptografia para autenticar e criptografar conexões entre dispositivos. O SSH também permite o tunelamento, ou encaminhamento de porta, que é quando os pacotes conseguem atravessar redes que, de outra forma, não seriam capazes de atravessar. O SSH é frequentemente usado para controlar servidores remotamente, para gerenciar a infraestrutura e para transferir arquivos.
>   
> ### O que o SSH faz?
> - Conexões criptografadas remotas: o SSH estabelece uma conexão entre o dispositivo de um usuário e uma máquina distante, geralmente um servidor. Ele usa criptografia para embaralhar os dados que atravessam a conexão.
>   
> - A capacidade fazer tunelamento: em rede, o tunelamento é um método para mover pacotes em uma rede usando um protocolo ou caminho que normalmente não seria possível usar. O tunelamento funciona envolvendo o pacote* com informações adicionais, chamadas de cabeçalhos, para alterar seu destino. Os túneis SSH usam uma técnica chamada encaminhamento de porta para enviar pacotes de uma máquina para outra.
>
> ### Como funciona o SSH?
> - O SSH é executado sobre o conjunto de protocolos TCP/IP, do qual grande parte da internet depende.TCP significa protocolo de controle de transmissão e IP significa protocolo de internet . O TCP/IP combina esses dois protocolos para formatar, rotear e entregar pacotes. O IP indica, entre outras informações, para qual endereço de IP um pacote deve ir (pense em um endereço de correspondência), enquanto o TCP indica para qual porta um pacote deve ir em cada endereço de IP.
>   
> - O TCP é um protocolo de camada de transporte: ele se preocupa com o transporte e a entrega de pacotes. Normalmente, protocolos adicionais são usados sobre o TCP/IP para colocar os dados transmitidos em um formato que o aplicativo possa usar. O SSH é um desses protocolos. (Outros exemplos incluem HTTP, FTP e SMTP).
>
> ### Para que o SSH é usado?
> Tecnicamente, o SSH pode transmitir qualquer dado arbitrário por uma rede, e o tunelamento SSH pode ser configurado para uma infinidade de propósitos. No entanto, os casos de uso mais comuns do SSH são:
> - Gerenciamento remoto de servidores, infraestrutura e computadores de funcionários.
> - Transferência segura de arquivos (o SSH é mais seguro do que os protocolos não criptografados como o FTP).
> - Acesso a serviços em nuvem sem expor as portas de uma máquina local à internet.
> - Conexão remota a serviços em uma rede privada.
> - Ignorar as restrições do firewall.
>
> ### Qual porta o SSH usa?
> - A porta 22 é a porta padrão para SSH. Às vezes, os firewalls podem bloquear o acesso a determinadas portas em servidores atrás do firewall, mas deixam a porta 22 aberta. Portanto, o SSH é útil para acessar servidores do outro lado do firewall: o pacote direcionado à porta 22 não é bloqueado e pode ser encaminhado para qualquer outra porta.
>
> ### Há algum risco de segurança associado ao SSH?
> - Qualquer protocolo pode ser abusado por partes maliciosas e a natureza criptografada além dos recursos de tunelamento do SSH o tornam particularmente atraente para invasores. O SSH tem sido usado em vários ataques documentados para extrair dados privados, abrir rotas de backdoor em uma rede segura e até mesmo obter acesso ao root em servidores.
>   
> - Certos tipos de ataques também podem roubar chaves SSH para acessar computadores e servidores privados. De fato, o gerenciamento de chaves SSH é um grande problema de segurança para grandes organizações, pois seus muitos servidores podem usar milhares ou até milhões de chaves, e o monitoramento e a atualização dessas chaves são praticamente impossíveis. Quando um invasor obtém uma chave, ele pode ter acesso permanente por meses ou anos.
>
> ### Qual é a diferença entre o SSH e outros protocolos para tunelamento?
> - Uma das principais diferenças entre o SSH e outros protocolos de tunelamento é a camada OSI em que eles operam. GRE, IP-in-IP e IPsec são todos protocolos da camada de rede. Dessa forma, eles não estão cientes das portas (um conceito da camada de transporte) e, em vez disso, operam entre endereços de IP. (A camada OSI exata do SSH não é estritamente definida, mas a maioria das fontes a descreve como um protocolo da camada 7/camada de aplicação).
>
> - Outra diferença é o uso do TCP pelo SSH. O TCP, conforme descrito acima, é um protocolo de camada de transporte e um dos principais usados na internet. Outro protocolo de camada de transporte amplamente usado é o UDP, o User Datagram Protocol. O UDP é um protocolo de transporte de "melhor esforço", enviar pacotes sem garantir sua entrega, o que o torna mais rápido, mas às vezes resulta em perda de pacotes. Embora o TCP seja mais lento que o UDP, ele garante a entrega de todos os pacotes em ordem e, portanto, é mais confiável.
>
> *** A escalabilidade de recursos é uma característica essencial para um servidor que precisa lidar com grandes volumes de dados. Ela permite que o sistema utilize mais recursos em função do aumento na demanda, garantindo um desempenho consistente.
>
> ### * Alguns comandos:
> - ```ls```  lista dos arquivos e diretórios existentes dentro de um diretório.
> - ```ls -a```  exibe nos resultados da listagem os arquivos e pastas ocultas existentes dentro do diretório.
> - ```pwd```  retorna o caminho completo do diretório em que você se encontra.
> - ```cd```  caminho que você deseja percorrer.
> - ```ls -l```  para obter uma listagem mais detalhada, incluindo permissões, proprietário, tamanho e data de modificação dos arquivos.
> - ```clear``` limpa o terminal.
> - ```ls --help```
> - ```cat``` abre o arquivo que você deseja.
> - ```rm``` seguido do nome de um arquivo remove este.
> - ```rmdir``` seguido do nome apaga diretório, se este diretório estiver vazio.
> - ```top``` mostra os processos em execução ordenados pelo uso de CPU (Ctrl + C para sair).
> - ```ps``` mostra os processos com o numero PID.
> - ```shutdown``` desliga o computador.
> - ```mkdir``` Cria nova pasta, diretório.
> - ```history``` visualizar a lista de comandos que foi executada.
> - ```ls -la``` lista rquivos ocultos de forma detalhada.
> - ```whatis``` verifica a descrição simples de um comando.
> - ```vi``` é o edito básico em grande parte das distribuições.
> - ```tar``` agrupa vários arquivos em apenas um.
>
> 
## Shell
> ### O que é o Shell?
> - é a interface de acesso ao sistema operacional, onde é possível interagir com o sistema por meio de comandos digitados do teclado. Ele pode ser acessado pelo modo gráfico e diretamente em modo texto.
>   
> ```angelica@oliveira:~-$```
> - ubuntu é o nome do usuário.
> - @servidor é o nome do host.
> - ~ é a abreviação para a pasta do usuário.
> - $ indica que o usuário não possui poderes administrativos.
>
>   
## Shell Script
> - É um programa não compilado que é enviado para um processador. Em seguida, um interpretador lê seu código e o traduz, de modo que o processo entende suas instruções que serão executadas em seguida.
>   
> - Shell Script é a linguagem de programação utilizada pelo shell no caso o shell é o nosso interpretador que vai ler os nossos programase dizer ao processadoro que fazer.
>   
> - Programas em shell scripts são escritos para tarefas administrativas e repetitivasno Linux.
> 
>
## Explorando o Linux Server
> ### Gerenciando arquivos
>  ```touch```
> 
> Criando um arquivo:
> 
> ![image](https://github.com/user-attachments/assets/1bf508ce-9c53-4d23-b373-bb70551607ef)
>
> Inserindo conteúdo:
> 
> (Quando terminar de escrever o conteúdo e só aperta Ctrl + D).
> 
> ![image](https://github.com/user-attachments/assets/ff31658a-8679-4fd8-bacb-576324e623b2)
>
> Para visualizar o conteúdo é só digital ```cat notas.txt```
> 
> O comando ```echo``` também manda uma mensagem para o arquivo e seria assim: ```echo hello world > notas.txt```
>
> Aqui foi utilizado o comando ```tar``` para compactar um arquivo, depois coloquei ele no diretório que eu escolhi e por fim, o removi usando o camando ```rm```
> 
> ![image](https://github.com/user-attachments/assets/66bb8200-b951-425b-bb6b-4b15b64ff115)
>
> * O operador >> é usado para adicionar (anexar) texto ao final de um arquivo existente ```echo "Bem-vindo ao Linux!" >> saudacao.txt```
> 
> ### Criando diretórios
> - ```mkdir -p``` é usado para criar diretórios aninhados.
> 
> - ```mv``` para mover arquivos.
>  
> - ```ls arc*``` lista arquivos iniciados por arc com qualquer sequência de caracteres adicionais, inclusive nada. Sendoa ssim, você conseguirá listar todos os arquivos que precisar analisar.
>
> PRÁTICA
> - Crie dois diretórios chamados dir e dir 2 na mesma posição hierárquica:
>   
> ```mkdir dir1 dir2```
>
> - Entre no diretório dir e crie dois arquivos chamados data1 e data2:
>   
> ```cd dir```
> ```touch data1 data2```
>
> - Copie somente o conteúdo de dir1 para dir2:
>
> ```cp -r dir1/* dir2```
>
> - Crie um novo diretório chamado dir3 e mova o conteúdo de dir1 e dir2 para dir3:
>
> ```mkdir dir3```
> ```mv dir1/* dir3```
>
> 
>  ## Shell scripting
> ### Construindo scripts no shell
> - A compreensão de práticas de scripting no shell possibilita que sejamos capazes de criar fluxos de trabalho otimizados, implementando práticas de integração e entrega contínuas. Além disso, essa abordagem facilita a configuração e gerenciamento da infraestrutura como código. Dessa forma, o aprofundamento dos estudos em Shell Scripting é um passo crucial no desenvolvimento como pessoa profissional em DevOps.
> 
> PRÁTICA
> - Elabore um script simples que exiba uma mensagem de boas-vindas quando executado:
> 
> ```echo "Bem-vindo ao meu script!"```
>
> - Crie um script que solicite ao usuário o nome de um diretório e, em seguida, o crie:
> 
> ![image](https://github.com/user-attachments/assets/07284fbb-00d9-470b-812a-2857ec4c40d7)
>
>
> ### Automatizando tarefas
> - O editor ```nano``` é mais uma alternativa para edição de textos no terminal, e está disponível em quase todas as distribuições linux, assim como o ```vim```.
> 
>
> ## Monitoramento e agendamento
> 
> ### Processando textos para coleta de dados
>
> - O comando ```grep``` é um importante aliado que atua na busca de dados em arquivos ou fluxos de entrada do código (dados digitados por um usuário no teclado, por exemplo). Esse comando nos permite especificar palavras ou padrões para pesquisa.
> ```grep - -help```
>
> ```cat novo.txt | grep "padrão"```
>
> - Crie um script que utiliza comandos como ps e grep para monitorar os processos que estão utilizando uma porcentagem significativa da CPU:
>
> ```#!/bin/bash```
> 
> ```echo "Top 5 processos por uso de CPU:"```
>
> ```ps aux --sort=-%cpu | head -n 6```
>
> - Desenvolva um script que utiliza comandos como ps e sort para exibir os processos que estão consumindo mais memória:
> 
> ```#!/bin/bash```
> 
> ```echo "Top 5 processos por uso de memória:"```
>
> ```ps aux --sort=-%mem | head -n 6```
>
> 
 




