# Brand Book — Sistema **COLO**
## Projeto Fertilidade · v0.3

> **O que este documento é:** o brand book do projeto. Define **apenas design** — cor, tipografia, grid, forma, movimento, imagem, componentes e aplicação. Não define mensagem, tom de voz nem copy.
>
> **O que ele não é:** um guia de comunicação. Direcionamento de mensagem foi movido para [VOZ-E-MENSAGEM.md](VOZ-E-MENSAGEM.md).
>
> **Dependência:** marca, nome e profissional responsável ainda não estão definidos (D2, D3 do [README.md](README.md)). O sistema foi construído como **camada de tokens marca-agnóstica** — funciona sob qualquer nome que for decidido, e nada aqui precisa ser refeito quando a marca sair.
>
> **Validação:** paleta testada em contraste — **26/26 pares aprovados em WCAG 2.1 AA**, a maioria em AAA. Números na seção 3.4.
>
> **Documento irmão:** [PSICOLOGIA-DAS-CORES.md](PSICOLOGIA-DAS-CORES.md) reúne a evidência revisada por pares por trás das escolhas cromáticas. Leia antes de propor qualquer mudança de paleta.

---

## 1. O conceito

**Colo** — a palavra em português para o gesto de receber e sustentar alguém.

O nome existe porque descreve a decisão que o sistema toma em toda bifurcação visual: **acolher antes de afirmar**. Onde a categoria escolhe entre parecer clínica (fria, institucional, azul) ou parecer delicada (rosa, floral, infantilizada), este sistema escolhe um terceiro lugar: **quente, adulto e organizado**.

### 1.1 A regra de decisão visual
Toda escolha de design passa por uma pergunta:

> **A peça comunica atenção, cuidado e método — ou comunica o desfecho?**

Comunicar o desfecho (bebê, positivo, barriga) é o erro estrutural da categoria. Comunicar atenção e método é o território deste sistema. Quando houver dúvida entre duas opções visuais, vence a que parece *examinada com cuidado*.

### 1.2 Por que este conceito e não outro
| Razão | Consequência de design |
|---|---|
| É maternal **sem ser sobre bebê** | Sobrevive ao dado de que 36,3% do público já perdeu uma gestação — a prova de fogo de toda decisão visual aqui |
| Traduz "ser recebida com atenção" | Justifica o dispositivo assinatura (§7.3) e o componente `Ficha` (§8.2) |
| É marca-agnóstico | Funciona sob qualquer nome que D3 decidir |

---

## 2. Princípios de design

Cinco regras. Quando houver discussão visual, elas decidem.

### 2.1 **Ela, não o desfecho** ⚠️ *inegociável*
Nenhum bebê, ultrassom, barriga de grávida, teste positivo, sapatinho, berço ou família com filhos. Em nenhum canal. Detalhamento em §6.

### 2.2 **Calor com método**
A credibilidade vem de parecer **organizado**, não de parecer hospital. Grid honesto, hierarquia tipográfica clara, dados apresentados com rigor. O calor vem da cor; o rigor vem da estrutura.

### 2.3 **Contido, não dramático**
Nem euforia (confete, explosão, saturação alta) nem melodrama (escuro, dessaturado, sombrio). O registro visual é sóbrio e quente — ver a matriz de luminosidade × saturação em §3.1.

### 2.4 **Mobile é o projeto, não a adaptação**
Público 97,8% Brasil, Android de entrada, 4G instável. Toda decisão é testada primeiro em **360px** de largura.

### 2.5 **O sistema tem que sobreviver à degradação**
Parte da operação acontece em canais que destroem design — WhatsApp, e-mail simples, impressão em preto e branco. O sistema precisa funcionar reduzido a **estrutura + uma imagem quadrada**. Se uma peça só existe com o CSS aplicado, ela não serve.

---

## 3. Cor

### 3.1 A lógica da paleta
Quatro famílias, cada uma com um trabalho:

