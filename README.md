Aqui está a documentação aprimorada para o seu projeto:

---

# Automação de Backup com Task Scheduler ( Windows)

Este projeto usa o **Task Scheduler** (Agendador de Tarefas) no Windows para automatizar a execução de backups periódicos da sua Obsidian Vault ou diretório de trabalho para um repositório Git. Com esta configuração, será possível realizar backups automáticos a cada três dias, além de ter um botão manual para atualizações instantâneas.

## Tecnologias Utilizadas
- **Git**
- **Bash**
- **Task Scheduler (Agendador de Tarefas)**

## Funcionalidades
- **Backup automático**: Realiza backup a cada três dias no repositório Git.
- **Atualização manual**: Disponibiliza um botão para execução manual do backup.

---

## Configuração do Backup Automático com Task Scheduler

1. **Abra o Agendador de Tarefas**
   No Windows, abra o **Task Scheduler** (Agendador de Tarefas) através da busca no menu Iniciar.

   ![Abrir Agendador de Tarefas]
   ![Pasted image 20240908125948](https://github.com/user-attachments/assets/f7a2d625-1625-463f-a9d2-76202b92abcd)


3. **Criar uma Nova Tarefa**
   Na janela do Agendador de Tarefas, clique em **Criar Tarefa Básica**.

   ![Criar nova tarefa](![Pasted image 20240908130323](https://github.com/user-attachments/assets/bdc191a4-ae19-4147-ae05-1f53828ba77d)
)

4. **Configurar a Ação**
   Vá até a aba **Ações**, clique em **Novo**, e selecione "Iniciar Programa". 
   - Escolha o arquivo de script que você criou (veja o código na seção abaixo).

5. **Condições**
   vá em ações, "novo", depois em "iniciar programa" selecione o arquivo que criamos depois vá em condições, e ative a função para executar apenas quando estiver com uma conexão ativa (internet), afinal você não quer dar push sem internet e receber um fatal error, não é mesmo?

6. **Disparadores**
   Em **Disparadores**, configure a tarefa para ser executada **a cada 3 dias**, garantindo a periodicidade do backup.

---

## Script de Backup

Crie um script Bash para ser executado pelo Task Scheduler. Aqui está um exemplo de código:

```bash
cd /d C:\Users\Henrique RIbeiro\Documents\lifework
git add .
git commit -m "atualização automática em %date%"
git push origin master (ou o nome da sau remote url e branch principal)
```

Este script adiciona, commita e faz o push de todas as alterações no diretório de trabalho para o repositório Git. Ele deve ser salvo como um arquivo `.bat` ou `.sh`, dependendo do seu ambiente.

---



Este cronograma executa o script a cada 3 dias, à meia-noite.

---

## Atualização Manual

Se desejar, você também pode criar um botão manual para forçar uma atualização no Obsidian. Para isso, consulte a seção de documentação sobre como adicionar botões de ação no Obsidian com plugins como **Templater** ou **Buttons**.

---

Com isso, seu backup estará automatizado e garantirá que seus arquivos estejam sempre seguros e sincronizados com o GitHub

---
