# Dotfiles

Minhas configurações pessoais para Linux, gerenciadas com Git e GNU Stow.

## Configurações incluídas

* Niri
* Fish
* Noctalia

## Instalação

Clone o repositório:

```bash
git clone https://github.com/goncalvespedroo/dotfiles.git ~/dotfiles
cd ~/dotfiles
```

Instale o GNU Stow.

No Fedora:

```bash
sudo dnf install stow
```

No Arch/CachyOS:

```bash
sudo pacman -S stow
```

## Restaurar as configurações

Antes de aplicar os dotfiles, faça backup de configurações existentes, caso elas já existam:

```bash
mv ~/.config/niri ~/.config/niri.backup
mv ~/.config/fish ~/.config/fish.backup
mv ~/.config/noctalia ~/.config/noctalia.backup
```

Depois aplique as configurações:

```bash
cd ~/dotfiles
stow niri
stow fish
stow noctalia
```

Ou de uma vez:

```bash
stow niri fish noctalia
```

## Atualizar os dotfiles

Depois de alterar alguma configuração:

```bash
cd ~/dotfiles
git status
git add .
git commit -m "Update configuration"
git push
```

## Restaurar mudanças do GitHub

Para baixar mudanças feitas em outra máquina:

```bash
cd ~/dotfiles
git pull
```

Como os arquivos ativos são links simbólicos criados pelo Stow, as configurações atualizadas passam a ser usadas diretamente pelo sistema.

## Estrutura

```text
dotfiles/
├── fish/
│   └── .config/fish/
├── niri/
│   └── .config/niri/
├── noctalia/
│   └── .config/noctalia/
└── .gitignore
```

## Importante

Não adicionar ao repositório:

* senhas
* tokens
* chaves SSH
* API keys
* arquivos de sessão
* dados pessoais ou arquivos de trabalho

O objetivo deste repositório é permitir reconstruir rapidamente meu ambiente Linux sem precisar configurar Niri, Fish e Noctalia manualmente novamente.
