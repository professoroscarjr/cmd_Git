# Como aumentar seu potencial de uso no Git

Este tutorial traz dicas e comandos avançados para você evoluir no uso do Git e ganhar produtividade no controle de versões.

---

## 1. Trabalhe com Branches de Forma Eficiente

- Crie branches para cada feature ou correção:
  ```bash
  git checkout -b nome-da-branch
  ```
- Liste branches locais e remotas:
  ```bash
  git branch       # locais
  git branch -r    # remotas
  ```
- Apague branches já mescladas:
  ```bash
  git branch --merged
  git branch -d nome-da-branch
  ```

---

## 2. Use Aliases para Comandos Frequentes

- Acelere comandos com atalhos:
  ```bash
  git config --global alias.co checkout
  git config --global alias.st status
  git config --global alias.lg "log --oneline --graph --all"
  ```
- Agora, basta usar `git co`, `git st` e `git lg`.

---

## 3. Limpe seu Histórico com Rebase

- Mantenha o histórico linear:
  ```bash
  git fetch origin
  git rebase origin/main
  ```
- Reescreva commits locais antes de dar push:
  ```bash
  git rebase -i HEAD~3
  ```
  (Permite editar, combinar ou apagar commits)

---

## 4. Stash: Guarde Mudanças Temporárias

- Salve alterações não finalizadas:
  ```bash
  git stash
  ```
- Recupere depois:
  ```bash
  git stash pop
  ```

---

## 5. Bisect: Encontre Bugs Rapidamente

- Use busca binária para encontrar o commit que introduziu o erro:
  ```bash
  git bisect start
  git bisect bad      # marca o commit atual como ruim
  git bisect good <hash> # marca um commit antigo como bom
  # Siga testando até o Git apontar o commit problemático
  git bisect reset
  ```

---

## 6. Visualize o Histórico de Forma Avançada

- Veja um log compacto e visual:
  ```bash
  git log --oneline --graph --decorate --all
  ```

---

## 7. Reflog: Recupere Commits Perdidos

- Se perdeu um commit após reset ou rebase:
  ```bash
  git reflog
  git checkout <hash>
  ```

---

## 8. Hooks: Automatize Ações

- Scripts que rodam em eventos Git (ex: pre-commit, post-merge)
- Exemplo: checar lint antes de commit
  ```bash
  echo "npm run lint" > .git/hooks/pre-commit
  chmod +x .git/hooks/pre-commit
  ```

---

## 9. Integre com GitHub

- Crie pull requests e faça code review pelo GitHub
- Use o GitHub CLI:
  ```bash
  gh pr create
  gh pr checkout <número>
  ```

---

## 10. Dicas Extras

- Sempre escreva mensagens de commit claras e descritivas.
- Use `.gitignore` para evitar versionar arquivos desnecessários.
- Explore o arquivo `.gitconfig` para personalizar ainda mais o seu ambiente.

---

## Referências

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [GitHub CLI](https://cli.github.com/)
- [Git Cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)

---

Com estas dicas, você poderá usar o Git de maneira mais avançada e eficiente!
