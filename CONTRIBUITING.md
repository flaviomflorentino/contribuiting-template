<p align="center">
    <img src="front-end.jpg" width="100%" />
</p>

# Contribuindo com o Apollo Design System Web

### Estamos aguardando sua colaboração! :)

> Adoraríamos que você contribuísse com nosso ds! Leia este documento para ver como contribuir.

### Por que eu deveria ler este guia? 

>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas ut dignissim ligula. Nulla ornare felis risus, quis tristique elit ullamcorper ut. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.

### Por quais tipos de contribuições estamos em busca?

Mantenha a mente aberta, existem muitas evoluções a serem feitas! 

Exemplos de contribuições úteis que significam menos trabalho para você:

- Melhorar a documentação
- Evolução de bugs  
- Criação de tutoriais
- Inclusão/correção de testes unitários

Exemplos de contribuições úteis e que demandam maior tempo/complexidade e passam por um processo de revisão crítico:

- Criação de novos componentes
- Implementação de novos funcionalidades  
- Remoção de componentes/funcionalidades em uso

Se você vir uma lacuna, mas não tiver tempo, experiência ou apenas precisar de ajuda com o ds, não hesite em iniciar uma discussão em nosso canal no slack `#apollo-design-system` ou abrir um issue.

### O que não procuramos

Fique atento a nossas regras de contribuição, pois caso ignoradas sua solicitação/issue/contribuição pode ser fechada.

> Por favor, não use as issues para perguntas de suporte. Verifique se o canal `#frontenders` no `slack` pode ajudar com seu problema. Ou em casos mais críticos entre em contato com os desenvolvedores do ds.

___

# Criando meu primeiro componente

Começe clonando nosso repositório

- `git clone https://github.com/PicPay/picpay-frontend.git`

Crie uma branch a partir da DEVELOP com o seguinte padrão para novos componentes:

- `git checkout -b feat/design-system/nome-do-componente`

Instale a extensão `NX Console` no `VSCode`. Selecione a opção Generate no NX Console e escolha a opção stencil - component.

<img src="stencil-component.png" />

Escolha um nome para o componente utilizando da notação dash-case. Por padrão os componentes do DS possuem o seu nome na frente, <b>apollo</b>:

<img src="generate.png" />

O console do Nx disponibilizara o seguinte comando:

- `nx generate @nxext/stencil:component --name=apollo-component --project=design-system --no-interactive`

Após realizar o paso anterior será criada uma pasta com o componente dentro de src/components, seguindo a estrutura:

- `libs/design-system/src/components/apollo-component`

- Pra ficar mais fácil a leitura dos componentes temos tirado o prefixo apollo da pasta/arquivos, deixando somente no nome do componente e tag-html:

<img src="example.png" />

Crie os arquivos .stories.tsx e .docs.mdx do storybook na pasta do seu componente:

<img src="doc-files.png" />

Para visualizar o seu componente no storybook execute o comando:

- `nx storybook design-system`

Após finalizar o desenvolvimento do componente, é necessário fazer o build para que ele fique disponível para utilizar na sua aplicação. Portanto, execute o comando:

- `nx build design-system`

Depois de implementado, crie uma PR e solicite a aprovação do time do Design System Apollo.

Pronto! Após a aprovação você já consegue utilizar o seu novo componente! :smile: 


## Ao colaborar com criação de um novo componentes valide os critérios abaixo

- Toda a estilização do componente deve ser feita através de nossos tokens(css e javascript)
- Testes unitários com no mínimo 70% de cobertura
- Documentação completa no storybook, contemplando todos as variações do componente
- Documentação do uso de componentes filhos
- Validação da equipe de design do ds
- Validação da equipe de front-end do ds

>Não se esqueça de rodar o lint após o desenvolvimento do novo componente. Tanto para estilos(stylelint) quanto para html e typescript(eslint).

- `npm run lint:css`
- `nx lint design-system`