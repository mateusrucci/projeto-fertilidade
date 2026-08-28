# Projeto Fertilidade — Diretrizes Iniciais

> **O que é este documento:** o ponto de entrada do projeto. Se você acabou de chegar, leia as seções 0 a 5 (≈10 min) e você já consegue produzir alguma coisa útil. As seções 6 a 13 são referência de consulta.
>
> **Status:** `v0.1 — fundacional`. Escrito a partir do material existente em 27/08/2026. Nada aqui está validado em produção ainda.
>
> **Regra de leitura dos números:** todo percentual neste documento é calculado **sobre quem respondeu àquela pergunta específica**, nunca sobre o total da base. A base tem respostas completas e parciais misturadas. Sempre que citar um número, cite junto o `n`.

---

## Arquivos deste repositório

| Arquivo | O que é |
|---|---|
| **`README.md`** | Este documento. Contexto do projeto, público, produto, riscos e decisões em aberto. **Comece aqui.** |
| **`DESIGN-SYSTEM.md`** | Brand book. Cor, tipografia, grid, fotografia, linguagem gráfica, componentes e formatos. Só design |
| **`PSICOLOGIA-DAS-CORES.md`** | Evidência revisada por pares por trás das escolhas cromáticas. Leia antes de propor mudança de paleta |
| **`VOZ-E-MENSAGEM.md`** | Direcionamento de tom e mensagem, extraído do brand book. Consultivo |
| **`brandbook.html`** | Versão visual do brand book — abra no navegador para ver paleta, tipografia e componentes renderizados |

> ⚠️ **A base bruta de leads não vive aqui e não deve viver.** `respostas_typebot.xlsx` contém nome, telefone, e-mail e dados de saúde — dado pessoal sensível pela LGPD (art. 5º, II · art. 11). O `.gitignore` bloqueia `.xlsx`, `.csv` e afins justamente para impedir isso. Trabalhe sempre com o agregado anônimo. Ver risco R5.

---

## 0. Leia isto primeiro

**O projeto:** vamos entrar no nicho de **fertilidade feminina**, com um produto cujo foco é ajudar mulheres que estão tentando engravidar a conseguirem o resultado — posicionado como **caminho natural (nutrição + protocolo individual)**, em oposição ao caminho medicamentoso/invasivo (indutores de ovulação, FIV).

**Por que este nicho:** já existe uma base real de **19.325 respostas** de formulário de captação, coletadas entre jul/2023 e mai/2025, com dados de diagnóstico, tempo de tentativa, idade, renda, tratamentos já feitos e campos abertos com a dor escrita pela própria pessoa. Não estamos partindo do zero — estamos partindo de dados de demanda já comprovada.

**O que já sabemos que funciona (hipótese forte):** um mecanismo de venda construído sobre **"3 vilões ocultos"** (inflamação, metais pesados, falta de estratégia nutricional por fase do ciclo) + atendimento consultivo por WhatsApp com quebra de objeção estruturada.

**O que NÃO está definido ainda:** qual produto vamos vender, por quanto, com que marca e assinado por qual profissional. Há **duas ofertas incompatíveis** nos documentos de origem. Ver seção 5 e seção 10.

**Onde você provavelmente vai atuar primeiro:** tráfego pago (Meta) → formulário/quiz de qualificação → WhatsApp → venda consultiva. Esse é o funil que já rodou.

---

## 1. Fontes deste documento

Tudo abaixo foi extraído de material fornecido pelo Mateus. Nada foi inventado. Onde há inferência, está marcado como inferência.

| # | Fonte | O que traz | Confiabilidade |
|---|---|---|---|
| F1 | `respostas_typebot.xlsx` (7,3 MB, 19.325 linhas, 45 colunas) | Base bruta de respostas do formulário de captação | **Alta** — dado primário |
| F2 | `relatorio_analise_typebot.xlsx` | Análise agregada da F1 (diagnósticos, abortos, tratamentos, renda, dores) | **Alta**, com uma ressalva (ver 1.1) |
| F3 | Google Doc — *Perguntas que podem surgir* | Banco de FAQ / quebra de objeção da consultoria | Alta (material operacional real) |
| F4 | Google Doc — *Blocos 01–10 + Quebra de objeções* | Script completo de atendimento WhatsApp da "Poly / Instituto Be Mater", incluindo áudios por diagnóstico e pitch do PFI | Alta (material operacional real) |
| F5 | Google Doc — *Carta de Vendas (Jon Benson)* | Roteiro de VSL do "Método Mamãe Positiva", assinado por "Carla" | **Média** — é rascunho, contém placeholders e personagem aparentemente fictícia |

