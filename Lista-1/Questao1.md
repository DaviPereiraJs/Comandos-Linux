## 1 (Souza. R.W.R, 2021) Execute os comandos solicitados em cada item:
**Davi Nascimento Pereira**

### (a) COMANDOS PARA REINICIALIZAR OU DESLIGAR O COMPUTADOR

**i) Execute dois comandos para reinicializar o computador de forma imediata.**
Existem várias formas de fazer isso no Linux. Duas das mais comuns e diretas são:
`sudo reboot`
ou
`sudo shutdown -r now`

*Comprovante:*
![Print reinicializando](./prints/substitua_pelo_nome_da_sua_imagem.png)

**ii) Agende o desligamento do seu PC em uma hora específica.**
Para agendar o desligamento para um horário exato (por exemplo, às 22:30), utilizamos o comando `shutdown` com o horário no formato HH:MM:
`sudo shutdown -h 22:30`

*Comprovante:*
![Print agendando desligamento](./prints/substitua_pelo_nome_da_sua_imagem.png)

**iii) Desligue seu PC depois de alguns minutos ou horas.**
Para desligar o sistema após um período de tempo (por exemplo, daqui a 60 minutos), usamos o sinal `+` seguido da quantidade de minutos:
`sudo shutdown -h +60`

*Comprovante:*
![Print desligando com timer](./prints/substitua_pelo_nome_da_sua_imagem.png)

**iv) Desligue seu PC em um prazo de cinco minutos e informe através de uma mensagem a todos os usuários do sistema.**
Podemos adicionar uma mensagem de aviso no próprio comando `shutdown`, que será enviada para o terminal de todos os usuários logados:
`sudo shutdown -h +5 "Atenção: O sistema será desligado em 5 minutos para manutenção. Salvem seus trabalhos!"`

*Comprovante:*
![Print desligando com mensagem](./prints/substitua_pelo_nome_da_sua_imagem.png)


### (b) COMANDOS DE NAVEGAÇÃO

**i) Exiba o diretório corrente.**
Para saber em qual diretório você está trabalhando no momento (Print Working Directory):
`pwd`

*Comprovante:*
![Print diretório corrente](./prints/substitua_pelo_nome_da_sua_imagem.png)

**ii) Exiba o conteúdo do diretório do usuário corrente.**
Para listar o conteúdo do diretório *home* do usuário atual (representado pelo `~`):
`ls ~` 
*(Nota: se você já estiver no diretório do usuário, apenas `ls` também funciona).*

*Comprovante:*
![Print ls home](./prints/substitua_pelo_nome_da_sua_imagem.png)

**iii) Exiba o Conteúdo do diretório corrente com uma listagem completa incluindo os arquivos ocultos.**
O parâmetro `-a` (all) mostra os arquivos ocultos (que começam com ponto), e o `-l` (long) exibe em formato de lista detalhada:
`ls -la`

*Comprovante:*
![Print ls la](./prints/substitua_pelo_nome_da_sua_imagem.png)

**iv) Exiba a árvore de diretórios do /etc/network.**
O comando `tree` exibe a hierarquia de forma gráfica no terminal (pode ser necessário instalar o pacote `tree` caso não venha por padrão na distribuição):
`tree /etc/network`

*Comprovante:*
![Print tree network](./prints/substitua_pelo_nome_da_sua_imagem.png)

**v) Exiba uma lista completa e recursiva do diretório /etc/network.**
O parâmetro `-R` (recursive) faz com que o comando entre em todos os subdiretórios, e o `-l` exibe a lista completa:
`ls -lR /etc/network`

*Comprovante:*
![Print ls lR network](./prints/substitua_pelo_nome_da_sua_imagem.png)

