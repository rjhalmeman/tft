# 🧭 Guia de Colaboração no Projeto `projetoBeta`

Este documento define o **fluxo de trabalho Git padronizado** para o projeto **`projetoBeta`**, com o objetivo de manter organização e controle de versões entre os colaboradores.

---

## 👥 Participantes

- **Radames** — mantenedor do repositório principal (branch `main`)
- **João** — colaborador (ex: branch `crudPessoa`)
- **Maria** — colaboradora (ex: branch `crudPedido`)

---

## 🔐 1. Acesso ao Repositório Privado

Radames deve conceder acesso ao repositório privado:

```bash
# No GitHub (interface web)
# Acesse Settings > Collaborators > Add people
# Adicione os usuários GitHub de João e Maria como "Collaborators"
```

---

## 🧩 2. Clonando o Repositório

Cada colaborador deve clonar o repositório pela primeira vez:

```bash
git clone git@github.com:rjhalmeman/projetoBeta.git
cd projetoBeta
```

> ⚠️ Use o link SSH (não HTTPS) para evitar pedir senha sempre.

---

## 🌿 3. Criando uma Branch de Trabalho

Antes de iniciar uma nova tarefa:

```bash
git checkout main
git pull origin main  # atualiza com as últimas mudanças
git checkout -b crudPessoa   # João cria essa
# ou
git checkout -b crudPedido   # Maria cria essa
```

---

## 💻 4. Fazendo Alterações e Commits

Após editar arquivos no projeto:

```bash
git add .
git commit -m "Implementa CRUD de Pessoa"
```

Commits devem ser **claros e descritivos**, por exemplo:

- `Adiciona tela de listagem de pedidos`
- `Corrige bug ao salvar pessoa`
- `Atualiza README com instruções`

---

## ☁️ 5. Enviando Branch para o GitHub

Quando a funcionalidade estiver pronta:

```bash
git push origin crudPessoa
# ou
git push origin crudPedido
```

---

## 🔄 6. Criando um Pull Request (PR)

1. Acesse o repositório no GitHub (`projetoBeta`).
2. Clique em **Compare & Pull Request**.
3. Verifique se o destino é **base: main** e origem é sua branch (`crudPessoa`).
4. Adicione uma descrição e clique em **Create Pull Request**.

---

## 🧑‍💻 7. Revisão e Aprovação

- **Radames** revisa o código enviado via PR.
- Se estiver tudo certo, ele executa o **merge**:

```bash
# Local ou via GitHub
git checkout main
git pull origin main
git merge crudPessoa
git push origin main
```

Após o merge, o colaborador pode deletar a branch antiga:

```bash
git branch -d crudPessoa
git push origin --delete crudPessoa
```

---

## 🔁 8. Mantendo o Repositório Atualizado

Antes de iniciar uma nova tarefa, sempre atualizar o ambiente local:

```bash
git checkout main
git pull origin main
```

---

## 📋 Exemplo de Fluxo Completo (João)

```bash
git clone git@github.com:rjhalmeman/projetoBeta.git
cd projetoBeta
git checkout -b crudPessoa
# (faz alterações no código)
git add .
git commit -m "Implementa CRUD de Pessoa"
git push origin crudPessoa
# Cria Pull Request no GitHub
```

## 📋 Exemplo de Fluxo Completo (Maria)

```bash
git clone git@github.com:rjhalmeman/projetoBeta.git
cd projetoBeta
git checkout -b crudPedido
# (faz alterações no código)
git add .
git commit -m "Implementa CRUD de Pedido"
git push origin crudPedido
# Cria Pull Request no GitHub
```

---

## ✅ Boas Práticas

- Sempre trabalhar em **branchs separadas** por tarefa.
- Nunca alterar diretamente a **main**.
- Fazer commits pequenos e com mensagens claras.
- Atualizar frequentemente o repositório local (`git pull origin main`).

---

**Radames Halmeman — 2025**
