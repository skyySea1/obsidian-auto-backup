esse projeto usará **Task Scheduler** (Agendador de Tarefas) no Windows, que permite a execução automática de programas ou scripts em horários programados.
tecnologias: git. bash 
FUnção :LiChevronsRightLeft:
- realizar backup a cada três dias no repositório git
- dispopnibilizar um botão para atualização manual

## abra o agendador de tarefas
![[Pasted image 20240908125948.png]]
crie uma tarefa:
![[Pasted image 20240908130323.png]]


vá em ações, "novo", depois em "iniciar programa"
selecione o arquivo que criamos
depois vá em condições, e ative a função para executar apenas quando estiver com uma conexão ativa (internet), afinal você não quer dar push  sem internet e receber um fatal error, não é mesmo?

Em "Disparadores", defina para repetir a cada 3 dias.



código

```bash
cd /d C:\Users\Henrique RIbeiro\Documents\lifework
git add .
git commit -m "atualização automática para %date%
git push origin master
170017
0 0 */3 * * /caminho/para/o/script/obsidian_push.sh

```