### 1.1 Ressalva importante sobre F2
Os cabeçalhos exportados do Typebot são `blockId`, não o texto da pergunta. Os rótulos semânticos ("renda", "investimento", "tempo de tentativa") foram **inferidos pela distribuição das respostas**. Duas colunas em particular — a que o relatório chama de *Renda* e a que chama de *Renda investimento* — precisam ser conferidas contra o fluxo original do Typebot antes de virarem base de precificação. **Ação:** abrir o Typebot e mapear `blockId → pergunta`. É uma tarefa de 30 minutos que destrava toda a leitura financeira da base.

---

## 2. O que já existe (inventário de ativos)

| Ativo | Estado | Onde |
|---|---|---|
| Base de 19.325 leads qualificados (nome, WhatsApp, e-mail, diagnóstico, dor) | Existe, **não tratada sob LGPD** — ver seção 9 | `respostas_typebot.xlsx` |
| Formulário/quiz de qualificação (Typebot) | Rodou até mai/2025, retomado em jul/2026 com volume baixo | Typebot (acesso a confirmar) |
| Script de atendimento WhatsApp em 10 blocos | Completo e pronto para uso | F4 |
| Banco de áudios por diagnóstico (9 variações) | Roteirizado, gravação a confirmar | F4 |
| Banco de quebra de objeção (6 objeções + 10 FAQs) | Completo | F3, F4 |
| Roteiro de VSL | Rascunho, precisa de revisão de claims | F5 |
| Produto/entrega | **Não definido** | — |
| Marca, domínio, identidade | **Não definido** | — |
| Profissional responsável técnico (nutricionista com CRN) | **Não definido** | — |
| Estrutura de checkout, pixel, tracking | **Não definido** | — |

---

## 3. O público (ICP)

### 3.1 Retrato em uma frase
Mulher brasileira de **30 a 42 anos**, tentando engravidar há mais de um ano, que **já foi a médico e saiu sem resposta**, que **ainda não fez nenhum tratamento formal**, com renda familiar até R$ 5.000, e para quem engravidar é a prioridade número um da vida — não uma entre várias.

### 3.2 Segmentos por diagnóstico *(n = 14.860)*

| Diagnóstico declarado | % | Leitura estratégica |
|---|---|---|
| **Normal, sem diagnósticos** | **32,2%** | O maior segmento. É a mulher "sem causa": foi ao médico, não achou nada, e continua sem engravidar. É para ela que o mecanismo dos "3 vilões ocultos" foi feito. **Público primário.** |
| **SOP / ovário policístico** | **30,5%** | Segundo maior. Público mais jovem (48% tem menos de 30 anos; 82% até 35). Alto volume, ciclo de decisão mais longo, menos urgência de idade. |
| Endometriose / Adenomiose | 13,0% | 60% tem 35+. Dor física real além da dor emocional. Segmento de altíssimo engajamento. |
| Infertilidade sem causa aparente | 12,4% | 65% tem 35+. Já rodou a investigação médica inteira. É o público mais frustrado e mais pronto para comprar. |
| Fator masculino (esperma) | 5,0% | Objeção estrutural: "o problema não sou eu". Exige abordagem de casal. |
| Falência ovariana | 4,2% | Urgência máxima, mas expectativa precisa ser gerenciada com muito cuidado (ver seção 9). |
| Trombofilia | 2,1% | 76% tem 35+. Quase sempre vem junto de histórico de aborto. |
| Azoospermia / vasectomia do parceiro | 0,6% | **Público a excluir** — não há entrega possível. |

### 3.3 Idade *(n = 9.550)*
- Menos de 30 anos — **24,4%**
- 30 a 35 anos — **29,4%**
- 35 a 42 anos — **29,9%**
- Mais de 40/42 anos — **16,3%**

**→ 46% da base tem 35 anos ou mais.** Idade é o segundo tema mais citado espontaneamente nos campos abertos. O "relógio biológico" é o motor de urgência mais forte que temos.

