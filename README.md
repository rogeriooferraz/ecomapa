# EcoMapa

O **EcoMapa** é uma plataforma proposta para facilitar a localização de pontos
públicos e privados de coleta de resíduos eletrônicos.

A iniciativa busca reunir, em uma única experiência, informações sobre locais
que recebem diferentes categorias de resíduos, como pilhas, baterias, lâmpadas,
eletrônicos e eletrodomésticos.

## Contexto acadêmico

O EcoMapa é desenvolvido como **Projeto Integrador** da turma de
**Programação de Dispositivos Móveis — período vespertino**, do
**IFSP - PRONATEC, Campus Diadema**.

O projeto pretende aproximar a população de pontos de coleta e coletores,
facilitando o descarte correto de resíduos eletrônicos e o acesso a informações
relevantes sobre os locais disponíveis.

## Proposta inicial

A experiência prevista inclui:

- localização de pontos de coleta próximos ao usuário;
- busca por tipo de resíduo;
- identificação de categorias a partir dos dados dos coletores;
- filtros gerados a partir das informações disponíveis;
- informações sobre pontos públicos e privados;
- consulta a dados de contato e atendimento;
- cadastro de usuários e coletores;
- cadastro e validação de pontos de coleta;
- tela de cadastro de pontos de coleta.

O escopo poderá ser ajustado conforme a evolução do projeto.

## Colaboração

As orientações para participação no projeto estão em
[`docs/CONTRIBUTING.md`](docs/CONTRIBUTING.md).

Cada integrante pode registrar sua participação em
[`docs/CONTRIBUTORS.md`](docs/CONTRIBUTORS.md), informando apenas dados
adequados para publicação no repositório.

## Interface

A interface é planejada para funcionar de forma responsiva em celulares,
tablets e computadores, priorizando a busca, os filtros e a visualização do
mapa conforme o espaço disponível em cada tela.

## Busca e categorização

A busca é orientada pelo resíduo que o usuário deseja descartar. Termos mais
específicos, como `geladeira`, podem ser associados à categoria correspondente,
como `Eletrodomésticos`, e usados para destacar pontos de coleta que informem
atendimento especializado para esse tipo de item.

As categorias e opções de filtro devem refletir os dados informados pelos
coletores cadastrados, evitando apresentar opções sem pontos de coleta
correspondentes.

A área do mapa utiliza a localização do usuário como referência, obtida pelo
endereço cadastrado quando disponível ou por localização aproximada quando
necessário.

## Comportamento em telas menores

Em celulares, a interface prioriza a busca e o mapa. Categorias e filtros são
apresentados depois da área principal. Em telas maiores, essas opções passam
para uma barra lateral à esquerda, mantendo o mapa como elemento central da
navegação.

## Arquivos de estilo

As duas páginas usam o CSS minificado do Bootstrap 5.3.8 via CDN. O arquivo
`frontend/css/style.css` contém os estilos próprios do mapa ilustrativo, e
`frontend/css/watermark.css` contém a marca d'água temporária.

## Estrutura do projeto

```text
ecomapa/
├── .github/
├── .gitignore
├── docs/
│   ├── CONTRIBUTING.md
│   └── CONTRIBUTORS.md
├── frontend/
│   ├── .nojekyll
│   ├── cadastro.html
│   ├── css/
│   ├── favicon.ico
│   ├── favicon.svg
│   ├── images/
│   ├── index.html
│   ├── js/
│   └── site.webmanifest
└── README.md
```

`frontend/` é a raiz do site publicado. Os caminhos entre páginas, estilos e
ícones são relativos a essa pasta. `docs/` reúne a documentação do projeto;
`.gitignore` e `README.md` permanecem na raiz. `frontend/js/` está reservado
para scripts futuros e contém `.gitkeep` para que o Git registre a pasta.

## Visualização local

Na raiz do repositório, execute:

```sh
python3 -m http.server 8000 --directory frontend
```

Depois, abra `http://localhost:8000/`. Não é necessário instalar dependências
para visualizar as páginas; o Bootstrap é carregado por CDN.

## Publicação

O workflow `.github/workflows/pages.yml` publica o conteúdo de `frontend/` no
GitHub Pages quando há alterações na branch `main`. O domínio `ecomapa.app` está
configurado nas opções do GitHub Pages.
