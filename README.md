# Lista de Compras — PWA + Firebase

Aplicativo compartilhado para duas ou mais pessoas, com:
- nome salvo em cada aparelho, sem login visível;
- uma Casa compartilhada por código de 6 dígitos;
- sincronização em tempo real via Firestore;
- “solicitado por” e “comprado por” automáticos;
- histórico de compras;
- supermercado, preço e preço por unidade;
- previsão simples de recompra;
- modo claro/escuro;
- backup JSON;
- instalação como PWA em Android e iPhone.

## 1. Criar o projeto no Firebase

1. Acesse o Firebase Console e crie um projeto.
2. Adicione um **aplicativo Web**.
3. Copie o objeto `firebaseConfig`.
4. Abra `firebase-config.js` e substitua os campos `COLE_AQUI`.

## 2. Ativar autenticação anônima

Firebase Console:
**Build > Authentication > Sign-in method > Anonymous > Enable**

O usuário não verá tela de login. A autenticação anônima existe apenas para dar um identificador seguro a cada instalação.

## 3. Criar Firestore

Firebase Console:
**Build > Firestore Database > Create database**

Escolha a região desejada.

## 4. Aplicar as regras

Em:
**Firestore Database > Rules**

Substitua as regras pelo conteúdo de `firestore.rules` e publique.

## 5. GitHub Pages

Crie um repositório e envie todos os arquivos da pasta.

Depois:
**Settings > Pages > Deploy from a branch > main > /root**

Aguarde o GitHub mostrar a URL pública.

## 6. Primeiro aparelho

1. Abra a URL.
2. Informe seu nome.
3. Toque em **Criar casa**.
4. Copie o código de 6 dígitos mostrado no perfil.

## 7. Segundo aparelho

1. Abra a mesma URL.
2. Informe o nome da segunda pessoa.
3. Toque em **Entrar em casa**.
4. Digite o código do primeiro aparelho.

A partir daí os dois aparelhos usam a mesma lista em tempo real.

## 8. Instalar como app

### Android
Abra no Chrome > menu > **Adicionar à tela inicial / Instalar app**.

### iPhone
Abra no Safari > Compartilhar > **Adicionar à Tela de Início**.

## Observação importante

O arquivo `firebase-config.js` não contém uma senha secreta. Em apps Web do Firebase, a segurança real vem das regras do Firestore e da autenticação. Mesmo assim, mantenha as regras publicadas exatamente ou mais restritivas que as fornecidas aqui.


## Atualização v3
Substitua index.html e service-worker.js no GitHub. Não substitua o firebase-config.js já configurado. A versão adiciona datas futuras, filtros, prioridade, categorias, calendário e recorrência.


## Atualização v4

A aba Compras agora permite tocar em qualquer compra realizada para editar:
- produto;
- data;
- quantidade e unidade;
- preço total;
- supermercado;
- solicitado por;
- comprado por;
- categoria;
- observação.

Também é possível excluir uma compra do histórico. As mudanças são salvas no Firebase e aparecem automaticamente em todos os aparelhos da Casa.

Para atualizar, substitua no GitHub apenas `index.html` e `service-worker.js`. Não altere seu `firebase-config.js`.
