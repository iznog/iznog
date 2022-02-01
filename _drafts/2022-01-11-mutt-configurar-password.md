---
layout: post
title: Mutt - configurar acesso a passwords 
date: 2022-01-14
author: Paulo
categories: linux, mutt, auth
---

# gerar uma chave
gpg --full-generate-key
indicação de nome e email da chave
# criar ficheiro de texto com passwords
vim .mutt_secrets

# encriptar ficheiro 
gpg -r email@exemplo.com -e ./mutt_secrets

# eliminar ficheiro de texto
shred -u .mutt_secrets

#confirmar a existência do ficheiro .mutt_secrets.gpg

colocar no ficheiro mutt a sequencia para abrir e carregar as opções do ficheiro gpg.


