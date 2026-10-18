# Introdução à Computação

## Exercícios de Git & GitHub

**Objetivo:** Usar Git para controlar versões de um projeto individual e GitHub para guardar e sincronizar o repositório: `git init`, `git add`, `git commit`, estados de ficheiros, repositórios remotos, `git push`, `git pull`, `git clone` e resolução de um conflito simples no VS Code.

## Pré-requisitos

-   Conta GitHub ativa.

-   Git instalado e configurado:

    ``` bash
    git --version
    git config --global user.name "O teu nome"
    git config --global user.email "o-teu-email@example.com"
    git config --list
    ```

-   Visual Studio Code instalado.

------------------------------------------------------------------------

## Exercício 1 --- Criar um repositório local

1.  Cria uma pasta chamada `ic-git-exercicio` e abre um terminal nessa pasta.
2.  Inicializa um repositório Git com `git init`.
3.  Cria um ficheiro `README.md` com um título para o projeto e uma breve descrição.
4.  Executa `git status` e identifica o estado do ficheiro.
5.  Prepara o ficheiro para o commit com `git add README.md`.
6.  Executa novamente `git status` e observa o que mudou.
7.  Regista a versão com `git commit -m "Cria README inicial"`.
8.  Executa `git status` e confirma que não existem alterações por registar.

## Exercício 2 --- Criar um repositório remoto e fazer push

1.  No GitHub, cria um repositório chamado `ic-git-exercicio`, sem adicionar automaticamente um README.

2.  Liga o repositório local ao remoto, substituindo `<URL_DO_REPOSITORIO>` pelo endereço do teu repositório:

    ``` bash
    git remote add origin <URL_DO_REPOSITORIO>
    ```

3.  Define a branch principal e envia o commit:

    ``` bash
    git branch -M main
    git push -u origin main
    ```

4.  Abre o repositório no GitHub e confirma que o `README.md` está
    disponível.

## Exercício 3 --- Fazer alterações e comparar estados

1.  Edita o `README.md` e acrescenta uma secção chamada **Funcionalidades**, com duas linhas de texto.
2.  Guarda o ficheiro e executa `git status` e `git diff`.
3.  Observa as alterações apresentadas pelo `git diff`.
4.  Executa `git add README.md` e volta a executar `git status`.
5.  Regista a alteração com `git commit -m "Adiciona funcionalidades ao README"`.
6.  Envia a nova versão para o GitHub com `git push`.
7.  Confirma no GitHub que a versão foi atualizada.

## Exercício 4 --- Adicionar, mover e remover ficheiros

1.  Cria um ficheiro `NOTAS.txt` com três linhas sobre o que aprendeste nesta aula.
2.  Adiciona o ficheiro ao controlo de versões e regista-o num commit.
3.  Renomeia o ficheiro para `APONTAMENTOS.txt` usando `git mv NOTAS.txt APONTAMENTOS.txt`.
4.  Executa `git status` e identifica a alteração.
5.  Regista e envia a alteração para o GitHub.
6.  Remove `APONTAMENTOS.txt` usando `git rm APONTAMENTOS.txt`.
7.  Regista a remoção num novo commit e faz `git push`.
8.  Confirma no histórico do GitHub que as alterações foram registadas.

## Exercício 5 --- Clonar o teu próprio repositório

1.  Cria uma nova pasta fora da pasta original do projeto.
2.  Abre um terminal nessa nova pasta e clona o teu repositório com `git clone <URL_DO_REPOSITORIO>`.
3.  Entra na pasta criada pelo comando `git clone`.
4.  Executa `git log --oneline` e identifica os commits existentes.
5.  Edita o `README.md`, acrescentando uma secção **O que aprendi**.
6.  Regista a alteração com `git add`, `git commit` e `git push`.
7.  Abre a pasta original do exercício e executa `git pull`.
8.  Confirma que a alteração feita na cópia clonada também aparece na pasta original.

## Exercício 6 --- Resolver um conflito entre duas cópias locais

Neste exercício, vais usar duas cópias locais do teu próprio
repositório. Não precisas de trabalhar com outro aluno.

1.  Garante que as duas cópias locais estão sincronizadas com o GitHub, executando `git pull` em cada uma.

2.  Na **primeira cópia**, altera o título inicial do `README.md` para `Projeto de Introdução à Computação - Versão A`. Faz commit e `git push`.

3.  Na **segunda cópia**, sem fazer primeiro `git pull`, altera a mesma linha para `Projeto de Introdução à Computação - Versão B`.

4.  Faz commit da alteração na segunda cópia.

5.  Tenta executar `git push`. O envio deverá ser rejeitado porque o repositório remoto já tem um commit que ainda não existe nesta cópia.

6.  Executa `git pull`. Se surgir um conflito, abre o `README.md` no VS Code e localiza os marcadores `<<<<<<<`, `=======` e `>>>>>>>`.

7.  Edita o ficheiro para escolher ou combinar o conteúdo pretendido. Remove todos os marcadores de conflito e guarda o ficheiro.

8.  Executa `git status`, prepara o ficheiro com `git add README.md` e conclui a resolução:

    ``` bash
    git commit -m "Resolve conflito no README"
    git push
    ```

9.  Confirma no GitHub que a versão final do `README.md` está correta.

**Nota:** Se o Git pedir que escolhas como integrar as alterações durante o `git pull`, segue as instruções apresentadas no terminal ou pede ajuda ao docente. Não apagues os marcadores de conflito sem decidir primeiro qual deve ser o conteúdo final.

## Exercício 7 --- Verificar o histórico e o estado final

1.  Na pasta do projeto, executa `git status` e `git log --oneline`.
2.  Confirma que `git status` indica que a árvore de trabalho está limpa.
3.  Identifica no histórico os commits criados durante os exercícios.
4.  Abre o repositório no GitHub e confirma que a versão remota contém as alterações finais.
5.  No final, deves conseguir explicar a diferença entre `git add`, `git commit`, `git push`, `git pull` e `git clone`.