**vi) Listagem longa do diretório home, com detalhes. O que significa cada coluna da listagem?**
Comando: `ls -l ~`
Significado de cada coluna (da esquerda para a direita):
1. **Permissões e Tipo:** O primeiro caractere indica o tipo (ex: `d` para diretório, `-` para arquivo) e os 9 seguintes indicam as permissões de leitura (r), gravação (w) e execução (x) para o dono, grupo e outros.
2. **Links:** Número de *hard links* que apontam para o arquivo/diretório.
3. **Dono:** Nome do usuário dono do arquivo.
4. **Grupo:** Nome do grupo ao qual o arquivo pertence.
5. **Tamanho:** Tamanho do arquivo em bytes.
6. **Data/Hora:** Mês, dia e hora da última modificação.
7. **Nome:** O nome do arquivo ou diretório.

*Comprovante:*
![Print ls l home](./prints/substitua_pelo_nome_da_sua_imagem.png)

**vii) Listagem longa de "/etc", ordenada alfabeticamente.**
Por padrão, o `ls` já ordena de forma alfabética. Para a listagem longa, basta usar:
`ls -l /etc`

*Comprovante:*
![Print ls l etc](./prints/substitua_pelo_nome_da_sua_imagem.png)

**viii) Listagem curta de "/usr", recursiva e ordenada por tamanho.**
O parâmetro `-R` faz a listagem recursiva e o `-S` ordena do maior para o menor tamanho. Como é uma listagem "curta", não usamos o `-l`:
`ls -RS /usr`

*Comprovante:*
![Print ls RS usr](./prints/substitua_pelo_nome_da_sua_imagem.png)

**ix) Suba um nível no diretório corrente.**
Os dois pontos (`..`) representam o diretório pai:
`cd ..`

*Comprovante:*
![Print cd pai](./prints/substitua_pelo_nome_da_sua_imagem.png)

**x) Retorne ao diretório do usuário.**
Você pode usar o atalho do til (`~`) ou simplesmente digitar `cd` sem argumentos:
`cd ~`

*Comprovante:*
![Print cd home](./prints/substitua_pelo_nome_da_sua_imagem.png)

**xi) Mude para o diretório raiz.**
A barra (`/`) representa o topo da hierarquia do sistema de arquivos do Linux:
`cd /`

*Comprovante:*
![Print cd raiz](./prints/substitua_pelo_nome_da_sua_imagem.png)

**xii) Retorne de forma imediata ao diretório anterior.**
O traço (`-`) faz você voltar para o último diretório em que estava antes da mudança atual:
`cd -`

*Comprovante:*
![Print cd volta](./prints/substitua_pelo_nome_da_sua_imagem.png)


### (c) COMANDOS PARA LOCALIZAÇÃO DE ARQUIVOS

**i) Utilize o find para localizar um ou vários arquivos como o nome interfaces em /etc.**
O comando `find` faz uma busca em tempo real. Especificamos o diretório de origem (`/etc`) e o parâmetro `-name` para buscar exatamente o nome do arquivo:
`find /etc -name "interfaces"`

*Comprovante:*
![Print find interfaces](./prints/substitua_pelo_nome_da_sua_imagem.png)

**ii) Use o comando find para encontrar todos os links simbólicos presentes em /usr.**
Para buscar por tipos específicos de arquivos com o `find`, usamos o parâmetro `-type`. A letra `l` (minúscula) representa *link simbólico*:
`find /usr -type l`

*Comprovante:*
![Print find links]

**iii) Repita o item anterior utilizando o comando locate.**
*Observação importante:* Diferente do `find`, o comando `locate` faz consultas de forma extremamente rápida em um banco de dados pré-construído (atualizado pelo `updatedb`), mas **não possui** uma opção nativa para filtrar a busca por tipo de arquivo (como links simbólicos). 

Para responder à questão, precisamos usar o `locate` em conjunto com outros comandos através de um *pipe* (`|`):
`locate "/usr/*" | xargs ls -ld 2>/dev/null | grep "^l"`
*(Explicação: O `locate` encontra todos os caminhos dentro de `/usr`, o `xargs ls -ld` lista os detalhes de cada um deles, e o `grep "^l"` filtra apenas as linhas que começam com a letra 'l', que é o identificador de links simbólicos).*



