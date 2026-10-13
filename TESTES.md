# 🧪 Verificações do Prompt Forge Studio

Foram concluídas **67 verificações automatizadas** em Chromium, incluindo edição, troca de visão, arraste nativo de blocos e arquivos, validação de nomes, importação, exportação, restauração, variáveis, histórico e painéis responsivos.

## 🔎 Condições dos testes

A navegação para URLs locais era bloqueada pelo ambiente de verificação. Por isso, o HTML foi carregado diretamente no documento de teste com `set_content`. O ciclo de salvamento e restauração foi verificado com um adaptador compatível com a API Storage, não com o armazenamento persistente de um perfil de usuário real.

A cópia foi verificada tanto pelo fluxo normal sem exceções quanto por adaptadores de teste que conferiram os textos finais e originais. Também foi forçada uma negação de permissão para verificar a alternativa de cópia manual. O conteúdo da área de transferência do sistema não foi lido.

Os testes responsivos usaram viewports de 1440 × 1000 e 390 × 844. Não houve erro JavaScript capturado nesses fluxos. Isso não representa certificação de todos os navegadores, dispositivos ou tamanhos de documento.

## ✅ Casos verificados

- Initial six blocks and thirteen templates
- Initial files and folders
- No initial JavaScript errors
- Markdown byte-preserving fixture 1
- Markdown byte-preserving fixture 2
- Markdown byte-preserving fixture 3
- Markdown byte-preserving fixture 4
- Markdown byte-preserving fixture 5
- Markdown byte-preserving fixture 6
- Markdown byte-preserving fixture 7
- Markdown byte-preserving fixture 8
- Markdown byte-preserving fixture 9
- Markdown byte-preserving fixture 10
- Markdown byte-preserving fixture 11
- Fenced headings excluded
- Raw HTML preview escaped
- Unsafe link protocols excluded
- Card edits update source
- Markdown view synchronized
- Markdown edits parse into cards
- Free-text block preserved
- Round trip through views unchanged
- Library click adds block
- Undo block addition
- Redo block addition
- Duplicate block
- Rename block updates heading
- Move block with accessible menu
- Delete block
- Native drag reorders cards
- Moved free-text remains a separate Markdown section
- Native library drag inserts at target
- Variables resolved in preview
- Variables do not overwrite original
- Copy action completed without exception
- Compiled clipboard payload exact
- Raw Markdown clipboard payload exact
- Denied clipboard opens manual fallback
- Create folder
- Create Markdown in selected folder
- Empty-file insertion menu
- Invalid filename rejected
- Rename file
- Duplicate file with new identity
- Move file to root
- Recursive folder deletion
- Undo recursive folder deletion
- Native explorer drag moves file into folder
- Multi-file import and duplicate names
- Export filename
- Markdown export exact contents
- Backup includes all files
- Backup contains original Markdown
- Invalid backup rejected
- Restore backup asks for confirmation
- Restore backup completes
- Backup cycles rejected
- Command palette opens matched file
- Persisted workspace restored through Storage adapter
- Explorer collapses
- Explorer reopens
- Mobile has no horizontal overflow
- Mobile library opens as drawer
- Mobile template click adds and closes drawer
- Mobile explorer opens
- Mobile dismisses drawer
- No JavaScript errors across all workflows

## 🔗 Visão em nodes

Verificada em Chrome headless pelo DevTools Protocol, com eventos de ponteiro, roda e arraste sintéticos, em viewports de 1440 × 900 e 390 × 844. As verificações anteriores (galeria, vendas e copy, photo edit, cobertura de técnicas, animações, recolher e expandir, aula e smoke) foram repetidas sem regressões nem erros JavaScript.

- One box per block, plus Início and Prompt final
- Main wires equal chained blocks plus one
- One variable node and one data wire per variable use
- Output dropped on a box chains it right after the source
- Undo restores the previous order
- Wire scissors takes the target out of the flow
- Loose box excluded from the compiled prompt, kept in the Markdown
- Loose card dimmed and badged in the blocks view
- Box menu links the box back into the flow
- Picking up a connected input and dropping it on empty canvas detaches the box
- Output dropped on empty canvas opens the type menu and chains the new block
- Header drag moves the box; undo restores its position
- Ctrl + wheel zooms the canvas
- Fit keeps every box inside the viewport
- Tidy up leaves no overlapping boxes
- Typing a new variable creates its node and keeps the caret
- Variable node edits the stored value and the compiled prompt
- Variable port dropped on a box inserts the placeholder
- Library drop on empty canvas creates a loose box
- Library drop on a wire lights it and inserts the block there
- Collapse and expand all apply to the boxes
- D key toggles the selected box out of the flow
- View, positions and loose boxes survive state validation on reload
- Empty file shows the add-first-block placeholder and its menu
- Mobile view switch fits without horizontal overflow
