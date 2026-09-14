# Rayton Casa Completa

Site institucional da Rayton Casa Completa — tintas e material de construção,
com três lojas em Ubatuba, Taubaté e Pindamonhangaba.

**Entregue e no ar** · [lojasrayton.com](https://lojasrayton.com)

---

## Sobre o projeto

Primeiro projeto entregue a cliente pagante. Substituiu um site anterior
feito em Canva, hospedado em servidor Windows (IIS) da Locaweb.

Página única, com as três lojas, categorias de produto e contato por
WhatsApp. Feito do zero: layout, código, otimização de imagens e publicação.

## Decisões técnicas

**Sem framework.** HTML, CSS e JavaScript puro. Uma página, sem build e sem
dependência de pacote.

**Configuração do IIS (`web.config`).** A hospedagem é Windows, e isso exigiu
três ajustes que não aparecem em hospedagem Linux:

- **Registro de MIME para `.webp`, `.svg` e `.woff2`.** O IIS não conhece
  essas extensões por padrão e **recusa servir o arquivo** — o site abre sem
  imagem e sem fonte, sem dar erro visível. Cada uma precisa ser declarada.
- **`index.html` como documento padrão**, para a raiz do domínio responder.
- **Redirecionamento 301 de `/home` para a raiz.** O site anterior vivia
  nesse endereço e o Google ainda o tinha indexado. Um 301 permanente leva
  quem clica no link antigo para a página certa e avisa o buscador para
  atualizar o índice — em vez de entregar um 404 para quem já conhecia a loja.

**Imagens em WebP**, com `width` e `height` declarados para evitar
deslocamento de layout durante o carregamento.

**Dados estruturados** em JSON-LD, para o Google exibir as informações das
lojas direto no resultado de busca.

## Tecnologias

`HTML5` · `CSS3` · `JavaScript` · `Schema.org / JSON-LD` · `IIS / web.config`

## Estrutura

```
index.html      pagina completa, com CSS e JS embutidos
web.config      configuracao do IIS: MIME types, documento padrao e 301
img/            fachadas das tres lojas em .webp e logo
```

---

## Autor

**William dos Santos** — desenvolvedor web, Ubatuba/SP

[LinkedIn](https://www.linkedin.com/in/william-dos-santos-) ·
[Instagram](https://instagram.com/williamsantxs) ·
williamdsantos.souza@gmail.com
