# 📝 Documento de MVP: Just Write It
**Conceito:** O refúgio digital para escrita focada, unindo a nostalgia da máquina de escrever com a praticidade do Markdown moderno.

---

## 1. Visão Geral
**Just Write It** é um editor de texto minimalista baseado em navegador, focado na experiência sensorial da escrita. Ele elimina todas as distrações visuais (menus, barras laterais, pop-ups) e foca no que importa: a conexão entre o pensamento e a tecla.

*   **Slogan:** Just write. No noise. Just vibe.
*   **Público-alvo:** Escritores, desenvolvedores (notas rápidas), estudantes e entusiastas da estética indie/minimalista.

---

## 2. Personas e Casos de Uso
1.  **O Programador "Vibe":** Quer anotar uma lógica ou rascunhar um README sem abrir o VS Code, mas quer sentir que ainda está em um ambiente "nerd".
2.  **O Escritor Minimalista:** Distrai-se facilmente com as ferramentas do Google Docs e busca um ambiente zen para fluir o texto.
3.  **O Aprendiz de Markdown:** Quer uma forma visual e imediata de praticar a sintaxe Markdown enquanto estuda.

---

## 3. Stack Tecnológica (The "Lean" Stack)
Para garantir a entrega em 48 horas e performance máxima:
*   **Framework:** [Next.js](https://nextjs.org/) (App Router) ou [Vite + React](https://vitejs.dev/).
*   **Estilização:** [Tailwind CSS](https://tailwindcss.com/) (pela agilidade e design system embutido).
*   **Markdown:** `react-markdown` (para renderização) e `remark-gfm` (suporte a tabelas/checklists).
*   **Áudio:** [Howler.js](https://howlerjs.com/) (gerenciamento de áudio com baixa latência).
*   **Exportação:** [html2pdf.js](https://ekoopmans.github.io/html2pdf.js/) (converte o HTML renderizado em PDF direto no cliente).
*   **Persistência:** `localStorage` (Zero custo de banco de dados).

---

## 4. Requisitos Funcionais (O que ele faz)
*   **RF01 - Editor Fullscreen:** Interface limpa que ocupa 100% da viewport.
*   **RF02 - Mecanismo de Som:** Emitir sons de teclas mecânicas ao digitar, com um som diferente para a tecla "Enter".
*   **RF03 - Auto-save:** Salvar o progresso automaticamente no `localStorage` a cada 500ms de inatividade após digitar.
*   **RF04 - Renderização Markdown:** Atalho (ex: `Ctrl + P`) ou botão flutuante discreto para alternar entre modo edição e modo visualização.
*   **RF05 - Exportação PDF:** Gerar um PDF formatado com tipografia elegante a partir do conteúdo escrito.
*   **RF06 - Contador de Palavras:** Exibição discreta (baixa opacidade) no rodapé.

---

## 5. Requisitos Não-Funcionais (A "Vibe")
*   **RNF01 - Latência de Áudio:** O som deve ser disparado em menos de 10ms após o clique (sensação tátil).
*   **RNF02 - Estética:** Uso de fontes Mono (ex: *JetBrains Mono*, *Space Mono*) ou Serifadas Modernas (ex: *Lora*, *Playfair Display*).
*   **RNF03 - Privacy-First:** Nenhum dado deve ser enviado para servidores. Tudo acontece no browser do usuário.
*   **RNF04 - Responsividade:** Deve funcionar bem em tablets, permitindo escrita com teclados externos.

---

## 6. Funcionalidades de Diferenciação (The Indie Touch)
*   **O "Zen Mode":** Quando o usuário começa a digitar, todos os elementos da interface (botão de exportar, contador) desaparecem suavemente (fade-out). Quando ele para por 3 segundos, eles reaparecem.
*   **Variação de Pitch:** Cada tecla pressionada tem um leve ajuste aleatório no tom do áudio para não soar como um loop robótico.
*   **Feedback Visual do Cursor:** Um cursor customizado que pulsa suavemente, como um terminal antigo.

---

## 7. Estratégia de Monetização & Crescimento
Para manter o espírito "indie livre", mas abrir portas para renda extra:

1.  **O "Soft-Paywall" de Exportação:**
    *   Ao clicar em "Exportar para PDF", abre-se um modal bonito: *"Seu texto está pronto! Este projeto é mantido por um desenvolvedor independente. Se você gostou da experiência, considere apoiar com qualquer valor."* (Botão de PIX/BuyMeACoffee).
2.  **Temas Premium (Fase 2):**
    *   Grátis: Temas "Paper" (Claro) e "Night" (Escuro).
    *   Pago (Lifetime Access): Temas "Cyberpunk", "Terminal 80s", "Deep Sea".

---

## 8. Roadmap de Desenvolvimento (O Final de Semana)

### Sábado: Estrutura e Alma
*   **Manhã:** Setup do projeto, configuração do Tailwind e criação do componente `Editor.tsx` com foco em tipografia.
*   **Tarde:** Implementação do áudio com `Howler.js` e a lógica de `localStorage`.
*   **Noite:** Integração do parser Markdown para visualização.

### Domingo: Polimento e Entrega
*   **Manhã:** Implementação da biblioteca de PDF e estilização do documento de saída.
*   **Tarde:** Criação das animações de UI (o "aparece e desaparece" dos menus) e refinamento dos sons.
*   **Noite:** Deploy na Vercel, criação do README.md no GitHub com um GIF demonstrativo e postagem em comunidades (Reddit r/SideProject, Twitter, etc).

---

## 9. Riscos e Mitigações
*   **Risco:** O som ficar irritante após 10 minutos.
    *   *Solução:* Adicionar um ícone de "Mute" muito fácil de acessar ou uma tecla de atalho rápida.
*   **Risco:** O PDF quebrar a formatação.
    *   *Solução:* Criar uma folha de estilo CSS `@media print` específica para garantir que o PDF seja sempre perfeito, independente do que se vê na tela.
# just-write-it
A Browser Tool for focus writing, with vibe mode.