- **PAPEL** — neutro quente. É o fundo de tudo. Não é branco: branco puro sinaliza instituição clínica.
- **VERDE** — botânico profundo. A cor institucional. Entrega credibilidade sem frieza.
- **TERRACOTA** — barro quente. A cor da **ação**. Só ela chama para clicar.
- **ACOLHIMENTO** — argila rosada clara. Superfície das seções afetivas. Nunca ação.

Mais **DOURADO**, raro, para marcação e destaque.

E uma ausência deliberada: **nenhum rosa**.

> ⚠️ **Registro honesto:** a exclusão do rosa é decisão de **posicionamento tomada contra a evidência psicológica** — rosa é a cor mais fortemente associada a amor e afeto na literatura (68,75% dos estudos). Trocamos o sinal mais direto de afeto por diferenciação numa categoria saturada de rosa pastel. A lacuna é coberta pela família `acolhe-*`. Fundamentação em [PSICOLOGIA-DAS-CORES.md](PSICOLOGIA-DAS-CORES.md).

**A matriz que governa a paleta** — luminosidade e saturação pesam mais que matiz na resposta emocional:

| | Claro | Escuro |
|---|---|---|
| **Saturado** | positivo, ação → `terra-500` | poder, autoridade → `verde-700` |
| **Dessaturado** | calmo, acolhedor → `papel-*`, `acolhe-*` | apagado, triste → **nenhuma cor do sistema** |

O quadrante inferior direito é onde paletas sóbrias perdem autoridade. O sistema não usa nada lá.

### 3.2 Tokens

```css
:root {
  /* PAPEL — fundos e superfícies */
  --papel-0:    #FDFBF7;  /* fundo base da página */
  --papel-50:   #F7F2EA;  /* superfície elevada / seção alternada */
  --papel-100:  #EFE7DA;  /* card sobre fundo */
  --papel-200:  #E2D6C4;  /* superfície pressionada */
  --linha:      #DCCFBC;  /* divisor decorativo (não-interativo) */

  /* TINTA — texto */
  --tinta-900:  #241E18;  /* texto principal */
  --tinta-700:  #4A3F35;  /* texto secundário */
  --tinta-500:  #756658;  /* texto de apoio / legenda */
  --tinta-400:  #7C736B;  /* borda de input, ícone, estado desabilitado */

  /* VERDE — marca e credibilidade */
  --verde-900:  #12291F;  /* bloco escuro / rodapé */
  --verde-800:  #1B3A2C;
  --verde-700:  #24503C;  /* ★ cor institucional primária */
  --verde-600:  #2F6A4E;
  --verde-400:  #7AAF94;  /* texto claro sobre verde escuro */
  --verde-200:  #A9C9B8;
  --verde-100:  #D6E5DC;  /* badge */
  --verde-50:   #EAF1EC;  /* bloco de destaque suave */

  /* TERRACOTA — ação */
  --terra-700:  #8C3D24;  /* pressionado */
  --terra-600:  #A34328;  /* hover */
  --terra-500:  #B54F30;  /* ★ ação primária */
  --terra-400:  #C97A5C;  /* decorativo */
  --terra-300:  #E1A78F;  /* acento sobre fundo escuro */
  --terra-100:  #F5DED3;
  --terra-50:   #FBF0EA;  /* fundo de aviso suave */

  /* ACOLHIMENTO — superfície quente e afetiva */
  --acolhe-50:  #FDF3F1;  /* fundo de seção */
  --acolhe-100: #FAE5E0;  /* card */
  --acolhe-200: #F4D3CC;  /* borda, destaque suave */

  /* DOURADO — marcação e destaque, com parcimônia */
  --dourado-700: #8F6A1F; /* único que passa AA como texto */
  --dourado-500: #C89B3C; /* preenchimento do grifo */
  --dourado-100: #F5E7C4;

  /* SEMÂNTICOS */
  --sucesso:    #2F6A4E;
  --atencao:    #8F6A1F;
  --erro:       #A3302A;
  --foco:       #24503C;
}
```

### 3.3 Regras de uso

