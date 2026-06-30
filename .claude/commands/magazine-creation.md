# Magazine Creation Skill

Cria a estrutura completa de uma revista digital com templates HTML/CSS prontos para uso.

## Uso

```
/magazine-creation [nome-da-revista] [tema]
```

## O que este skill faz

Ao ser invocado, cria o seguinte na pasta `revista/` do projeto:

1. **`index.html`** — Página principal / sumário
2. **`capa.html`** — Template de capa
3. **`editorial.html`** — Template de editorial
4. **`artigo.html`** — Template de artigo
5. **`contracapa.html`** — Template de contracapa
6. **`css/estilos.css`** — Folha de estilos completa
7. **`css/print.css`** — Estilos para impressão/PDF
8. **`assets/`** — Pasta para imagens e mídia

## Instruções para o modelo

Quando este skill for invocado, execute as seguintes etapas:

### 1. Coletar parâmetros

Se não fornecidos nos argumentos, pergunte ao usuário:
- Nome da revista
- Tema / foco editorial
- Paleta de cores preferida (ou use padrão: azul e branco)
- Número de seções/artigos esperados

### 2. Criar estrutura de pastas

```
revista/
├── index.html
├── capa.html
├── editorial.html
├── artigo.html
├── contracapa.html
├── css/
│   ├── estilos.css
│   └── print.css
└── assets/
    └── .gitkeep
```

### 3. Gerar os arquivos

Gere cada arquivo com o conteúdo abaixo, substituindo os placeholders pelos valores informados pelo usuário.

#### `index.html` — Sumário

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{NOME_REVISTA}} — Sumário</title>
  <link rel="stylesheet" href="css/estilos.css">
</head>
<body class="pagina-sumario">
  <header class="cabecalho-revista">
    <div class="logo-revista">{{NOME_REVISTA}}</div>
    <div class="edicao-info">Edição {{EDICAO}} • {{MES_ANO}}</div>
  </header>

  <main class="sumario">
    <h1>Nesta Edição</h1>
    <nav class="lista-sumario">
      <a class="item-sumario" href="capa.html">
        <span class="numero-pagina">01</span>
        <div class="info-item">
          <h2>Capa</h2>
          <p>{{CHAMADA_CAPA}}</p>
        </div>
      </a>
      <a class="item-sumario" href="editorial.html">
        <span class="numero-pagina">03</span>
        <div class="info-item">
          <h2>Editorial</h2>
          <p>{{CHAMADA_EDITORIAL}}</p>
        </div>
      </a>
      <a class="item-sumario" href="artigo.html">
        <span class="numero-pagina">05</span>
        <div class="info-item">
          <h2>Artigo Principal</h2>
          <p>{{CHAMADA_ARTIGO}}</p>
        </div>
      </a>
    </nav>
  </main>

  <footer class="rodape-revista">
    <p>{{NOME_REVISTA}} © {{ANO}} — Todos os direitos reservados</p>
  </footer>
</body>
</html>
```

#### `capa.html` — Capa

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{NOME_REVISTA}} — Capa</title>
  <link rel="stylesheet" href="css/estilos.css">
</head>
<body class="pagina-capa">
  <div class="capa-container">
    <div class="capa-topo">
      <span class="nome-publicacao">{{NOME_REVISTA}}</span>
      <span class="edicao-numero">Edição {{EDICAO}}</span>
    </div>

    <div class="capa-imagem-principal">
      <img src="assets/capa-principal.jpg" alt="Imagem de capa" />
    </div>

    <div class="capa-chamadas">
      <h1 class="manchete-principal">{{MANCHETE_PRINCIPAL}}</h1>
      <ul class="chamadas-secundarias">
        <li>{{CHAMADA_1}}</li>
        <li>{{CHAMADA_2}}</li>
        <li>{{CHAMADA_3}}</li>
      </ul>
    </div>

    <div class="capa-rodape">
      <span>{{MES_ANO}}</span>
      <span>{{PRECO}}</span>
    </div>
  </div>
</body>
</html>
```

#### `editorial.html` — Editorial

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{NOME_REVISTA}} — Editorial</title>
  <link rel="stylesheet" href="css/estilos.css">