### 3.4 Tempo de tentativa *(n = 8.227)*
- Mais de 5 anos — **24,2%**
- Entre 2 e 5 anos — **20,1%**
- Entre 1 e 2 anos — **22,1%**
- 6 meses a 1 ano — **16,1%**
- 0 a 6 meses — **17,5%**

**→ 44,3% está tentando há mais de 2 anos.** Este é um público que já gastou dinheiro, já chorou muito e já foi decepcionado. Copy de "solução mágica rápida" queima. Copy de "ninguém olhou pro seu caso de verdade" acerta.

### 3.5 Histórico de aborto *(n = 11.471)*
- Nenhum aborto — 63,7%
- **Pelo menos um aborto — 36,3%** (um: 23,6% · dois: 8,0% · três: 2,8% · mais de três: 1,9%)

**→ Mais de 1 em cada 3 já perdeu uma gestação.** Isso muda o tom de tudo. Não é só "não consigo engravidar", é luto não elaborado. Qualquer criativo ou copy que trate isso com leviandade destrói a marca.

### 3.6 Nível de tratamento já realizado *(n = 11.232)*
- **Não fiz nenhum desses — 64,3%**
- Remédios indutores de ovulação — 21,6%
- Acompanhamento nutricional — 8,7%
- Fertilização in vitro — 4,2%
- Inseminação artificial — 1,2%

**→ Este é o achado mais valioso da base.** Dois terços do público **nunca fez tratamento nenhum**. Não estamos disputando com a FIV — estamos disputando com a **inércia** e com o "vai acontecer quando Deus quiser". O concorrente real é *não fazer nada*.

Consequência direta: **apenas 8,7% já fez acompanhamento nutricional.** A categoria "nutrição para fertilidade" é praticamente virgem para este público. Isso é bom (mercado aberto) e ruim (precisamos educar antes de vender).

### 3.7 Suplementação atual *(n = 15.144, campo aberto)*
- **54,7% respondeu "não" / "nenhum"** — mais da metade não toma nada
- Ácido fólico — 15,3% · Ômega 3 — 13,4% · Vitamina D — 11,2% · Coenzima Q10 — 7,3% · Vitamina B12 — 3,9% · Magnésio — 3,6% · Inositol — 1,7%

**→ Confirma 3.6:** é um público sub-tratado, não um público saturado de protocolos. E abre uma linha de receita óbvia (suplementação própria) — ver seção 11.

### 3.8 Urgência declarada *(n = 10.358, escala 0–10)*
- Nota **10 — 61,0%** · notas 8 a 10 — **79,3%** · nota 1 — 7,3%

E a urgência sobe com o tempo de tentativa: 64,4% dá nota 10 entre quem tenta há menos de 6 meses, contra **72,4% entre quem tenta há mais de 5 anos**.

**→ Urgência não é um problema neste nicho. Confiança é.** Não precisamos criar desejo; precisamos provar que somos diferentes dos que já falharam com ela.

### 3.9 Poder de decisão *(n = 700 — base pequena, tratar como direcional)*
- "Posso tomar essa decisão sozinha" — **64,9%**
- "Preciso conversar com meu marido" — **35,1%**

**→ Um terço das vendas tem um segundo decisor invisível.** O script já prevê essa objeção (F4). O material de venda precisa ter uma peça pensada para ela mostrar ao parceiro.

### 3.10 Renda e capacidade de investimento
Renda declarada *(n = 4.957)*: **48,7% até R$ 4.000**; 33,5% até R$ 3.000.
Faixa de investimento/gasto *(n = 8.552)*: **40,2% até R$ 3.000**; 28,5% de R$ 3.000 a R$ 5.000; ~13% acima de R$ 8.000.

⚠️ **Estes dois campos precisam ser validados contra o Typebot antes de fundamentar preço** (ver 1.1). A hipótese mais provável é que o segundo campo seja *"quanto você já gastou tentando engravidar"* — o que, se confirmado, é um argumento de venda devastador: **quase 70% já gastou até R$ 5.000 sem resultado.**

### 3.11 Geografia *(n = 8.169 com telefone)*
- Brasil — **97,8%** · Portugal — 1,1% · EUA — 0,3% · demais — <1%

**→ Operação Brasil.** Portugal existe como cauda relevante (diáspora), mas não justifica campanha própria agora.

### 3.12 A dor, nas palavras delas *(campo aberto, n = 13.857)*