| Regra | Detalhe |
|---|---|
| **Terracota é só ação** | Se não é clicável, não é terracota. Uma tela = **uma ação terracota**. A cor perde poder no instante em que decora |
| **Verde é a instituição** | Cabeçalho, rodapé, blocos de autoridade, selos, gráficos. Nunca na ação primária |
| **Papel é o padrão** | Todo fundo começa em `--papel-0`. Branco puro (`#FFF`) só existe *dentro* de botões e sobre blocos verdes |
| **Acolhimento é superfície, nunca ação** | Fundo das seções afetivas. Croma baixo demais para competir com a terracota |
| **Nenhum neutro quente médio-escuro como superfície grande** | Papel só existe claro (L\* acima de 80). Escurecer o bege "para dar contraste" cruza para o marrom, a mais negativa das cores quentes na literatura |
| **Dourado é raro** | Só `--dourado-700` pode ser texto. Mais de uma marcação por tela anula o efeito |
| **Proporção alvo** | ~70% papel · ~20% verde · ~8% terracota · ~2% dourado. `acolhe-*` substitui o papel pontualmente, não soma |

### 3.4 Contraste validado (WCAG 2.1)

Calculado, não estimado. **26/26 aprovados.**

| Uso | Par | Ratio | Nível |
|---|---|---|---|
| Texto principal | `tinta-900` / `papel-0` | **15.95** | AAA |
| Texto secundário | `tinta-700` / `papel-0` | **9.89** | AAA |
| Texto de apoio | `tinta-500` / `papel-0` | **5.35** | AA |
| **Ação primária** | `branco` / `terra-500` | **5.09** | AA |
| Ação hover | `branco` / `terra-600` | **6.19** | AAA |
| Ação pressionada | `branco` / `terra-700` | **7.48** | AAA |
| Botão institucional | `branco` / `verde-700` | **9.18** | AAA |
| Bloco escuro | `papel-0` / `verde-900` | **14.91** | AAA |
| Link / título verde | `verde-700` / `papel-0` | **8.88** | AAA |
| Texto em bloco claro | `verde-800` / `verde-50` | **10.84** | AAA |
| Texto claro s/ escuro | `verde-400` / `verde-900` | **6.15** | AAA |
| Acento s/ escuro | `terra-300` / `verde-900` | **7.43** | AAA |
| Aviso suave | `terra-700` / `terra-50` | **6.68** | AAA |
| Texto em acolhimento | `tinta-900` / `acolhe-50` | **15.12** | AAA |
| Texto em card afetivo | `tinta-900` / `acolhe-100` | **13.62** | AAA |
| Título sobre acolhimento | `verde-800` / `acolhe-100` | **10.28** | AAA |
| Dourado como texto | `dourado-700` / `papel-0` | **4.78** | AA |
| Texto sobre dourado | `tinta-900` / `dourado-500` | **6.44** | AAA |
| Erro | `branco` / `erro` | **6.97** | AAA |
| Borda de input / ícone | `tinta-400` / `papel-0` | **4.49** | AA *(alvo não-texto: 3.0)* |

> ⚠️ Três tokens foram corrigidos durante a validação: a terracota original (`#C25A38`) reprovava com 4.36, o cinza de borda (`#8A7868`) com 2.68 e o dourado (`#C89B3C`) com 3.55. **Qualquer ajuste de cor exige rodar o teste de novo.** O script trava a build no CI.

---

## 4. Tipografia

### 4.1 A dupla

**Display — `Fraunces`** *(Google Fonts, variável)*
Serifa de tela com eixos `wght`, `opsz` e `SOFT`. Editorial e quente. O mercado brasileiro de saúde é monocultura de sans geométrica — uma serifa quente diferencia estruturalmente.
`SOFT` em 30–50 arredonda os terminais e retira o peso institucional. `WONK` permanece em 0.

**Texto e UI — `Inter`** *(Google Fonts, variável)*
X-height alto, aberturas abertas, legível a 16px em Android de entrada. Cobertura completa de Latin Extended — todos os diacríticos do português desenhados, não sintetizados.

**Alternativa conservadora:** `Lora` no lugar da Fraunces. Troca de um token, zero refatoração.

