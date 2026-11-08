# SATURN · Canal oficial de testes Android 🪐

Este repositório público distribui **somente** arquivos de instalação Android e o manifesto `update.json` do aplicativo SATURN.

O código-fonte, as credenciais, as notas e as coleções de usuários ficam **fora deste repositório**.

## Estado

**Canal criado, aguardando primeira versão assinada.** Não existe APK oficial nem manifesto de atualização publicado neste momento. Não envie manualmente um APK debug ao canal de releases: APKs de teste podem ter assinaturas diferentes e prejudicar atualizações sobrepostas.

## Como funcionarão os lançamentos

A pipeline privada de `Nrzxl/saturn-mobile` irá:

1. Analisar, testar e compilar um APK Android release.
2. Assinar com um **keystore persistente** armazenado nos GitHub Actions Secrets do repositório privado.
3. Publicar o APK neste repositório como uma GitHub Release.
4. Calcular o SHA-256 do APK e atualizar `update.json` **somente após** a publicação da release.

O aplicativo consultará `https://raw.githubusercontent.com/Nrzxl/saturn-downloads/main/update.json` quando o usuário abrir a área *Atualizar SATURN*. A instalação requer confirmação do usuário no Android; não é automática nem silenciosa.

## Informações públicas

O arquivo `update.json` terá as chaves `version`, `build`, `apk_url`, `sha256` e `notes`. Expor o APK e os metadados da versão é intencional; **nunca** publique informações privadas, tokens ou arquivos `*.keystore` aqui.

## Android e iPhone

O APK Android não funciona no iPhone. O fluxo nativo de iOS será disponibilizado separadamente por TestFlight/Apple, enquanto a versão Web poderá usar uma hospedagem independente.

## Direitos e segurança

SATURN é um aplicativo independente para organizar filmes, séries e livros. Não hospeda ou distribui filmes, séries, livros digitais nem conteúdo de streaming.