### (d) COMANDOS DE MANIPULAÇÃO DE ARQUIVOS E DIRETÓRIOS

**i e ii) De acordo com a figura 1, criar a seguinte estrutura de diretórios dentro do /home/seuusuario. OBS: Tente criar mais de um diretório com um único comando.**
`mkdir -p ~/diretorio01/diretorio01_{1,2} ~/diretorio02/diretorio02_1 ~/diretorio02/diretorio02_2/diretorio02_{21,22,23}`

*Comprovante:*
![Print da criação dos diretórios](./prints/

---

**iii e iv) Criar um arquivo chamado numeros.txt e inserir os números solicitados.**
`echo -e "10\n100\n50\n34\n25\n1\n2\n56" > numeros.txt`

*Comprovante:*

---

**v e vi) Criar um arquivo chamado disciplinas.txt e inserir os nomes.**
```bash
cat << EOF > disciplinas.txt
Gerência de Redes
Laboratório de Desenvolvimento de Sistemas
Lógica de Programação
Sistemas Operacionais
Governança de Tecnologia da Informação
Redes de Computadores
EOF

** vii) Criar um arquivo chamado Lista Disciplinas.txt.
seq 1 6 > "Lista Disciplinas.txt"**

Comprovante:

viii) Duplicar o arquivo numeros.txt para numeros1.1.txt, numeros2.1.txt e numeros2.2.1.txt.
cp numeros.txt numeros1.1.txt && cp numeros.txt numeros2.1.txt && cp numeros.txt numeros2.2.1.txt

Comprovante:

ix) Duplicar o arquivo numeros.txt para numeros1.1.num, numeros2.1.num e numeros2.2.1.num.
cp numeros.txt numeros1.1.num && cp numeros.txt numeros2.1.num && cp numeros.txt numeros2.2.1.num

Comprovante:

x) Duplicar o arquivos disciplinas.txt para disciplinas1.txt, disciplinas2.txt e disciplinas2.2.3.txt.
cp disciplinas.txt disciplinas1.txt && cp disciplinas.txt disciplinas2.txt && cp disciplinas.txt disciplinas2.2.3.txt

Comprovante:

xi) Mova os arquivos .num para os respectivos diretórios criados.

Bash
mv numeros1.1.num ~/diretorio01/diretorio01_1/
mv numeros2.1.num ~/diretorio02/diretorio02_1/
mv numeros2.2.1.num ~/diretorio02/diretorio02_2/diretorio02_21/
Comprovante:

xii) Mova os arquivos .txt copiados de numeros para os respectivos diretórios.

Bash
mv numeros1.1.txt ~/diretorio01/diretorio01_1/
mv numeros2.1.txt ~/diretorio02/diretorio02_1/
mv numeros2.2.1.txt ~/diretorio02/diretorio02_2/diretorio02_21/
Comprovante:

xiii) Mova os arquivos disciplinas copiados para os respectivos diretórios.

Bash
mv disciplinas1.txt ~/diretorio01/diretorio01_1/
mv disciplinas2.txt ~/diretorio02/diretorio02_1/
mv disciplinas2.2.3.txt ~/diretorio02/diretorio02_2/diretorio02_23/
Comprovante:

xiv) Faça uma cópia de todos os diretórios e arquivos do diretório /etc/network para o diretorio01.
cp -r /etc/network ~/diretorio01/

Comprovante:

xv) Faça a renomeação do arquivo numeros.txt para numeros Atualizados.txt.
mv numeros.txt "numeros Atualizados.txt"

Comprovante:

xvi) Execute o seguinte comando ping -c10 ww.google.com.br > request.txt.
ping -c10 www.google.com.br > request.txt

Comprovante:

xvii) Utilizando o comando rmdir tente remover o diretório1.2 e o diretório2.1, apresente o resultado.
rmdir ~/diretorio01/diretorio01_2 ~/diretorio02/diretorio02_1

Resultado obtido e Comprovante:
O diretório diretorio01_2 foi apagado sem erros pois estava vazio. O terminal apresentou um erro para o diretorio02_1 avisando que não está vazio (Directory not empty), pois arquivos foram movidos para ele anteriormente.

xviii) Remova todos os arquivos que terminem com num, faça isso de forma recursiva e exibindo o nome de cada arquivo antes de elimina-lo.
find ~ -name "*.num" -exec rm -v {} \;

## 2 (Souza. R.W.R, 2021) Nas distribuições Linux, as principais bibliotecas de sistema e os arquivos de configuração e scripts de inicialização ficam armazenados em quais diretórios?

* **Bibliotecas de sistema:** Ficam armazenadas principalmente no diretório `/lib` (e em algumas distribuições também em `/lib32`, `/lib64` e `/usr/lib`). Elas contêm as bibliotecas compartilhadas necessárias para o boot do sistema e para a execução dos comandos no diretório `/bin` e `/sbin`.
* **Arquivos de configuração e scripts de inicialização:** Ficam armazenados no diretório `/etc`. Esse é o diretório central onde ficam os arquivos que controlam o comportamento dos programas e os scripts que iniciam os serviços do sistema durante o boot.

---

## 3 (Souza. R.W.R, 2021) Descreva o que é o ping e em que casos ele é utilizado?

O **ping** é uma ferramenta de diagnóstico de redes que utiliza o protocolo ICMP (Internet Control Message Protocol) enviando pacotes de solicitação (Echo Request) para um endereço de destino e aguardando uma resposta (Echo Reply).

**Casos de uso:**
* Testar a conectividade básica entre dois dispositivos na rede (saber se o outro computador/servidor está ligado e acessível).
* Verificar se há perda de pacotes durante a transmissão.
* Medir a latência da rede (o tempo que o pacote leva para ir até o destino e voltar, geralmente medido em milissegundos).
* Auxiliar na resolução de problemas de DNS (quando tentamos pingar um nome de domínio como `google.com` e vemos se ele é resolvido para um IP).

---

## 4 (Souza. R.W.R, 2021) Divisão de Sub-redes (192.168.100.0/24)

Para dividir a rede Classe C `192.168.100.0/24` em duas sub-redes iguais, precisamos pegar 1 bit emprestado da porção de hosts. Isso altera a máscara de `/24` para **`/25`** (ou `255.255.255.128` em formato decimal).

A divisão das duas sub-redes fica assim:
* **Sub-rede 1:** `192.168.100.0/25` (IPs válidos do `.1` ao `.126`)
* **Sub-rede 2:** `192.168.100.128/25` (IPs válidos do `.129` ao `.254`)

### Definição dos Endereços IP:

**Para os Computadores (Utilizando a Sub-rede 1):**
* **Computador 1:**
    * IP: `192.168.100.2`
    * Máscara: `255.255.255.128`
* **Computador 2:**
    * IP: `192.168.100.3`
    * Máscara: `255.255.255.128`
* **Computador 3:**
    * IP: `192.168.100.4`
    * Máscara: `255.255.255.128`

**Para o Telefone IP (Utilizando a Sub-rede 2):**
* **Telefone IP:**
    * IP: `192.168.100.130`
    * Máscara: `255.255.255.128`

**Para o Servidor:**
*Regra de Redes:* Como os computadores e o telefone estão em sub-redes diferentes, eles não se comunicam diretamente. Para que o Servidor consiga se comunicar com todos, ele precisa atuar como um Gateway/Roteador. Portanto, ele precisará ter um endereço IP em cada uma das sub-redes (geralmente usamos o primeiro IP válido de cada rede para isso, configurando interfaces virtuais ou duas placas de rede físicas).
* **IP do Servidor na Sub-rede 1 (Gateway dos PCs):** `192.168.100.1` (Máscara: `255.255.255.128`)
* **IP do Servidor na Sub-rede 2 (Gateway do Telefone):** `192.168.100.129` (Máscara: `255.255.255.128`)