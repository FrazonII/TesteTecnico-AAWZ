# README Padrão até linha 53
# Formulario

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Run End-to-End Tests with [Cypress](https://www.cypress.io/)

```sh
npm run test:e2e:dev
```

This runs the end-to-end tests against the Vite development server.
It is much faster than the production build.

But it's still recommended to test the production build with `test:e2e` before deploying (e.g. in CI environments):

```sh
npm run build
npm run test:e2e
```

# Observações do Projeto

Processar NPM's
```sh
npm install
npm run dev
npm install axios
```

## Funções Implementadas

Foi utilizado o "projeto" padrão do Vue.js no site oficial para estruturar o código.

O formulário pode receber as informações necessárias em cada campo separado: nome; e-mail; endereço; cidade; uf; CEP.

Na inserção do "CEP" é realizada uma validação no dado recebido utilizando a API do viacep, aonde ele verifica a existência do CEP e caso exista já preenche automaticamente com as informações vigentes.

## Funções não implementadas

Armazenamento dos dados inseridos;
Resumo dos usuários por Estado;
Resumo dos usuários por Origem;
Tabela de usuários cadastrados;
Biblioteca para state management, Vuex.

# Por qual razão a meta final não foi atingida?

Infelizmente o projeto completo não pode ser executado da maneira solicitada no documento do teste técnico.
Mesmo tendo conhecimentos básicos em html e css, me vi em uma situação difícil quando apresentado ao Vue.js, levando em consideração que a base de javascript também é rasa. 
Porém, com muito esforço e dedicação vejo que pude ir além do imaginado até mesmo por mim. Mesmo trabalhando o dia inteiro e não podendo utilizar meu computador por mais tempo do que o desejado (situação familiar em que vivemos no momento não permite a utilização do quarto), pude buscar conhecimento em estudos por exemplo: udemy, curso em vídeo (Gustavo Guanabara), profissionais da área, chatGPT.
Abrindo o site oficial da AAWZ também busquei compreender o código que havia na página para eu buscar insights que pudessem ser úteis. Vendo a paleta de cores da empresa, não consegui aplicar no formulário pois a visualização não ficaria amigável.