Temas mais citados espontaneamente:

| Tema | % |
|---|---|
| **"Não sei o que tenho" / causa desconhecida** | **24,6%** |
| Ovulação / ciclo irregular | 13,9% |
| Idade / tempo passando | 12,3% |
| SOP | 11,0% |
| Endometriose | 7,5% |
| Peso / obesidade | 6,2% |
| Fator masculino | 5,2% |
| Ansiedade / emocional | 4,6% |
| Alimentação | 4,6% |

**→ A dor nº 1 não é um diagnóstico. É a ausência de um.** "Não sei o que tenho" é a resposta mais frequente da base inteira. **Qualquer headline que prometa uma resposta ("descubra o que ninguém investigou no seu caso") ataca a dor mais universal do público.**

Verbatins reais (anonimizados, úteis para copy):

> "Eu já usei letrozol, clomid, já fiz inseminação intrauterina. E nada ajudou. Eu já vou fazer 38 anos mês que vem."

> "Porque é meu sonho engravidar e todo mês quando a menstruação vem é muito difícil controlar a ansiedade e a tristeza."

> "Gostaria muito de entender meu corpo, as necessidades dele e o porquê não consigo engravidar mesmo não tendo nenhum diagnóstico."

> "Porque preciso encontrar uma solução natural para a infertilidade antes de buscar meios artificiais."

> "A dor de não realizar um sonho por ter esperado o 'momento certo'."

> "Pq não sei mais onde procurar respostas, diagnósticos, alguma luz para o meu sonho."

---

## 4. Como a base se comportou no tempo

| Período | Volume | Observação |
|---|---|---|
| jul/2023 – dez/2023 | 4.252 | Início da operação |
| jan/2024 – dez/2024 | 10.636 | **Pico**: mar/2024 (2.191) e abr/2024 (2.050). Ago/2024 sem coleta |
| jan/2025 – mai/2025 | 4.385 | Queda progressiva |
| jun/2025 – mai/2026 | ~0 | **Operação parada por ~12 meses** |
| jun/2026 – ago/2026 | 50 | Retomada recente, volume de teste |

**Taxa de conclusão do formulário: 46,6%** (8.999 completas de 19.325). Mais da metade abandona no meio.

Onde as pessoas caem (taxa de preenchimento por etapa):
- Nome — 88,4%
- Suplementos que usa — 78,4%
- Diagnóstico — 76,9%
- Campo aberto da dor — 71,7%
- E-mail — 60,0%
- Histórico de aborto — 59,4%
- **WhatsApp — 42,3%** ← maior gargalo

**→ Menos da metade entrega o WhatsApp, que é justamente o canal onde a venda acontece.** Otimizar a posição e o enquadramento do pedido de WhatsApp no fluxo é provavelmente a maior alavanca isolada de resultado do funil hoje.

**Implicação de dado:** a base é **histórica** (mediana em 2024). Leads de 2023–2024 estão frios e muitas já resolveram (engravidaram ou desistiram). Reativar essa base é uma tese válida, mas exige mensagem própria de reativação — não é o mesmo tratamento de um lead novo. E exige checagem de LGPD (seção 9).

---

## 5. O produto e a oferta

⚠️ **ESTE É O PONTO MAIS CRÍTICO DO PROJETO.** Os documentos de origem descrevem **dois produtos diferentes, com duas marcas, duas assinaturas profissionais e dois preços incompatíveis.** Isso precisa ser resolvido antes de qualquer produção.

### Versão A — "PFI · Protocolo de Fertilidade Individual" *(fonte F4)*
- **Marca:** Instituto Be Mater · **Assinatura:** Poly, nutricionista fundadora
- **Modelo:** serviço de **acompanhamento individual 1:1**, 60 dias, sem videochamada
- **Entrega:** 2 formulários (dia 0 e dia 30) → 2 prescrições individualizadas · plano alimentar · solicitação e leitura de exames · suplementação · suporte por WhatsApp
- **Bônus:** e-book de receitas sem glúten/lactose · e-book de sobremesas por fase do ciclo · plataforma com aulas (psicóloga, fisioterapeuta, aromaterapia)
- **Preço:** ancoragem 12× R$ 99,70 → oferta 12× R$ 49,70 (**≈ R$ 596 total**)
- **Prova declarada:** 6 anos de experiência, centenas de pacientes, 16 países