```css
--fonte-display: 'Fraunces', 'Lora', Georgia, serif;
--fonte-texto:   'Inter', -apple-system, 'Segoe UI', Roboto, sans-serif;
```

### 4.2 Escala fluida (mobile-first, base 16px)

| Token | Tamanho | Face / peso |
|---|---|---|
| `--t-display` | `clamp(2.25rem, 7vw, 4rem)` | Fraunces 600 · `SOFT` 40 |
| `--t-h1` | `clamp(1.875rem, 5.5vw, 3rem)` | Fraunces 600 · `SOFT` 40 |
| `--t-h2` | `clamp(1.5rem, 4vw, 2.25rem)` | Fraunces 600 · `SOFT` 30 |
| `--t-h3` | `clamp(1.25rem, 3vw, 1.5rem)` | Fraunces 500 |
| `--t-lead` | `clamp(1.125rem, 2.5vw, 1.375rem)` | Inter 400 |
| `--t-corpo` | `1rem` | Inter 400 · **nunca abaixo de 16px** |
| `--t-apoio` | `0.875rem` | Inter 400 |
| `--t-micro` | `0.75rem` | Inter 400 |

### 4.3 Regras
- Corpo em **16px mínimo**, sempre
- Medida de linha: **60–72 caracteres** no desktop
- `line-height`: 1.6 no corpo, 1.15 nos displays
- **Nunca centralizar bloco longo de texto.** Título pode ser centralizado; texto corrido, não
- `text-wrap: balance` nos títulos
- Números tabulares (`font-variant-numeric: tabular-nums`) sempre que dígitos se alinham em coluna
- Caixa alta apenas em labels curtos, com `letter-spacing` de 0.1–0.15em

---

## 5. Grid, espaço e forma

```css
/* ESPAÇO — grade de 8, com meio-passo de 4 */
--e-1: 4px;   --e-2: 8px;   --e-3: 12px;  --e-4: 16px;
--e-5: 24px;  --e-6: 32px;  --e-7: 48px;  --e-8: 64px;  --e-9: 96px;

/* RAIO */
--r-sm:   8px;    /* input, tag */
--r-md:   12px;   /* card */
--r-lg:   20px;   /* bloco, modal */
--r-full: 999px;  /* ação e badge — a pílula é a forma do botão */

/* ELEVAÇÃO — sombra na cor da tinta, nunca preto puro */
--sombra-1: 0 1px 2px rgba(36,30,24,.06), 0 1px 3px rgba(36,30,24,.04);
--sombra-2: 0 4px 12px rgba(36,30,24,.07);
--sombra-3: 0 12px 32px rgba(36,30,24,.10);

/* LARGURAS */
--l-texto:    680px;   /* coluna de leitura */
--l-conteudo: 1120px;
```

**Por que sombra colorida:** preto puro sobre papel quente produz um cinza sujo. Todas as sombras herdam a tinta.

**Layout:** grupos irmãos são espaçados com `gap` de flex ou grid, nunca com margens por elemento. Conteúdo largo — tabela, código, diagrama — recebe `overflow-x: auto` no próprio container.

**Toque:** alvo mínimo de **48×48px**. Ação primária ocupa largura total no mobile.

---

## 6. Fotografia e imagem

### 6.1 Proibido ⚠️
Bebê · recém-nascido · ultrassom · barriga de grávida · teste de gravidez · sapatinho, chupeta, mamadeira · berço ou quarto de bebê · casal com filhos · mãos formando coração sobre barriga · cegonha · jaleco, estetoscópio, laboratório · pessoa chorando no escuro · **rosa em qualquer tom**.

*Jaleco e laboratório reconstroem o registro clínico do qual o sistema se diferencia. Pessoa chorando é exploração de dor. Rosa é o clichê da categoria. E imagem de bebê é o erro estrutural descrito em §1.1.*

