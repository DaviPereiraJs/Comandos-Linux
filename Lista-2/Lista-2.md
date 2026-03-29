# Lista de Exercícios - Usuários, Grupos e Permissões
**Prof. Renato William**
**Davi Nascimento Pereira**

**1. Cadastre os usuários alice, bob, carlos, daniel e erica.**
```
sudo useradd alice
sudo useradd bob
sudo useradd carlos
sudo useradd daniel
sudo useradd erica
2. Crie no seu diretório home os diretórios producao, rh, financeiro e ti.


mkdir ~/producao ~/rh ~/financeiro ~/ti
3. Cadastre os grupos funcionarios, gerentes e informatica.


sudo groupadd funcionarios
sudo groupadd gerentes
sudo groupadd informatica
4. Colocar os usuários dentro do grupo conforme abaixo:

funcionarios: alice, daniel, erica.

gerentes: bob, carlos

informatica: carlos, alice.


sudo usermod -aG funcionarios alice
sudo usermod -aG funcionarios daniel
sudo usermod -aG funcionarios erica
sudo usermod -aG gerentes bob
sudo usermod -aG gerentes carlos
sudo usermod -aG informatica carlos
sudo usermod -aG informatica alice
5. Alterar o usuário dono dos diretórios conforme abaixo:

producao usuário dono bob e grupo funcionarios.

rh usuário dono erica e grupo gerentes.

financeiro usuário dono bob grupo gerentes.

ti usuário dono carlos grupo informatica.

sudo chown bob:funcionarios ~/producao
sudo chown erica:gerentes ~/rh
sudo chown bob:gerentes ~/financeiro
sudo chown carlos:informatica ~/ti
6. Altere as permissões dos diretórios conforme abaixo:

producao: Usuário e outros somente leitura. Grupo leitura, escrita e execução.

Modo Octal: sudo chmod 474 ~/producao

Modo Literal: sudo chmod u=r,g=rwx,o=r ~/producao

rh: Usuário e outros sem permissão. Grupo leitura, escrita e execução.

Modo Octal: sudo chmod 070 ~/rh

Modo Literal: sudo chmod u=,g=rwx,o= ~/rh

financeiro: Usuário somente leitura, grupo escrita e execução e outros nenhuma.

Modo Octal: sudo chmod 430 ~/financeiro

Modo Literal: sudo chmod u=r,g=wx,o= ~/financeiro

ti: Usuário leitura, escrita e execução, grupo leitura e outros nenhuma.

Modo Octal: sudo chmod 740 ~/ti

Modo Literal: sudo chmod u=rwx,g=r,o= ~/ti

7. Supondo os detalhes dos arquivos pertencentes a um determinado diretório, analise a figura 1 e responda o que se pede:

a) Quais os nomes dos diretórios contidos nessa relação? Qual o nome do arquivos contidos nesta relação?

Diretórios: pgms, teste1, teste2 e Faturamento.

Arquivos: Controle, mbox, exemplo e Linux.

b) Existe algum usuário do mesmo grupo de Rui? Caso positivo, qual?
Sim. O usuário Rui pertence ao grupo Contab. Os usuários Pedro e Tiago também pertencem a este mesmo grupo.

c) Qual o tamanho do arquivo Controle?
O arquivo Controle possui 1565 bytes.

d) Quais as permissões de acesso que os usuários do mesmo grupo de João possuem para acessar o arquivo Controle?
O usuário João e o arquivo Controle pertencem ao grupo Financ. As permissões do grupo para este arquivo são rw-, ou seja, permissão de leitura e escrita (gravação).

e) Eu sou do grupo do usuário Pedro, que permissões tenho com relação ao arquivo exemplo?
O usuário Pedro e o arquivo exemplo pertencem ao grupo Contab. As permissões do grupo são r-x, ou seja, permissão de leitura e execução.

f) Diga o comando completo para permitir que os usuários do mesmo grupo de Rui possam ler e gravar, mas não possam executar o arquivo Linux.
O arquivo Linux atualmente possui a permissão -rwxr--r--. Para alterar a permissão do grupo (que é Contab, o mesmo de Rui) para ler e gravar (rw-), o comando é:


chmod g=rw Linux
g) Qual o código octal para a permissão de acesso do arquivo exemplo.
O arquivo exemplo possui as permissões -rwxr-xr-x. Em octal, isso corresponde a 755 (rwx=7, r-x=5, r-x=5).

h) Qual o código literal para a permissão de acesso do arquivo exemplo.
O código literal correspondente a -rwxr-xr-x é u=rwx,g=rx,o=rx.

i) Altere o dono do arquivo Linux para Rui.


sudo chown Rui Linux
j) Altere o grupo do arquivo Linux para Staff.


sudo chgrp staff Linux