### Versão B — "Método Mamãe Positiva" *(fonte F5)*
- **Marca:** Método Mamãe Positiva · **Assinatura:** Carla, nutricionista desde 2010
- **Modelo:** **infoproduto/curso** — protocolo em aulas gravadas, sem 1:1
- **Entrega:** protocolo anti-inflamatório individual · detox de metais pesados · plano nutricional por fase do ciclo · suplementação · listas, chás e receitas · aulas em vídeo
- **Bônus:** Guia de Receitas Fertilizadoras · Programa de Detox de Metais Pesados · Meditações de Conexão · Super Bônus "Mapa da Fertilidade"
- **Preço:** ancoragem R$ 10.000 → oferta **R$ 2.000**, garantia de 30 dias
- **Prova declarada:** 9.523 mulheres, 27 países, história pessoal de 13 anos e 8 meses de tentativas, 2 FIVs, positivo aos 43 anos

### As incompatibilidades, explicitamente

| Dimensão | Versão A | Versão B | Conflito |
|---|---|---|---|
| Preço | ~R$ 596 | R$ 2.000 | **3,4×** |
| Modelo | Serviço 1:1 (escala limitada por atendimento) | Digital (escala ilimitada) | Modelos de negócio opostos |
| Marca | Instituto Be Mater | Método Mamãe Positiva | — |
| Profissional | "Poly" | "Carla" | — |
| Prova social | centenas de pacientes / 16 países | 9.523 mulheres / 27 países | **Números se contradizem** |

Há ainda uma inconsistência **dentro** da Versão A: o Bloco 09 do script oferece "um tratamento que fica menos de R$ 40 por mês", enquanto o Bloco 10 fecha em 12× R$ 49,70. Precisa ser alinhado antes de ir para o atendimento.

**Nota sobre a Versão B:** o documento tem marcas claras de rascunho (uma pergunta do redator ficou no corpo do texto, e o nome do marido na história pessoal é "Mateus"). Trate F5 como **estrutura de VSL a ser reescrita**, não como copy aprovada. Ver seção 9 antes de reaproveitar qualquer claim dela.

### Recomendação (a decidir com o Mateus)
Os dados apontam para **Versão A como porta de entrada**: 64,3% do público nunca fez tratamento nenhum, quase metade tem renda até R$ 4.000, e a dor nº 1 é "ninguém olhou pro meu caso" — o que um produto 1:1 resolve e um curso gravado não. A Versão B funciona melhor como **produto de escala numa fase 2**, depois que a entrega 1:1 estiver validada e documentada.

---

## 6. O mecanismo (a tese central da venda)

Este é o núcleo intelectual do produto e aparece de forma consistente em F4 e F5. **É o que diferencia a oferta.** Toda copy deve orbitar isto.

**Premissa:** o corpo não engravida porque está desorganizado, não porque está quebrado. Antes de forçar (hormônio, indutor, FIV), é preciso **preparar**.

**Os 3 vilões ocultos:**

1. **Inflamação** — Sintomas de entrada: inchaço, gases, queda de cabelo, acne, cansaço, ansiedade, intestino irregular. Impacta absorção de nutrientes, produção hormonal, maturação folicular e implantação do embrião.
   *Diferencial argumentativo:* **inflamação é individual.** Tirar glúten e lactose não resolve — cada mulher tem alimentos-gatilho próprios. É isto que justifica um protocolo individual em vez de uma dieta genérica.

2. **Acúmulo de metais pesados** — Argumento de que interfere na ovulação, na maturação folicular e na qualidade do esperma do parceiro.
   *Diferencial argumentativo:* trocar cosméticos só evita **entrar** mais; é preciso **retirar** o que já está acumulado.
   ⚠️ **Este vilão carrega os claims mais arriscados do projeto. Leia a seção 9 antes de escrever qualquer coisa sobre ele.**

3. **Falta de estratégia nutricional por fase do ciclo** — Folicular, ovulatória, lútea têm necessidades distintas.
   *Exemplo âncora usado no script:* cúrcuma é boa como antioxidante na fase folicular, mas pode atrapalhar na fase de implantação. **O que ajuda numa fase pode atrapalhar na outra.**