### 6.2 Permitido
- **Ela** — 30 a 45 anos, brasileira, diversa em tom de pele e tipo de corpo, luz natural, expressão serena ou pensativa. Nunca eufórica, nunca destruída
- **Mãos** — preparando alimento, segurando xícara, escrevendo. Cuidado sem rosto
- **Alimento real** — verduras, chá, tempero, cozinha doméstica brasileira
- **Cotidiano** — luz de janela, mesa, caderno, copo d'água
- **A profissional em trabalho** — lendo exame, escrevendo

### 6.3 Tratamento
Temperatura quente (+5 a +10), saturação levemente reduzida, sem filtro estourado, sem viradas de cor. Devem parecer **fotografadas, não licenciadas de banco**.

### 6.4 Enquadramento
Preferência por planos médios e detalhes. Evitar plano aberto vazio e retrato posado frontal de banco de imagem. Espaço negativo generoso à esquerda ou à direita, para receber tipografia sem sobreposição.

---

## 7. Linguagem gráfica

### 7.1 Formas orgânicas
Formas abstratas de contorno curvo e irregular, sobrepostas com transparência. Servem como fundo e respiro.
- Nunca representam anatomia
- Nunca competem com o texto — opacidade máxima de 20% quando atrás de conteúdo
- Derivam da família verde ou terracota, nunca em cor cheia

### 7.2 Divisores
Linha de 1px em `--linha` para separação decorativa. Divisor orgânico (curva suave) apenas em transição entre blocos de fundo diferente, no máximo uma vez por página.

### 7.3 O grifo — dispositivo assinatura
Marcação em `--dourado-500` a **35% de opacidade**, cobrindo aproximadamente os **44% inferiores** da altura da linha, com terminais irregulares — como marcação feita à mão.

```css
.grifo{
  background: linear-gradient(to top,
    rgba(200,155,60,.42) 0%, rgba(200,155,60,.42) 44%, transparent 44%);
  padding: 0 2px;
  border-radius: 1px;
}
```

É o elemento mais característico do sistema. Traduz visualmente a ideia de **atenção individual** — algo que foi lido e marcado.

**Regra:** uma marcação por bloco de texto. Duas anulam a primeira.

### 7.4 Ícones
Traço de 1.5px, terminais arredondados, grade de 24px, sem preenchimento. Cor herda do texto. Nunca ícone colorido, nunca emoji como elemento de interface.

---

## 8. Componentes

### 8.1 Biblioteca base
`Botão` (primário terracota · secundário verde contornado · terciário texto) · `Campo` · `Seletor de opção` · `Card` · `Bloco de destaque` · `Acordeão` · `Barra de progresso` · `Badge` · `Tabela` · `Divisor`.

### 8.2 Componentes próprios

| Componente | Função de design |
|---|---|
| **`Ficha`** | Bloco de exibição de dados que devolve ao usuário as informações que ele mesmo forneceu. Fundo `acolhe-*` ou `verde-50`, lista de definição em duas colunas |
| **`Grifo`** | O dispositivo de §7.3 |
| **`DiagramaDoMétodo`** | Representação visual única e repetida do método, aplicada de forma idêntica em todos os canais. Consistência vale mais que variedade |
| **`SeloDeCredencial`** | Bloco de identificação profissional — avatar, nome, registro. Pílula contornada em `verde-200` |

### 8.3 Contratos de componente
Restrições estruturais da biblioteca, aplicadas em tempo de build:

- **`AntesDepois` não existe** — o componente é deliberadamente ausente. Não há como montar a peça com peças aprovadas
- **`Depoimento` exige `autorizacaoId`** — sem a prop, não renderiza
- **`NúmeroDeProva` é token único** — vem de um só arquivo, impedindo divergência entre canais

*Regras de conteúdo e de claim não pertencem a este documento. Ver [README.md](README.md) §9.*

---

## 9. Aplicação por formato

Especificações de layout. Sem direcionamento de mensagem.

