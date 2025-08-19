# Simple Ad Blocker (Beginner) por Guilherme Mendes

Um **bloqueador de anúncios simples** feito para portfólio de quem está começando.  
Funciona como uma extensão do Chrome (Manifest V3), escondendo seletores comuns de anúncios e permitindo **ativar/desativar por site**.

> ⚠️ Projeto educativo. Não pretende competir com bloqueadores completos.

## Como instalar (modo desenvolvedor)

1. Baixe/extraia esta pasta do projeto.
2. Abra o Chrome e vá em `chrome://extensions/`.
3. Ative **Modo do desenvolvedor** (canto superior direito).
4. Clique em **Carregar sem compactação** e selecione a pasta do projeto.
5. A extensão aparecerá com o nome **Simple Ad Blocker (Beginner)**.

## Como usar
- Abra qualquer site e clique no ícone da extensão.
- Use o **toggle** para ativar/desativar o bloqueio **apenas nesse domínio**.
- Clique em **Recarregar página** para aplicar imediatamente (opcional).

## Como funciona (resumo técnico)
- `content.js` aplica regras simples para **ocultar** elementos com seletores comuns de anúncios (`.ad`, `.ads`, `iframe[src*="doubleclick"]`, etc.).
- Um `MutationObserver` observa o DOM e reaplica as regras em elementos inseridos dinamicamente.
- O status de ativação por domínio é salvo usando `chrome.storage.sync` (permanece salvo entre dispositivos logados).

## Limitações
- Regras são **genéricas**, alguns anúncios podem passar ou causar efeitos visuais inesperados.
- Não há bloqueio de requisições de rede, apenas oculta elementos visuais.
- Players como o do YouTube podem exigir recarga manual para funcionar corretamente.

## Próximos passos (sugestões para evoluir o projeto)
- Fazer uma página de **Opções** com seletores personalizáveis.
- Migrar para **declarativeNetRequest** para bloquear anúncios via rede.
- Adicionar temas claros/escuros no popup.
- Criar testes automatizados (ex: Playwright) e configurar CI com GitHub Actions.

## Estrutura do projeto