**Por que este mecanismo funciona:** ele dá uma **resposta** ("é isto que você tem") aos 24,6% que dizem "não sei o que tenho", **sem contradizer o médico** (não nega o diagnóstico, diz que a investigação foi incompleta) e **sem prometer substituir a medicina** (posiciona-se como preparo, não como cura).

---

## 7. Funil e jornada

```
Meta Ads
   ↓
Formulário / quiz de qualificação (Typebot)
   ↓  conclusão 46,6% · WhatsApp capturado em 42,3%
WhatsApp — atendimento consultivo humano (script de 10 blocos)
   ↓
Venda (PFI ou Método) → onboarding por formulário → prescrição
```

### O script de WhatsApp, resumido *(F4 — leia o original antes de operar)*

| Bloco | Função | Mecânica |
|---|---|---|
| 01 | Boas-vindas | Áudio da profissional se apresentando + pergunta aberta sobre o caso |
| 02 | Espelhamento | Envia o **áudio específico do diagnóstico dela** (9 variações: aborto, idade, ISCA, endometriose, SOP, baixa reserva, FIV, indutor, "comecei agora") |
| 03 | Identificação coletiva | "Todo dia recebo centenas de mulheres…" + pergunta se ela se reconhece |
| 04 | Compromisso | "Engravidar é realmente prioridade pra você hoje?" — micro-sim antes do pitch |
| 05–06 | Vilão 1: inflamação | Sintomas → consequência → "dieta anti-inflamatória genérica não funciona" |
| 07 | Vilão 2: metais pesados | Detox vs. só evitar contato |
| 08 | Vilão 3: fases do ciclo | Exemplo da cúrcuma |
| 09 | Prova | Prints/áudios/vídeos de caso semelhante + pergunta de fechamento condicional |
| 10 | Oferta | Apresentação do PFI + ancoragem + desconto + bônus |

**Padrão a preservar:** cada bloco termina em **pergunta**. O script não é um monólogo — é uma sequência de micro-compromissos. Isso é o que sustenta a taxa de resposta.

### Objeções mapeadas *(F3 + F4)*
Dinheiro · "Preciso pensar" · "Preciso ver se tenho limite" · "Tá caro" · "Preciso ver com meu cônjuge" · "Não sei se vou conseguir implementar" · "Não vou ter consulta?" · "Você tem caso igual ao meu?" · "Consigo emagrecer/ganhar massa?" · "Parcela sem juros?" · "É caro o que vou precisar usar?" · "Vou precisar fazer exame?" · "Qual a minha garantia?" · "O que você acha desses exames?"

As respostas prontas estão em F3 e F4. **Use-as como base, mas revise à luz da seção 9** — algumas prometem mais do que se pode prometer.

---

## 8. Diretrizes de copy e mensagem

**Tom:** empatia primeiro, autoridade depois. Este público foi tratado como número por médicos — o diferencial percebido é *ser vista*. Nunca escreva de cima para baixo.

**Faça:**
- Ataque a dor nº 1: **"ninguém investigou o seu caso de verdade"** (24,6% da base)
- Use o inimigo comum: o sistema que trata mulher como número, não o médico individual
- Reposicione, não negue: *"infertilidade sem causa aparente é infertilidade sem investigação suficiente"* — esta linha é excelente e já está pronta em F4
- Segmente o criativo por diagnóstico (SOP, endometriose, aborto, idade) — os 9 áudios já provam que a segmentação funciona no atendimento
- Trate perda gestacional com gravidade: 36,3% da base já passou por isso
- Ancore urgência na **biologia** ("cada ciclo importa"), não em escassez artificial de vaga

**Não faça:**
- Prometer gravidez, prazo para gravidez ou taxa de sucesso (ver seção 9)
- Tratar FIV/medicina reprodutiva como charlatanismo — parte relevante do público já fez ou vai fazer, e o posicionamento correto é **preparo complementar**, não substituição
- Usar tom de "solução mágica": 44,3% tenta há mais de 2 anos e já ouviu tudo
- Prometer emagrecimento ou ganho de massa como benefício principal (aparece em F3 — é resposta reativa a objeção, não promessa de vitrine)

---

## 9. Riscos e compliance

**Esta seção não é burocracia. Cada item abaixo é capaz de derrubar a operação inteira.** Nenhuma copy vai ao ar sem passar por aqui.