</head>
<body class="pagina-interna">
  <header class="cabecalho-pagina">
    <span class="nome-publicacao">{{NOME_REVISTA}}</span>
    <span class="secao-atual">Editorial</span>
    <span class="numero-pagina">03</span>
  </header>

  <article class="editorial-container">
    <h1 class="titulo-editorial">Palavra do Editor</h1>
    <div class="foto-editor">
      <img src="assets/foto-editor.jpg" alt="Foto do editor" />
      <p class="legenda-foto">{{NOME_EDITOR}}, Editor-chefe</p>
    </div>
    <div class="texto-editorial">
      <p>{{PARAGRAFO_1}}</p>
      <p>{{PARAGRAFO_2}}</p>
      <p>{{PARAGRAFO_3}}</p>
    </div>
    <div class="assinatura-editor">
      <p>{{NOME_EDITOR}}</p>
      <p><em>Editor-chefe, {{NOME_REVISTA}}</em></p>
    </div>
  </article>

  <nav class="navegacao-paginas">
    <a href="index.html">← Sumário</a>
    <a href="artigo.html">Próxima →</a>
  </nav>

  <footer class="rodape-pagina">
    <p>{{NOME_REVISTA}} — Edição {{EDICAO}} — {{MES_ANO}}</p>
  </footer>
</body>
</html>
```

#### `artigo.html` — Artigo

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{TITULO_ARTIGO}} — {{NOME_REVISTA}}</title>
  <link rel="stylesheet" href="css/estilos.css">
</head>
<body class="pagina-interna">
  <header class="cabecalho-pagina">
    <span class="nome-publicacao">{{NOME_REVISTA}}</span>
    <span class="secao-atual">{{SECAO}}</span>
    <span class="numero-pagina">05</span>
  </header>

  <article class="artigo-container">
    <div class="artigo-cabecalho">
      <span class="categoria-artigo">{{CATEGORIA}}</span>
      <h1 class="titulo-artigo">{{TITULO_ARTIGO}}</h1>
      <p class="subtitulo-artigo">{{SUBTITULO}}</p>
      <div class="meta-artigo">
        <span class="autor">Por {{AUTOR}}</span>
        <span class="data-publicacao">{{DATA}}</span>
        <span class="tempo-leitura">{{TEMPO_LEITURA}} min de leitura</span>
      </div>
    </div>

    <div class="artigo-imagem-destaque">
      <img src="assets/artigo-imagem.jpg" alt="{{LEGENDA_IMAGEM}}" />
      <p class="legenda">{{LEGENDA_IMAGEM}}</p>
    </div>

    <div class="artigo-corpo">
      <p class="chapeu">{{CHAPEU}}</p>
      <p>{{PARAGRAFO_1}}</p>
      <blockquote class="destaque">
        <p>{{CITACAO_DESTAQUE}}</p>
      </blockquote>
      <p>{{PARAGRAFO_2}}</p>
      <p>{{PARAGRAFO_3}}</p>
    </div>

    <div class="artigo-tags">
      <span class="tag">{{TAG_1}}</span>
      <span class="tag">{{TAG_2}}</span>
    </div>
  </article>

  <nav class="navegacao-paginas">
    <a href="editorial.html">← Anterior</a>
    <a href="contracapa.html">Próxima →</a>
  </nav>

  <footer class="rodape-pagina">
    <p>{{NOME_REVISTA}} — Edição {{EDICAO}} — {{MES_ANO}}</p>
  </footer>
</body>
</html>
```

#### `contracapa.html` — Contracapa

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{NOME_REVISTA}} — Contracapa</title>
  <link rel="stylesheet" href="css/estilos.css">
</head>
<body class="pagina-contracapa">
  <div class="contracapa-container">
    <div class="proxima-edicao">
      <h2>Na próxima edição</h2>
      <ul>
        <li>{{PROXIMO_1}}</li>
        <li>{{PROXIMO_2}}</li>
        <li>{{PROXIMO_3}}</li>
      </ul>
    </div>

    <div class="expediente">
      <h3>Expediente</h3>
      <p><strong>Publicação:</strong> {{NOME_REVISTA}}</p>
      <p><strong>Editor-chefe:</strong> {{NOME_EDITOR}}</p>
      <p><strong>Redação:</strong> {{ENDERECO_REDACAO}}</p>
      <p><strong>Contato:</strong> {{EMAIL_CONTATO}}</p>
      <p><strong>Site:</strong> {{SITE}}</p>
    </div>

    <div class="redes-sociais">
      <h3>Siga-nos</h3>
      <p>{{REDES_SOCIAIS}}</p>
    </div>

    <div class="contracapa-logo">
      <span>{{NOME_REVISTA}}</span>
      <p>{{SLOGAN}}</p>
    </div>
  </div>
