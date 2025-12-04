**Project Overview**

- **Tipo:** Site estático (HTML/CSS/JS) — sem build tools ou dependências Node/Python encontradas.
- **Arquivos-chave:** `index.html` (estrutura + scripts inline), `staly.css` (estilos), `assets/` (imagens e ícones), `notas.txt` (anotações de marcação e exemplos).
- **Padrões principais:** HTML sem frameworks; scripts DOM vanilla embutidos em `index.html`.

**How To Run / Dev Workflow**

- **Abrir localmente:** abra `index.html` no navegador (duplo clique ou `open index.html`). Não há `npm`/`make`/CI configurado.
- **Editar estilos:** edite `staly.css` e recarregue a página.
- **Editar comportamento:** scripts estão inline em `index.html`. Para mudanças de lógica, edite o bloco `<script>` antes de extrair para arquivos separados se necessário.

**Project-Specific Conventions & Patterns**

- Sessão de login: a lógica de autenticação é implementada inline (variáveis `savedUser`, `savedPass`, e credenciais estáticas `pedro-dev` / `123`). Procure em `index.html` por esses identificadores quando for alterar fluxo de login.
- Uso semântico de HTML: `main`, `header`, `nav`, `section`, `footer` são empregados — preserve essas tags ao refatorar para manter acessibilidade/SEO.
- Recursos estáticos: imagens e ícones ficam em `assets/` — mantenha caminhos relativos como `assets/lutador.jpg` e `./assets/favicon.png`.

**Integration Points & External Resources**

- Ícones/JS externos: ionicons é carregado via CDN (`https://unpkg.com/ionicons@7.4.0/...`).
- Links externos: redes sociais e recursos (ex.: links em `#social-links`) são links absolutos; validar ao modificar.

**Safe Edit Guidelines for AI Agents**

- Não altere credenciais embutidas (`pedro-dev` / `123`) sem pedir confirmação — elas são usadas para demo/local e mudar isso pode quebrar testes humanos.
- Ao mover código JS inline para arquivos separados, atualize também as referências no `index.html` e confirme que o comportamento de login (mostrar/ocultar `#login-container` e `#conteudo`) permanece.
- Mantenha alterações pequenas e fáceis de reverter; este repositório não tem histórico CI configurado.

**Examples (what to change and where)**

- Alterar título do site: edite `<title>` em `index.html`.
- Atualizar estilos do botão secundário: edite a classe `.secundario` em `staly.css`.
- Atualizar rede social ou ícone: substitua `./assets/github.png` e atualize o `href` correspondente em `index.html`.

**Search Hints / Quick Grep**

- Procurar texto de login/registro: `grep -n "pedro-dev\|savedUser\|toggle-register" index.html`.
- Procurar assets referenciados: `grep -R "assets/" -n`.

**What I Could Not Find**

- Não há `package.json`, scripts de build, testes automatizados ou instruções de CI no repositório. O `README.md` está essencialmente vazio.

**When In Doubt**

- Pergunte ao mantenedor antes de alterar comportamento de autenticação ou links públicos.
- Para mudanças maiores (introdução de bundler, testes), proponha um plano primeiro.

Please review these instructions and tell me which parts you want expanded or adjusted.