### 🔴 R1 — Claims falsos sobre metais pesados e síndromes genéticas
F4 e F5 afirmam que o excesso de metais pesados está relacionado a **autismo, Síndrome de Down, Síndrome de Turner e Síndrome de Edwards**. Down, Turner e Edwards são **aneuploidias cromossômicas** — alterações no número de cromossomos. **Não há evidência científica de que sejam causadas por metais pesados.**
**Consequência:** publicidade enganosa (CDC art. 37), risco de ação civil, reprovação e banimento em plataformas de anúncio, e — o pior — culpabilização de mães.
**Ação obrigatória:** remover integralmente estes claims. O vilão "metais pesados" pode ser mantido com fundamentação real (qualidade oocitária, estresse oxidativo), mas **sem associação a síndromes cromossômicas**.

### 🔴 R2 — Promessa de resultado
"Engravidar em 60 dias", "fertilidade de uma mulher de 20 anos", "funciona independente do seu problema" são promessas de resultado em saúde.
**Consequência:** o Código de Ética do Nutricionista (CFN Res. 599/2018) veda garantia de resultado; somam-se CDC art. 37 e CONAR. Expõe o profissional a processo no conselho.
**Ação obrigatória:** substituir promessa de resultado por promessa de **processo e preparo** ("preparar seu corpo", "tratar o que não foi investigado", "aumentar suas chances"). Reescrever a abertura da VSL.

### 🔴 R3 — Depoimentos possivelmente fictícios
F5 traz "Mariana", "Patrícia", "Ana, 38, São Paulo", "Bruna, 40, Curitiba" e o número "9.523 mulheres em 27 países", incompatível com o "centenas de pacientes em 16 países" de F4.
**Consequência:** depoimento fabricado em saúde é publicidade enganosa e crime de consumo, além de banimento em plataforma.
**Ação obrigatória:** só usar depoimento **real, com autorização de uso por escrito**. Definir o número de prova social verdadeiro e usar **um só**, em todos os canais.

### 🟠 R4 — Políticas de anúncio de saúde (Meta)
A Meta proíbe anúncios que afirmem ou insinuem conhecer a condição de saúde da pessoa ("Você que tem endometriose…", "Cansada de testes negativos?"). Fertilidade cai em categoria sensível.
**Ação:** escrever criativos na **terceira pessoa ou coletiva** ("muitas mulheres descobrem que…"), nunca acusatória na segunda pessoa. Ter conta de backup e BM estruturada antes de escalar.

### 🟠 R5 — LGPD sobre a base existente
`respostas_typebot.xlsx` contém nome, telefone, e-mail **e dados de saúde** — que a LGPD classifica como **dado pessoal sensível** (art. 5º, II), com regime de tratamento próprio (art. 11).
**Ações:**
- Não circular o arquivo bruto. Trabalhar sempre com o agregado (`relatorio_analise_typebot.xlsx`), que já é anônimo
- Confirmar qual consentimento foi coletado em 2023–2025 e se ele cobre o uso atual (reativação/remarketing)
- Definir política de retenção, canal de opt-out e responsável pelos dados antes de qualquer disparo em massa
- Nunca commitar a base bruta em repositório

### 🟠 R6 — Escopo profissional e responsável técnico
O produto envolve **solicitação e interpretação de exames** e **prescrição de suplementação** — atos privativos de profissional habilitado e regulamentado (CFN Res. 656/2020 para suplementação, entre outras).
**Ação:** definir o profissional responsável, com registro ativo, **antes do lançamento**. Sem RT definido, não há produto — há risco.

### 🟡 R7 — Segmentos sem entrega possível
Azoospermia/vasectomia do parceiro (0,6%) e alguns casos de falência ovariana não têm entrega realista pelo protocolo.
**Ação:** criar critério de **desqualificação no formulário** e roteiro de encaminhamento respeitoso. Vender para quem não pode ser atendido gera reembolso, reclamação e dano reputacional em um público que conversa entre si.

> **Nota:** os enquadramentos legais acima estão citados como orientação prática de risco e devem ser confirmados com assessoria jurídica antes do lançamento. O ponto que não depende de advogado: **os claims de R1, R2 e R3 são factualmente insustentáveis e precisam sair.**

---

## 10. Decisões em aberto

Nada de produção pesada avança antes destas respostas. Ordenadas por bloqueio.