</body>
</html>
```

#### `css/estilos.css` — Estilos Principais

```css
/* ===== RESET & BASE ===== */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --cor-primaria: #1a3a5c;
  --cor-secundaria: #e8a020;
  --cor-texto: #222222;
  --cor-texto-claro: #666666;
  --cor-fundo: #ffffff;
  --cor-fundo-alt: #f5f5f5;
  --fonte-titulo: 'Georgia', serif;
  --fonte-corpo: 'Arial', sans-serif;
  --largura-max: 900px;
  --espacamento: 2rem;
}

body {
  font-family: var(--fonte-corpo);
  color: var(--cor-texto);
  background: var(--cor-fundo);
  line-height: 1.6;
}

/* ===== CABEÇALHO ===== */
.cabecalho-revista, .cabecalho-pagina {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem var(--espacamento);
  background: var(--cor-primaria);
  color: white;
}

.nome-publicacao { font-family: var(--fonte-titulo); font-size: 1.5rem; font-weight: bold; }
.secao-atual { font-size: 0.9rem; text-transform: uppercase; letter-spacing: 0.1em; }
.numero-pagina { font-size: 0.9rem; opacity: 0.8; }

/* ===== SUMÁRIO ===== */
.pagina-sumario main { max-width: var(--largura-max); margin: 0 auto; padding: var(--espacamento); }
.pagina-sumario h1 { font-family: var(--fonte-titulo); font-size: 2rem; color: var(--cor-primaria); margin-bottom: 2rem; border-bottom: 3px solid var(--cor-secundaria); padding-bottom: 0.5rem; }

.lista-sumario { display: flex; flex-direction: column; gap: 1rem; }

.item-sumario {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  padding: 1.5rem;
  background: var(--cor-fundo-alt);
  border-left: 4px solid var(--cor-secundaria);
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s;
}
.item-sumario:hover { transform: translateX(4px); }
.numero-pagina { font-size: 2rem; font-weight: bold; color: var(--cor-secundaria); min-width: 3rem; }
.info-item h2 { font-family: var(--fonte-titulo); color: var(--cor-primaria); }
.info-item p { color: var(--cor-texto-claro); font-size: 0.9rem; margin-top: 0.25rem; }

/* ===== CAPA ===== */
.pagina-capa { background: var(--cor-primaria); color: white; min-height: 100vh; }

.capa-container { display: grid; grid-template-rows: auto 1fr auto auto; min-height: 100vh; }

.capa-topo {
  display: flex;
  justify-content: space-between;
  padding: 1.5rem var(--espacamento);
  background: rgba(0,0,0,0.3);
}
.nome-publicacao { font-family: var(--fonte-titulo); font-size: 2rem; font-weight: bold; }
.edicao-numero { font-size: 0.9rem; align-self: center; }

.capa-imagem-principal img { width: 100%; height: 60vh; object-fit: cover; display: block; }

.capa-chamadas {
  padding: var(--espacamento);
  background: rgba(0,0,0,0.7);
}
.manchete-principal { font-family: var(--fonte-titulo); font-size: 2.5rem; margin-bottom: 1rem; }
.chamadas-secundarias { list-style: none; display: flex; flex-direction: column; gap: 0.5rem; }
.chamadas-secundarias li::before { content: "▶ "; color: var(--cor-secundaria); }

.capa-rodape {
  display: flex;
  justify-content: space-between;
  padding: 1rem var(--espacamento);
  background: var(--cor-secundaria);
  color: var(--cor-primaria);
  font-weight: bold;
}

/* ===== PÁGINAS INTERNAS ===== */
.pagina-interna article { max-width: var(--largura-max); margin: 0 auto; padding: var(--espacamento); }

/* Editorial */
.editorial-container { display: grid; grid-template-columns: 1fr 2fr; gap: 2rem; align-items: start; }
.titulo-editorial { font-family: var(--fonte-titulo); font-size: 2rem; color: var(--cor-primaria); grid-column: 1 / -1; margin-bottom: 1rem; }
.foto-editor img { width: 100%; border-radius: 8px; }
.legenda-foto { text-align: center; font-size: 0.85rem; color: var(--cor-texto-claro); margin-top: 0.5rem; }
.texto-editorial p { margin-bottom: 1rem; }
.assinatura-editor { margin-top: 2rem; font-style: italic; border-top: 2px solid var(--cor-secundaria); padding-top: 1rem; }

