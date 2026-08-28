# warspear (PKGBUILD)

Espelho do pacote [`warspear` do AUR](https://aur.archlinux.org/packages/warspear),
mantido separado para poder acompanhar as versões do jogo sem depender do ritmo
de atualização do AUR.

O histórico completo do upstream está preservado neste repositório, com a
autoria original de cada commit. Ver `git log`.

## Créditos

O pacote original é obra de:

- Sergei Marochkin `<me@ziggi.org>` (mantenedor no AUR)
- Mikhail Velichko `<efklid@gmail.com>`
- Vitaliy Popov `<symbx.live@gmail.com>`
- e demais contribuidores no histórico

Este fork só ajusta a versão empacotada.

## O que este repositório NÃO contém

**O jogo.** Warspear Online é software proprietário (`Copyright AIGRIND LLC`,
licença `AIGRIND-1.0`, distribuído como `non-free`).

O `PKGBUILD` apenas aponta para o `.deb` oficial no servidor da AIGRIND, que é
baixado pelo `makepkg` no momento da compilação. Nada do jogo é redistribuído
aqui, e nada deve ser adicionado.

## Diferença para o upstream

| | upstream (AUR) | aqui |
|---|---|---|
| `pkgver` | 13.4.2 | **13.4.3** |

Nada mais foi alterado além do `pkgver`, dos dois `sha512sums` e do cabeçalho
de mantenedor.

## Uso

```bash
makepkg -si
```

## Atualizar quando sair versão nova

```bash
# 1. conferir se a versão já está publicada pelo fornecedor
curl -sI "http://distr.warspear-online.com/linux/pool/non-free/w/warspear/warspear_<VERSAO>_amd64.deb" | head -1

# 2. subir a versão e recalcular os hashes
sed -i 's/^pkgver=.*/pkgver=<VERSAO>/' PKGBUILD
updpkgsums                          # pacote: pacman-contrib

# 3. regenerar os metadados (ESSENCIAL — o .SRCINFO não se atualiza sozinho)
makepkg --printsrcinfo > .SRCINFO

# 4. instalar
makepkg -si
```

## Acompanhar o upstream

A branch local aqui é `main`; a do AUR é `master`.

```bash
git remote add aur https://aur.archlinux.org/warspear.git   # se ainda não existir
git fetch aur
git log main..aur/master          # o que mudou lá e não está aqui
git log aur/master..main
git merge aur/master              # trazer, se fizer sentido
```