| Formato | Dimensão | Especificação visual |
|---|---|---|
| **Anúncio estático** | 1080×1350 (4:5) e 1080×1080 | Fundo `papel-0` ou `verde-900`. Display em Fraunces ocupando 40–55% da altura. Margem de segurança de 64px. Uma única forma orgânica, canto superior direito |
| **Anúncio em vídeo** | 1080×1920 (9:16) | Legenda queimada em Inter 600, caixa `verde-900` a 85%, terço inferior, margem de segurança de 240px no topo e 320px na base |
| **Quiz** | 360px base | Uma pergunta por tela. Barra de progresso fixa no topo. Alvos de 56px, coluna única. Ação primária em largura total, fixa na base |
| **Página longa** | `--l-texto` 680px | Coluna única centralizada. Blocos `verde-*` alternando com `papel-*` para segmentar. Ação persistente após o primeiro terço. Peso alvo **< 400 KB** na primeira tela |
| **Card quadrado** | 1080×1080 | Formato de degradação (§2.5). Só `Ficha`, `DiagramaDoMétodo` ou `SeloDeCredencial`. Tipografia mínima de 32px |
| **Documento impresso / PDF** | A4 | Papel como fundo, Fraunces nos títulos, Inter no corpo a 11pt, cabeçalho em `verde-700`, `SeloDeCredencial` na capa. Precisa funcionar em impressão monocromática |

---

## 10. Acessibilidade e performance

**Acessibilidade** — WCAG 2.1 AA como piso, validado em §3.4.
- Foco visível: 2px sólido em `--foco`, offset de 2px
- Nunca comunicar estado apenas por cor
- Alvo de toque mínimo de 48px
- `prefers-reduced-motion: reduce` desliga toda transição
- Labels reais, nunca placeholder como label
- HTML semântico, hierarquia de headings sem saltos

**Movimento**
```css
--tempo-rapido: 150ms;  /* hover, foco */
--tempo-padrao: 250ms;  /* entrada de elemento */
--tempo-lento:  400ms;  /* transição de seção */
--curva: cubic-bezier(.22,.61,.36,1);
```
Entrada por **fade + 8px de subida**. Sem escala, bounce ou rotação. Nada pisca, pulsa ou treme. Sem contador regressivo animado.

**Performance** — Android de entrada em 4G instável:
- Fontes variáveis em `woff2`, subset **latin + latin-ext**, `font-display: swap`, `preload` apenas nos dois pesos da primeira tela
- Imagens em AVIF com fallback WebP, `loading="lazy"` abaixo da dobra, dimensões explícitas para evitar layout shift
- Orçamento: **< 400 KB** e **LCP < 2,5s** em 4G simulado
- Sem biblioteca de animação — as transições acima são CSS puro

---

## 11. O que ainda não está definido

| Item | Depende de |
|---|---|
| Logotipo, símbolo, assinatura visual | **D3** (marca e domínio) |
| Retrato e identidade da profissional | **D2** (quem assina) |
| Densidade da UI de produto | **D1** (modelo do produto) |
| Modo escuro | Sem prioridade até o funil validar |

**Já produzível sem nenhuma decisão pendente:** anúncio, quiz, página longa, card quadrado e documento impresso. A camada de tokens não muda quando a marca sair.

---

## 12. Implementação

1. `tokens.css` com §3, §4 e §5 — **antes de qualquer componente**
2. Teste de contraste no CI, travando a build abaixo de AA
3. Componentes base, mobile-first, com os contratos de §8.3
4. Kit de criativo para o time — Figma ou Canva, o que a equipe realmente usa

---

**Histórico**
- `v0.3` — 28/08/2026 — convertido em brand book. Removido todo direcionamento de copy, tom de voz e mensagem (movido para [VOZ-E-MENSAGEM.md](VOZ-E-MENSAGEM.md)). Adicionadas especificações de formato, ícones, enquadramento fotográfico e divisores.
- `v0.2` — 28/08/2026 — correções vindas de [PSICOLOGIA-DAS-CORES.md](PSICOLOGIA-DAS-CORES.md): família `acolhe-*`, `tinta-400` fora da zona do marrom, regra do rosa reenquadrada. 26/26 pares em AA.
- `v0.1` — 28/08/2026 — proposta inicial. 23/23 pares em AA.
