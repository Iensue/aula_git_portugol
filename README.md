# Atividade Avaliativa: Git Colaborativo com Portugol

## Integrantes do grupo
* **Gustavo Iensue** (Gerente do Projeto )
* **[Oliveira]** (Desenvolvedor Colaborador)

## Objetivo
Desenvolver colaborativamente um algoritmo em Portugol para realizar operações matemáticas básicas (soma e subtração), simulando um fluxo de trabalho profissional com Git, uso de branches, Pull Requests e merge via terminal.

## Etapas realizadas

### 1. Gustavo Iensue (Gerente)
* **Criação do Repositório:** Criou o repositório no GitHub com um `README.md` inicial.
* **Clone e Configuração:** Clonou o repositório na máquina local utilizando chave SSH.
* **Código Inicial (Soma):** Criou o arquivo `algoritmo.por` implementando a estrutura básica e a função de **Soma**.
* **Envio:** Realizou o commit e o push para a branch `main`.

### 2. [Oliveira] (Desenvolvedor)
* **Clone:** Clonou o repositório para colaborar.
* **Branch de Feature:** Criou a branch `feature-subtracao` para isolar o desenvolvimento.
* **Implementação (Subtração):** Adicionou a lógica de **Subtração** ao arquivo `algoritmo.por`.
* **Envio:** Fez o commit das alterações e o push da branch para o repositório remoto.
* **Pull Request:** Solicitou a integração do código via Pull Request.

### 3. Gustavo Iensue (Gerente)
* **Revisão e Merge:** Baixou as alterações do remoto, verificou o código da feature e realizou a integração (merge) na `main` via terminal.
* **Limpeza:** Removeu a branch de feature local e remotamente após o sucesso da integração.

---

## Comandos Utilizados

Abaixo estão os comandos executados no terminal durante o processo:

### Comandos Iniciais (Gustavo Iensue)
```bash
git clone git@github.com:iensue/nome-do-repo.git
# Criação do arquivo algoritmo.por
git add .
git commit -m "soma"
git push origin main

### Comandos de Desenvolvimento (Conta Desenvolvedor)
```bash
git clone git@github.com:Iensue/aula_git_portugol.git
cd aula_git_portugol
git switch -c feature-subtracao
# Abertura do VS Code e implementação da subtração
git add .
git commit -m "feat: implementar subtracao"
git push -u origin feature-subtracao

### Comandos de Integração/Merge (Gustavo Iensue)
```bash
# 1. Atualizar referências remotas
git fetch --all --prune

# 2. Garantir que está na main e atualizado
git checkout main
git pull origin main

# 3. Trazer a branch da feature para o local para conferência
git fetch origin feature-subtracao:feature-subtracao

# 4. Verificações de log e diferenças antes do merge
git log --oneline --graph --decorate main..feature-subtracao
git diff main..feature-subtracao

# 5. Realizar o Merge
git checkout main
git merge --no-ff feature-subtracao -m "merge: integrar feature-subtracao na main"

# 6. Enviar alterações para a main remota
git push origin main

# 7. Limpeza das branches (remota e local)
git push origin --delete feature-subtracao
git branch -d feature-subtracao