| # | Decisão | Por que bloqueia | Dono |
|---|---|---|---|
| D1 | **Qual produto vamos vender?** Versão A (1:1, ~R$ 596), Versão B (digital, R$ 2.000) ou um híbrido | Define preço, entrega, funil, copy, estrutura de time — tudo | Mateus |
| D2 | **Quem é o profissional que assina?** Nome real, CRN ativo, história verdadeira | Sem isso não há prova social legítima nem produto legal | Mateus |
| D3 | **Qual a marca e o domínio?** | Trava identidade, LP, e-mail, redes | Mateus |
| D4 | **Qual o número de prova social verdadeiro?** | Precisa ser um só, consistente em todos os canais | Mateus |
| D5 | **Mapear `blockId → pergunta` no Typebot** | Destrava a leitura correta de renda × capacidade de investimento (ver 1.1) | Ops |
| D6 | **A base de 19.325 leads pode ser reativada sob o consentimento coletado?** | Define se temos um ativo de receita imediata ou um passivo de LGPD | Jurídico |
| D7 | **Vamos vender suplemento próprio?** 54,7% não toma nada | Muda a economia da operação e o cálculo de LTV | Mateus |
| D8 | **Ticket e forma de pagamento** — parcelamento sem juros? (F3 hoje diz que só há com juros) | Objeção nº 1 do público de renda até R$ 4.000 | Mateus |

---

## 11. Próximos passos sugeridos

**Fase 0 — Fundação (destravar D1–D6)**
1. Reunião de decisão sobre produto, marca e profissional responsável
2. Mapear o Typebot e corrigir o dicionário de campos
3. Passar F3, F4 e F5 pelo filtro da seção 9 — versão limpa dos claims
4. Consulta jurídica: LGPD da base + revisão dos claims

**Fase 1 — Reconstruir o funil que já existe**
5. Reescrever o quiz de qualificação, movendo a captura de WhatsApp (hoje é o gargalo: 42,3%) e incluindo critério de desqualificação (R7)
6. Reescrever o script de WhatsApp com os claims corrigidos, mantendo a estrutura de 10 blocos e os 9 áudios segmentados
7. Gravar os áudios com o profissional real
8. Estruturar checkout, pixel/CAPI e tracking

**Fase 2 — Tráfego**
9. Criativos segmentados pelos 4 grandes segmentos: sem diagnóstico (32,2%), SOP (30,5%), endometriose (13,0%), sem causa aparente (12,4%)
10. Ângulo principal a testar: **"não é que você não pode engravidar — é que ninguém investigou o seu caso de verdade"**
11. Meta de aprendizado da fase: CPL, taxa de conclusão do quiz, taxa de captura de WhatsApp, taxa de resposta no bloco 01

**Fase 3 — Escala**
12. Reativação da base histórica (dependente de D6)
13. VSL reescrita para escala fria
14. Avaliar produto digital (Versão B) como esteira, e suplementação própria (D7)

---

## 12. Glossário

| Termo | Significado |
|---|---|
| **PFI** | Protocolo de Fertilidade Individual — o produto 1:1 da Versão A |
| **SOP** | Síndrome dos Ovários Policísticos |
| **ISCA** | Infertilidade Sem Causa Aparente |
| **FIV** | Fertilização in vitro |
| **IIU** | Inseminação intrauterina |
| **Indutor de ovulação** | Medicamento (clomifeno/letrozol) para forçar ovulação |
| **Reserva ovariana** | Quantidade estimada de folículos restantes |
| **Fases do ciclo** | Folicular · ovulatória · lútea |
| **Os 3 vilões** | Inflamação · metais pesados · falta de estratégia nutricional por fase — o mecanismo central da oferta |
| **Positivo** | Como o público chama o teste de gravidez positivo. **Use esse vocabulário — é o deles** |

---

## 13. Como manter este documento

- Este arquivo é a **fonte de verdade de contexto** do projeto. Quando uma decisão da seção 10 for tomada, ela sobe para a seção correspondente e sai da lista de pendências.
- Números novos entram **sempre com o `n`** e a data da coleta.
- Claims de saúde novos passam pela seção 9 **antes** de entrar em qualquer peça.
- Se você mudou produto, preço ou posicionamento e não atualizou este arquivo, o próximo a entrar no projeto vai produzir a coisa errada.

**Histórico**
- `v0.1` — 27/08/2026 — versão inicial, a partir de F1–F5.