/* Artigo */
.artigo-cabecalho { margin-bottom: 2rem; }
.categoria-artigo { background: var(--cor-secundaria); color: var(--cor-primaria); padding: 0.25rem 0.75rem; font-size: 0.8rem; font-weight: bold; text-transform: uppercase; border-radius: 2px; }
.titulo-artigo { font-family: var(--fonte-titulo); font-size: 2.5rem; color: var(--cor-primaria); margin: 1rem 0 0.5rem; }
.subtitulo-artigo { font-size: 1.2rem; color: var(--cor-texto-claro); margin-bottom: 1rem; }
.meta-artigo { display: flex; gap: 1.5rem; font-size: 0.85rem; color: var(--cor-texto-claro); flex-wrap: wrap; }

.artigo-imagem-destaque { margin: 2rem 0; }
.artigo-imagem-destaque img { width: 100%; height: 400px; object-fit: cover; border-radius: 4px; }
.legenda { font-size: 0.85rem; color: var(--cor-texto-claro); margin-top: 0.5rem; font-style: italic; }

.artigo-corpo p { margin-bottom: 1.5rem; font-size: 1.1rem; }
.chapeu { font-size: 1.3rem; font-weight: bold; color: var(--cor-primaria); border-left: 4px solid var(--cor-secundaria); padding-left: 1rem; }

blockquote.destaque {
  background: var(--cor-fundo-alt);
  border-left: 6px solid var(--cor-secundaria);
  padding: 1.5rem;
  margin: 2rem 0;
  font-family: var(--fonte-titulo);
  font-size: 1.3rem;
  font-style: italic;
  color: var(--cor-primaria);
}

.artigo-tags { display: flex; gap: 0.5rem; flex-wrap: wrap; margin-top: 2rem; }
.tag { background: var(--cor-fundo-alt); padding: 0.25rem 0.75rem; border-radius: 20px; font-size: 0.85rem; color: var(--cor-texto-claro); }

/* ===== CONTRACAPA ===== */
.pagina-contracapa {
  background: var(--cor-primaria);
  color: white;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.contracapa-container { max-width: var(--largura-max); padding: var(--espacamento); display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; }
.contracapa-container h2, .contracapa-container h3 { color: var(--cor-secundaria); margin-bottom: 1rem; }
.contracapa-container ul { list-style: none; }
.contracapa-container li { padding: 0.5rem 0; border-bottom: 1px solid rgba(255,255,255,0.1); }
.contracapa-container p { margin-bottom: 0.5rem; font-size: 0.9rem; }
.contracapa-logo { grid-column: 1 / -1; text-align: center; margin-top: 2rem; border-top: 2px solid var(--cor-secundaria); padding-top: 2rem; }
.contracapa-logo span { font-family: var(--fonte-titulo); font-size: 3rem; font-weight: bold; }
.contracapa-logo p { color: var(--cor-secundaria); font-style: italic; margin-top: 0.5rem; }

/* ===== NAVEGAÇÃO ===== */
.navegacao-paginas {
  display: flex;
  justify-content: space-between;
  max-width: var(--largura-max);
  margin: 2rem auto;
  padding: 0 var(--espacamento);
}
.navegacao-paginas a {
  background: var(--cor-primaria);
  color: white;
  padding: 0.75rem 1.5rem;
  text-decoration: none;
  border-radius: 4px;
  transition: background 0.2s;
}
.navegacao-paginas a:hover { background: var(--cor-secundaria); color: var(--cor-primaria); }

/* ===== RODAPÉ ===== */
.rodape-revista, .rodape-pagina {
  text-align: center;
  padding: 1rem;
  background: var(--cor-fundo-alt);
  color: var(--cor-texto-claro);
  font-size: 0.85rem;
}

/* ===== RESPONSIVO ===== */
@media (max-width: 600px) {
  .editorial-container { grid-template-columns: 1fr; }
  .contracapa-container { grid-template-columns: 1fr; }
  .manchete-principal { font-size: 1.8rem; }
  .titulo-artigo { font-size: 1.8rem; }
}
```

#### `css/print.css` — Estilos para Impressão/PDF

```css
@media print {
  .navegacao-paginas, .cabecalho-revista { display: none; }
  body { font-size: 12pt; color: black; background: white; }
  a { text-decoration: none; color: black; }
  .artigo-imagem-destaque img { max-height: 300px; }
  page { size: A4; margin: 2cm; }
}
```

### 4. Confirmar criação

Após gerar todos os arquivos, informe ao usuário:
- Lista de arquivos criados
- Como personalizar as cores (variáveis CSS em `estilos.css`)
- Como substituir os placeholders `{{NOME}}` pelo conteúdo real
- Sugestão de próximos passos (adicionar imagens em `assets/`, publicar via GitHub Pages, etc.)
