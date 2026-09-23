# Conectar mais de uma conta do Instagram

Este guia vale para esta instalação do OpenReply, que usa um app próprio da Meta
criado por **pessoa física** (sem empresa e sem verificação de empresa). Nesse
modelo, o app fica com **Acesso Padrão** (Standard Access) às permissões do
Instagram, e o Acesso Padrão só funciona para contas que têm uma função no app.
Por isso, toda conta nova precisa ser cadastrada como testadora antes de ser
conectada.

O OpenReply aceita várias contas profissionais do Instagram no mesmo espaço de
trabalho. Cada conta tem as próprias campanhas e o próprio limite de envios
(750 respostas privadas por hora, conforme a Meta).

## Pré-requisitos

- A conta precisa ser **Comercial** ou **de Criador de conteúdo**. Conta pessoal
  não conecta. No app do Instagram: Configurações, Tipo de conta.
- Você precisa conseguir entrar nessa conta do Instagram (para aceitar o convite
  e autorizar a conexão).
- A conta não pode estar conectada a outro espaço de trabalho do OpenReply.

## Passo a passo

### 1. Convidar a conta como testadora no app da Meta

1. Acesse [developers.facebook.com/apps](https://developers.facebook.com/apps) e
   abra o app **OpenReply Devoluapp**.
2. No menu lateral, abra **Funções do app → Funções**.
3. Clique em **Adicionar pessoas**, escolha **Testador do Instagram** e digite o
   nome de usuário exato da conta (sem o @).
4. Clique em **Adicionar**. A conta aparece na lista com o status **Pendente**.

### 2. Aceitar o convite com a conta do Instagram

O aplicativo do celular nem sempre mostra o convite. O caminho mais confiável é
o navegador:

1. Entre no Instagram pelo navegador **com a conta convidada**.
2. Abra `https://www.instagram.com/accounts/manage_access/`.
3. Na aba **Convites de testador**, aceite o convite de **OpenReply Devoluapp**.
4. Volte à tela de funções do app na Meta e confira se o status **Pendente**
   sumiu.

### 3. Conectar a conta no OpenReply

1. Entre em `https://openreply.devoluapp.cloud` com o seu e-mail.
2. Vá em **Configurações** e clique em **Conectar outra conta do Instagram**.
3. Na tela do Instagram, entre com a conta nova (se estiver logado com outra
   conta, troque antes) e autorize todas as permissões pedidas.
4. De volta ao OpenReply, a conta aparece na lista de contas conectadas.

### 4. Criar campanhas para a conta nova

- Use o seletor de conta no topo do painel para escolher a conta antes de criar
  a campanha. Cada campanha fica vinculada à conta selecionada.
- Teste comentando a palavra-chave com **outra** conta do Instagram. O OpenReply
  ignora comentários da própria conta de propósito.

## O que não precisa fazer

- **Webhook:** o mesmo webhook do app atende todas as contas. Não é preciso
  mexer na configuração de webhooks da Meta.
- **Variáveis de ambiente e Coolify:** nada muda na instalação.
- **Publicação do app:** o app já está publicado; contas novas só precisam da
  função de testador.

## Problemas comuns

| Sintoma | Causa provável | Solução |
| --- | --- | --- |
| "Insufficient Developer Role" na tela de login do Instagram | A conta não foi convidada ou não aceitou o convite | Refaça os passos 1 e 2 |
| O login no Instagram funciona, mas a conexão falha ou todas as chamadas retornam `Unsupported request - method type: get` | A conta tem token válido, mas não tem função no app | Confira se o convite foi aceito (passo 2) e conecte de novo |
| "Essa conta do Instagram está conectada a outro espaço de trabalho" | A conta já está em outro espaço de trabalho | Desconecte lá primeiro |
| O convite não aparece no celular | Limitação do app do Instagram | Use o endereço `instagram.com/accounts/manage_access/` no navegador |

## Limites

- O app aceita até **50 testadores do Instagram**.
- Para contas de **outras pessoas** que você não pode cadastrar como testadoras,
  seria necessário o **Acesso Avançado**, que exige Análise do App e
  verificação de empresa pela Meta. Veja [META_APP_REVIEW.md](../META_APP_REVIEW.md).
