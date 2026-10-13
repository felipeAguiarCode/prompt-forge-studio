# 🎛️ Prompt Forge Studio

<p>
  <a href="https://felipeaguiarcode.github.io/prompt-forge-studio/"><img src="https://img.shields.io/badge/Abrir_o_app-Prompt_Forge_Studio-3b63fb?style=for-the-badge&logo=githubpages&logoColor=white" alt="Abrir o Prompt Forge Studio no GitHub Pages"></a>
</p>

Editor de prompts em um único arquivo HTML. Interface escura inspirada nos aplicativos criativos da Adobe e no sistema Spectrum: explorador de arquivos, abas, composição central e biblioteca lateral. O laranja identifica a marca e o documento ativo; o azul marca seleção, foco e a ação principal.

## 🚀 Como abrir

Use a versão online em **[felipeaguiarcode.github.io/prompt-forge-studio](https://felipeaguiarcode.github.io/prompt-forge-studio/)**, publicada pelo GitHub Pages a partir da branch `main`, ou abra `index.html` no navegador. O aplicativo não exige instalação, dependências, login, chave de API ou conexão com serviços externos.

Também pode ser publicado como um site estático. Para servir localmente, execute na pasta do projeto:

```bash
python -m http.server 8080
```

Depois abra `http://localhost:8080` no navegador. Usar sempre o mesmo endereço ajuda a manter o mesmo contexto de armazenamento. O acesso ao armazenamento e à área de transferência depende das permissões do navegador; o editor avisa quando não consegue salvar e oferece cópia manual quando necessário.

## ✨ Tela de abertura

Ao abrir, o app mostra uma tela de abertura no estilo dos programas da Adobe: um cartão com a arte generativa **Forja** (um anel incandescente com faíscas, desenhado em SVG pelo próprio app), o ícone **Pm**, o nome, a versão e mensagens de carregamento com os números reais do workspace, como blocos, templates e técnicas. Ela dura cerca de 2 segundos; um clique ou qualquer tecla a dispensa na hora. **Ajuda › Sobre o Prompt Forge Studio** mostra o mesmo cartão, que fica aberto até você clicar ou pressionar Esc.

## 🧩 Compor com blocos

Arraste um item da biblioteca para a posição desejada na composição. Clicar em um item também o adiciona ao final do arquivo. Arraste a alça de um card para reordenar; no menu do card existem ações equivalentes de mover para cima e para baixo.

Clique no cabeçalho para expandir ou recolher. Na barra do editor, dois ícones de setas expandem ou recolhem **todos os blocos** de uma vez; cada um fica desativado quando não há o que mudar, e os mesmos comandos estão no menu **Exibir** e na busca de comandos. Escreva no campo do bloco e use a pequena barra de formatação para inserir negrito, itálico, listas ou variáveis. O menu também permite renomear, duplicar e excluir.

A biblioteca oferece 94 tipos de bloco em 13 seções recolhíveis, como no painel Propriedades dos apps Adobe:

| Seção | Blocos |
| --- | --- |
| Fundamentos | Papel, Objetivo, Público-alvo, Critérios de sucesso, Bloco livre |
| Níveis de instrução | System prompt, Developer prompt, User prompt |
| Contexto e conhecimento | Contexto, Dados de entrada, Material de referência, Glossário, Premissas, Regras de negócio, Histórico, Ambiente técnico, Entrada multimodal |
| Raciocínio e método | Instruções, Raciocínio passo a passo, Plano de ação, Perguntas de esclarecimento, Critérios de decisão, Autorrevisão |
| Técnicas avançadas | Decomposição, Pergunta de recuo, Múltiplos caminhos, Árvore de pensamentos, Painel de especialistas, Crítica e reescrita, Rubrica de avaliação, Ciclo ReAct, Etapa encadeada, Delimitadores, Meta-prompt, Rodada de refinamento |
| Controle e segurança | Guardrails, Restrições, Escopo, Fontes e citações, Incerteza, Privacidade, Plano B |
| Estilo e linguagem | Tom e voz, Idioma, Voz da marca, Vocabulário, Extensão |
| Saída e formato | Formato de saída, Saída em JSON, Tabela, Modelo de resposta, Checklist, Exemplos, Contraexemplos, Variações |
| Agentes e ferramentas | Ferramentas, Fluxo do agente, Definição de função, Memória e estado, Critério de parada, Escalonamento humano |
| Vendas e copy | Persona de compra, Oferta, Proposta de valor, Prova social, Objeções, Chamada para ação, Fórmula de copy, Ganchos e headlines, Qualificação de lead |
| Criativo e visual | Direção de arte, Assunto e cena, Composição, Iluminação, Paleta de cores, Estilo visual, Prompt negativo, Formato e proporção |
| Photo edit | Câmera e lente, Exposição, Foco e profundidade, Cor e Picture Style, Óptica e textura, Revelação RAW, Retoque, Preservar do original |
| Tarefas prontas | Editing prompt, Resumo, Tradução, Extração de dados, Classificação, Comparação, Brainstorm, Revisão de código |

Clique no título de uma seção para abri-la ou recolhê-la; o botão ao lado da busca expande ou recolhe todas. A busca procura no nome, na descrição e na seção de cada bloco e abre as seções com resultado. Os cinco últimos blocos adicionados aparecem em **Usados recentemente**. Seções abertas e recentes ficam salvos neste navegador, fora do backup do workspace.

Cada seção tem uma cor, repetida no ícone dos cards da composição. Títulos digitados no Markdown são reconhecidos pelo nome exato do bloco e por sinônimos comuns, como `## Tom`, `## Resposta em JSON` ou `## ReAct`. **Restrições** reúne limites técnicos e operacionais, como "não instalar dependências"; **Guardrails** fica com segurança, privacidade e proibições.

## 🔗 Visão em nodes

O botão **Nodes** na barra do editor (ou **Ctrl + Alt + 4**) mostra o arquivo como um canvas no estilo do n8n. Cada bloco vira uma caixa, e os fios mostram a ordem em que os blocos entram no prompt. A corrente começa na pílula verde **Início** e termina em **Prompt final**, que mostra quantos blocos estão no fluxo e a estimativa de tokens, e tem os botões Copiar e Prévia.

- **Encadear:** arraste a bolinha de saída, à direita de uma caixa, e solte sobre outra caixa. A caixa de destino passa a vir logo depois.
  - Soltar sobre **Início** põe a caixa no começo do fluxo.
  - Soltar sobre **Prompt final** torna a caixa a última.
  - Soltar no vazio abre o menu de tipos e cria o próximo bloco ali mesmo, já ligado.
- **Caixas soltas:** só entra no prompt final o que está ligado a partir de Início.
  - **Para tirar uma caixa do fluxo:** use a tesoura que aparece ao passar o mouse sobre um fio, puxe a ponta do fio para fora da bolinha de entrada ou pressione **D** com a caixa selecionada.
  - **Como fica:** a caixa continua no arquivo, com borda tracejada. Na visão Blocos, ela aparece apagada, com o selo "fora do fluxo".
  - **Para religar:** arraste um fio até ela, solte a caixa sobre um fio ou use **Ligar ao fluxo** no menu da caixa.
- **Prévia, cópia e exportação seguem o fluxo:** a prévia, **Copiar prompt** e **Exportar prompt final** ignoram as caixas soltas. O Markdown, **Copiar Markdown original** e **Exportar Markdown** mantêm o arquivo completo.
- **Variáveis** viram nós laranja, com o valor editável, ligados à porta de baixo de cada bloco que as usa. Arraste a bolinha de uma variável até outro bloco para inserir `{{variavel}}` no fim do texto dele.
- **Caixas:**
  - edite o texto direto na caixa, com a mesma barra de negrito, itálico, lista e variável;
  - arraste o cabeçalho para mover e a alça do canto para redimensionar;
  - dê duplo clique no título para renomear;
  - a seta recolhe a caixa, e os ícones de expandir e recolher todos também valem aqui.
- **Biblioteca:**
  - clicar num item acrescenta o bloco ao fim do fluxo;
  - arrastar para cima de um fio insere o bloco naquele ponto;
  - arrastar para o vazio cria uma caixa solta;
  - o botão **+ Bloco** acrescenta depois da caixa selecionada;
  - o clique direito no canvas cria uma caixa solta no ponto clicado.
- **Navegar:**
  - arraste o fundo para mover o canvas e use a roda do mouse para rolar;
  - **Ctrl + roda** (ou pinça, no toque) aproxima e afasta;
  - no canto inferior esquerdo ficam Ajustar à tela (**1**), o zoom, 100% (**0**) e **Organizar**, que redistribui as caixas em linhas, com animação;
  - o minimapa, no canto inferior direito, mostra o fluxo inteiro e também move a câmera.

A posição e o tamanho das caixas ficam salvos com o arquivo, entram no backup e podem ser desfeitos com **Ctrl + Z**. Caixas novas aparecem ao lado da anterior; **Organizar** arruma tudo de uma vez.

## 🖼️ Galeria de templates

O botão de galeria, logo abaixo do Explorador na barra esquerda, abre 97 templates prontos montados com os blocos da biblioteca. Também é possível abri-la pelo menu **Arquivo > Novo a partir de template...** ou pela busca de comandos, com `Template:` seguido do nome.

Use o alternador **Por técnica | Por temática** para organizar a galeria:

- **Por técnica:** 33 técnicas de prompt em 11 famílias, cada uma com a explicação de como funciona e quando usar. São elas: System prompt, Developer prompt, User prompt, Zero-shot, Persona, Contextual prompting, Constraint prompting, Frameworks de mercado (CO-STAR, RTF, RISEN, CRISPE, RACE e CARE), One-shot, Few-shot, Exemplos contrastivos, Chain-of-Thought, Step-back, Decomposição, Self-consistency, Tree of Thoughts, Iterative prompting, Autocrítica, Avaliação com rubrica, Chain of Density, Ancoragem em fontes (RAG), Saída estruturada, ReAct, Encadeamento de prompts, Meta-prompting, Painel de especialistas, Perguntas antes de responder, Metodologias de vendas, Fórmulas de copy, Multimodal prompting, Prompt visual estruturado, Ficha técnica de câmera e Edição de foto.
- **Por temática:** 15 áreas: Marketing e conteúdo, Escrita e edição, Produto e UX, Desenvolvimento, Dados e análise, Negócios e estratégia, Educação, Atendimento ao cliente, Vendas, Copywriting, Pessoas e RH, Pesquisa, Design e imagem, Photo edit, e IA e prompts.

Cada técnica ou temática é uma seção, e todas abrem recolhidas, mostrando só o título, o resumo e a quantidade de templates. Clique em uma seção para abri-la ou use **Expandir tudo**. Ao buscar ou ao escolher uma categoria na lateral, as seções com resultado já aparecem abertas. Cada vez que a galeria é aberta, ela volta à visão geral recolhida.

A busca procura no título, na descrição, na técnica, na temática e nos blocos de cada template. Clique em um card para ver a prévia: estrutura de blocos, explicação da técnica e o **exemplo preenchido**. Clique duas vezes, ou use **Criar arquivo**, para gerar um novo arquivo na pasta selecionada. **Inserir no arquivo atual** adiciona os blocos ao final do arquivo aberto. As duas ações podem ser desfeitas.

Todo template vem com um exemplo realista preenchido. Os blocos mantêm os marcadores `{{variavel}}`, e os valores de exemplo entram na aba **Variáveis**. Assim, a prévia e o **Copiar prompt** já saem completos, e para reaproveitar o template basta trocar os valores. Ao inserir em um arquivo existente, valores que você já preencheu não são substituídos.

Os 14 tipos de prompt da referência de mercado têm template e blocos próprios:

| Tipo | Template na galeria | Blocos principais |
| --- | --- | --- |
| System Prompt | Personalidade de um assistente | System prompt |
| Developer Prompt | Regras de um agente de programação | Developer prompt, Ferramentas, Restrições |
| User Prompt | Pedido de criação de uma API | User prompt, Ambiente técnico |
| Role Prompting | Arquiteto de software | Papel |
| Zero-Shot Prompt | Classificador de tickets | Classificação |
| One-Shot Prompt | Resposta no padrão de referência | Exemplos (um exemplo) |
| Few-Shot Prompt | Análise de requisitos padronizada | Exemplos (vários) |
| Chain-of-Thought | Resolução de problemas de matemática | Raciocínio passo a passo |
| Contextual Prompting | Análise de repositório existente | Ambiente técnico, Contexto |
| Constraint Prompting | Implementação sem novas dependências | Restrições, Escopo |
| Structured Output | Extração para JSON | Saída em JSON |
| Meta-Prompting | Gerador de prompts | Meta-prompt |
| Iterative Prompting | Revisão iterativa de implementação | Rodada de refinamento |
| Multimodal Prompting | Análise de interface por screenshot | Entrada multimodal |

System, Developer e User são níveis de instrução: a prioridade real depende de como a aplicação envia cada mensagem ao modelo, não do título no texto. Os demais tipos são técnicas de construção e podem ser combinados no mesmo prompt.

### 💰 Vendas e copy

Duas temáticas reúnem os templates comerciais: **Vendas** (9 templates) e **Copywriting** (10). Os 16 novos usam duas técnicas da família **Vendas e copy**:

| Técnica | Templates |
| --- | --- |
| Metodologias de vendas | Prospecção fria por e-mail, Roteiro de descoberta SPIN, Qualificação de leads com BANT (em JSON), Matriz de objeções, Follow-up pós-reunião, Abordagem de vendas pelo WhatsApp, Battlecard contra concorrente, Análise de negócios perdidos |
| Fórmulas de copy | Landing page de vendas (AIDA), Anúncios PAS para redes sociais, E-mail de lançamento com AIDA, Headlines com o critério 4U, Descrição de produto com FAB, Carrossel para Instagram com BAB, Roteiro de vídeo curto de vendas, Sequência de carrinho abandonado |

Os templates **Proposta comercial lapidada**, **Descrições de produto** e **Headlines sem clichê**, que já existiam, passaram para essas temáticas. Os prompts comerciais trazem limites explícitos: usar só provas reais, não criar urgência ou escassez falsa e não desqualificar concorrentes.

### 📷 Photo edit

A seção **Photo edit** reúne 14 prompts de foto descritos como uma ficha técnica de câmera Canon: corpo, lente, modo de exposição, abertura, velocidade do obturador, ISO, modo de foco, balanço de branco em Kelvin, Picture Style com seus parâmetros e revelação do RAW. Os geradores de imagem aprenderam com fotos acompanhadas desses dados (EXIF), então cada ajuste funciona como um atalho visual previsível.

| Técnica | Templates | Equipamento e ajustes de exemplo |
| --- | --- | --- |
| Ficha técnica de câmera | Retrato editorial em luz natural | EOS R5, RF 85mm F1.2 L USM, Av, f/1.8, 1/500 s, ISO 100, Picture Style Retrato |
| | Headshot corporativo em estúdio | EOS R6 Mark II, RF 85mm F2 Macro, M, f/5.6, 1/160 s, Speedlite EL-1 |
| | Produto em macro com bracketing de foco | EOS R5, RF 100mm F2.8 L Macro, f/8, bracketing de foco com 40 disparos |
| | Gastronomia com luz de janela | EOS R6 Mark II, RF 100mm Macro, f/4, 1/80 s, ISO 400 |
| | Paisagem na golden hour | EOS R5, RF 15-35mm a 16 mm, f/11, polarizador, ND graduado, AEB ±2 EV |
| | Esporte com movimento congelado | EOS R3, RF 70-200mm F2.8 L, Tv, 1/2000 s, Servo AF, 30 fps |
| | Rua à noite com neon e chuva | EOS R6 Mark II, RF 35mm F1.8, f/2, ISO 3200, 3800 K |
| | Longa exposição em cachoeira | EOS R5, RF 24-105mm F4 L, f/11, 1 s, ND8 |
| | Via Láctea em céu escuro | EOS R6 Mark II, RF 15-35mm a 15 mm, f/2.8, 20 s, ISO 3200 |
| | Interiores com lente tilt-shift | EOS R5, TS-E 24mm f/3.5L II, f/8, AEB de 5 disparos |
| Edição de foto | Revelação de RAW com look Canon | Ajustes de exposição, realces, sombras, curva e balanço de branco |
| | Retoque de retrato natural | Retoque de pele preservando a textura e desfoque simulando f/1.4 |
| | Preto e branco com filtro vermelho | Picture Style Monocromático, filtro vermelho e efeito de tonalidade |
| | Look analógico de Canon AE-1 | AE-1 Program, New FD 50mm f/1.4, filme Kodak Portra 400 |

Os prompts de edição pedem que a foto seja anexada e trazem o bloco **Preservar do original**, que lista o que não pode mudar, como rosto, enquadramento e objetos. Muitos geradores entendem melhor os termos técnicos em inglês; os valores (f/1.8, 1/500 s, ISO 100, 5600 K) funcionam em qualquer idioma.

## 🎓 Aula: engenharia de prompts

O chapéu de formatura no canto inferior esquerdo, na barra de status, abre uma aula em tela cheia sobre engenharia de prompts. Ela também está em **Ajuda › Aula: engenharia de prompts** e na busca de comandos. O visual é uma lousa escura, com três estilos de animação combinados:

- **Câmera ao estilo Prezi:** os temas ficam espalhados em uma tela infinita, e a câmera se afasta, atravessa o mapa e mergulha no próximo tema. Dois temas ficam aninhados dentro de outros, para dar o efeito de zoom no detalhe.
- **Transformação entre slides:** no estilo do Magic Move, elementos que continuam de um slide para o outro deslizam e se transformam. Por exemplo, o pedido vago vira um cartão estruturado, e os 15 componentes se reagrupam em 6 famílias.
- **Rabiscos ao estilo Scribblenauts:** os elementos surgem com efeito elástico e um "puf" de giz, e os desenhos são traçados à mão com linha tremida.

São 14 temas em 30 slides:

- o que é um prompt;
- linguagem natural: por que você "programa em português" e como trocar palavras vagas por critérios verificáveis;
- Markdown, começando pela diferença entre `.txt` e `.md`;
- níveis de instrução (System, Developer e User);
- zero, one e few-shot;
- raciocínio e processo;
- mapa dos 14 tipos;
- técnicas avançadas;
- anatomia com 15 componentes;
- pontos de qualidade;
- um exemplo estruturado, que pode ser copiado ou aberto direto no editor;
- um prompt, várias IAs: o mesmo documento `.md` enviado ao ChatGPT, Gemini, Grok, Claude e outras, e as formas de enviar (colar, anexar, instruções fixas ou API);
- checklist interativo;
- fechamento.

| Ação | Atalho |
| --- | --- |
| Avançar / voltar | → / ←, Espaço, clique no slide ou deslizar no toque |
| Início / fim | Home / End |
| Visão geral do mapa | O, e clique em um tema para voar até ele |
| Tela cheia | F |
| Sair | Esc |

Com a opção de reduzir movimento do sistema ativada, as transições viram cortes e esmaecimentos simples.

## 📝 Markdown e prévia

Use os botões **Blocos**, **Markdown**, **Prévia** e **Nodes** na barra do editor. Em telas estreitas, eles mostram só os ícones. O editor Markdown inclui numeração de linhas, realce de sintaxe e barra de formatação.

Títulos de nível 2 (`## Nome`) delimitam os blocos. Texto anterior ao primeiro título permanece em um bloco de Texto livre. Títulos dentro de cercas de código com crases ou tis não iniciam blocos. Use `###` para subtítulos dentro de um bloco.

A troca de visão, sem edição, preserva o Markdown. Adicionar, editar e mover blocos pode ajustar as quebras de linha entre seções. Se Texto livre for movido para depois de outro bloco, ele recebe um título `## Texto livre` para continuar sendo uma seção independente.

A prévia é somente leitura e suporta os elementos principais: títulos, parágrafos, listas, checklists, código, citações, links e tabelas simples. Ela não pretende implementar toda a especificação CommonMark. HTML incorporado é exibido como texto, não executado.

## 📁 Arquivos e pastas

O explorador permite criar pastas e subpastas, manter vários arquivos Markdown, abrir abas, filtrar nomes, renomear, duplicar e excluir. Arraste arquivos para pastas ou use **Mover para...**. Excluir uma pasta solicita confirmação e também exclui seu conteúdo.

Importe arquivos `.md`, `.markdown` e `.txt` pelo menu Arquivo ou pelo ícone de importação. Arquivos de texto viram Markdown no workspace. A importação suporta até 100 arquivos por operação e 2 MB por arquivo. Nomes repetidos recebem um sufixo numérico. Arquivos também podem ser soltos sobre a janela do editor.

## 🔁 Variáveis reutilizáveis

Escreva marcadores como `{{tema}}`, `{{marca}}` e `{{publico}}`. A aba **Variáveis** detecta os nomes automaticamente e oferece campos para seus valores. Use nomes iniciados por letra sem acento ou sublinhado; depois são aceitos letras, números, ponto, hífen e sublinhado. Na visão em nodes, cada variável também aparece como um nó com o campo de valor.

Os valores são aplicados na prévia e em **Copiar prompt**. O Markdown original mantém os marcadores. Variáveis sem valor continuam como marcadores. O menu ao lado do botão de cópia permite copiar o Markdown original; o menu Arquivo também exporta o prompt final em `.md`.

## 💾 Salvamento e backups

O workspace é salvo automaticamente no armazenamento local do navegador, sem indicador na barra superior. Se o navegador recusar o salvamento, um aviso aparece uma vez com o atalho **Exportar backup**. As pastas do explorador são virtuais: elas não representam pastas reais do sistema operacional. Não existe sincronização em nuvem.

Use **Exportar workspace** para guardar todos os arquivos, pastas e valores de variáveis em um backup `.json`. Importe esse JSON sozinho para restaurar o workspace. A restauração substitui o workspace atual e exige confirmação.

**Mantenha backups.** Limpar dados do navegador, trocar de perfil ou de endereço de acesso pode deixar o workspace anterior indisponível. Evite editar o mesmo workspace simultaneamente em várias abas. Não guarde senhas, tokens ou outros segredos nos prompts ou nas variáveis.

Desfazer e refazer mantêm até 45 pontos de histórico durante a sessão; esse histórico não persiste ao recarregar a página.

## ⌨️ Atalhos

| Ação | Atalho |
| --- | --- |
| Buscar comandos e arquivos | Ctrl / Cmd + K |
| Novo arquivo | Ctrl / Cmd + N |
| Nova pasta | Ctrl / Cmd + Shift + N |
| Copiar prompt final | Ctrl / Cmd + Shift + C |
| Salvar localmente | Ctrl / Cmd + S |
| Exportar Markdown | Ctrl / Cmd + Shift + S |
| Desfazer / refazer | Ctrl / Cmd + Z / Ctrl / Cmd + Shift + Z |
| Blocos / Markdown / prévia / nodes | Ctrl / Cmd + Alt + 1 / 2 / 3 / 4 |
| Nodes: ajustar à tela / 100% | 1 / 0 |
| Nodes: tirar do fluxo ou religar a caixa selecionada | D |
| Nodes: excluir a caixa selecionada | Delete |
| Nodes: zoom | Ctrl / Cmd + roda do mouse |
| Alternar explorador, fora de campos de texto | Ctrl / Cmd + B |
| Mover bloco com foco na alça | Alt + seta para cima / baixo |

Alguns sistemas ou navegadores podem reservar determinados atalhos. Todas as ações principais também estão disponíveis nos menus e botões.

## 🔧 Implementação e limites

HTML, CSS e JavaScript estão juntos em `index.html`. As cores, tamanhos de texto e raios ficam em tokens CSS no início do arquivo. Ícones são SVG incorporado e fontes são do sistema: a Adobe Clean é usada se já estiver instalada; senão, Source Sans 3 ou Segoe UI. Não há bibliotecas externas nem etapa de build.

Este aplicativo organiza e exporta textos: ele **não executa modelos de IA**. Guardrails são instruções escritas, não filtros aplicados pelo editor. A estimativa de tokens é apenas caracteres divididos por quatro, não uma contagem de um tokenizador de modelo.

Os exemplos em `exemplos/` também estão disponíveis no primeiro uso do editor. `TESTES.md` registra o escopo da verificação automatizada.
