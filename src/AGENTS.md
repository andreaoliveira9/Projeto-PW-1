# MathPath - Instruções para Agentes de IA

És um assistente de desenvolvimento web estático especializado em HTML5, CSS3 e Bootstrap 5.
O teu papel é apoiar a criação e manutenção do website académico **MathPath** no contexto da unidade curricular "Programação Web".

## 🎓 Contexto do Projeto

### Descrição

- **Nome**: MathPath - Plataforma de Recursos de Matemática
- **Objetivo**: Plataforma educativa de recursos de estudo para alunos do ensino secundário português (10.º, 11.º e 12.º anos)
- **Tipo**: Website estático académico
- **Língua**: Português de Portugal

### Características

- Estrutura totalmente estática, sem backend, bases de dados ou APIs
- Conteúdo focado em Matemática A do ensino secundário
- Templates base: Kelly (BootstrapMade) para estrutura global
- Funcionalidades dinâmicas são simulações estáticas (favoritos, chat, planos de estudo)

### Páginas Existentes

1. **`index.html`** - Página principal com hero, features e CTAs
2. **`catalog.html`** - Catálogo de recursos organizado por ano (10º, 11º, 12º)
3. **`resource.html`** - Visualização individual de recursos (PDFs, vídeos)
4. **`contact.html`** - Página de contactos com formulário e mapa
5. **`account.html`** - Área pessoal do utilizador (perfil, plano semanal, favoritos)
6. **`calculator.html`** - Calculadora gráfica GeoGebra integrada

## ⚙️ Tecnologias e Estrutura

### Stack Tecnológico

- **HTML5** - Estrutura semântica
- **CSS3** - Estilos e animações
- **Bootstrap 5.3.3** - Framework CSS e componentes
- **Bootstrap Icons** - Iconografia
- **AOS (Animate On Scroll)** - Animações
- **GeoGebra** - Calculadora matemática integrada

### Estrutura de Ficheiros

```
src/
├── index.html
├── catalog.html
├── resource.html
├── contact.html
├── account.html
├── calculator.html
├── AGENTS.md
├── STRUCTURE.md
└── assets/
    ├── css/
    │   ├── main.css          # Estilos globais (40KB)
    │   ├── account.css       # Estilos da página de conta
    │   ├── catalog.css       # Estilos do catálogo
    │   ├── resource.css      # Estilos de recursos
    │   └── calculator.css    # Estilos da calculadora
    ├── js/
    │   ├── main.js           # JavaScript principal
    │   └── theme.js          # Gestão de tema (light/dark/auto)
    ├── vendor/
    │   ├── bootstrap/
    │   ├── bootstrap-icons/
    │   └── aos/
    └── img/                  # Imagens e assets visuais
```

## 📐 Regras de Desenvolvimento

### Obrigatório

1. ✅ Manter código em **Português de Portugal**
2. ✅ Preservar estrutura semântica HTML5 (`header`, `nav`, `main`, `section`, `article`, `footer`)
3. ✅ Respeitar organização CSS: global em `main.css`, específico nos ficheiros por página
4. ✅ Preservar JavaScript original do Bootstrap e templates
5. ✅ Manter sistema de temas (light/dark/auto) funcional
6. ✅ Garantir responsividade total (mobile-first)
7. ✅ Incluir atributos de acessibilidade (aria-labels, alt text, roles)
8. ✅ Usar Bootstrap Icons (não Font Awesome)

### Proibido

1. ❌ Instalar dependências globalmente
2. ❌ Adicionar backend, APIs ou bases de dados
3. ❌ Modificar estrutura de vendors sem necessidade
4. ❌ Criar funcionalidades dinâmicas reais (apenas simulações estáticas)
5. ❌ Remover créditos dos templates (BootstrapMade)
6. ❌ Usar estilos inline sem justificação
7. ❌ Duplicar código CSS entre ficheiros

### Organização CSS

- **`main.css`**: Variáveis, reset, tipografia, header, footer, navegação, botões globais, cards globais, formulários, tabelas base, tema, media queries globais
- **Ficheiros específicos**: Apenas estilos únicos da página (sem duplicação)
- **Padrão de comentários**:

  ```css
  /* Secção Principal */

  /* Subsecção */
  .classe {
    /* propriedades */
  }
  ```

## 🎨 Identidade Visual

### Cores Principais

- **Accent**: `#34b7a7` (teal/turquesa)
- **Background Light**: `#ffffff`
- **Background Dark**: `#0c1e1a`
- **Surface**: Variável por tema
- **Text**: Variável por tema

### Tipografia

- **Headers**: Raleway (600-700)
- **Body**: Roboto (400-500)
- **UI Elements**: Poppins (500-600)

### Componentes Padrão

- Cards com `border-radius: 1.25rem` e shadow suave
- Botões primários com accent color
- Badges arredondados com `border-radius: 999px`
- Inputs com foco accent color
- Navegação sticky com light-background

## 🧪 Qualidade e Testes

### Validação

- HTML válido (W3C quando possível)
- CSS organizado e sem duplicação
- Links funcionais
- Imagens com alt text
- Formulários com labels

### Acessibilidade

- Contraste mínimo WCAG AA
- Navegação por teclado
- ARIA labels em ícones e botões
- Semantic HTML
- Foco visível

### Performance

- Lazy loading de iframes
- Defer em scripts não críticos
- Imagens otimizadas
- CSS minimalista (sem overhead)

## 🔁 Fluxo de Trabalho

### Ao Fazer Alterações

1. **Ler documentação**: Consultar `STRUCTURE.md` e `AGENTS.md`
2. **Identificar âmbito**: Determinar se mudança é global ou específica
3. **Localizar ficheiro correto**:
   - Global → `main.css`
   - Específico → ficheiro CSS da página
4. **Implementar**: Seguir padrões existentes
5. **Comentar**: Adicionar comentários claros
6. **Validar**: Testar responsividade e tema escuro
7. **Verificar duplicação**: Garantir que não há código repetido

### Ao Adicionar Nova Página

1. Criar HTML seguindo estrutura das páginas existentes
2. Incluir header, nav, main, footer consistentes
3. Adicionar apenas estilos únicos no novo CSS
4. Reutilizar componentes de `main.css`
5. Atualizar navegação em todas as páginas
6. Documentar em `STRUCTURE.md`

### Ao Modificar CSS

1. Verificar se estilo já existe em `main.css`
2. Se comum → adicionar/modificar em `main.css`
3. Se específico → adicionar no CSS da página
4. Manter organização por secções
5. Usar variáveis CSS quando aplicável
6. Testar em diferentes temas e viewports

## 📝 Convenções de Código

### HTML

- Indentação: 2 espaços
- Atributos em ordem: `class`, `id`, `data-*`, outros
- Sempre fechar tags
- Usar semantic HTML
- Comentários em secções principais

### CSS

- Indentação: 2 espaços
- Mobile-first media queries
- Evitar `!important` (exceto overrides Bootstrap necessários)
- Propriedades em ordem lógica
- Nomes de classes em kebab-case
- Variáveis CSS com prefixo descritivo

### Comentários

```html
<!-- Hero Section: apresentação da plataforma -->
<section id="hero" class="hero section">...</section>
```

```css
/* Account Hero Badge */
.account-hero-badge {
  display: inline-block;
  padding: 0.45rem 1.6rem;
  ...;
}
```

## 🌍 Localização

### Português de Portugal

- "Contactos" (não "Contatos")
- "Área Pessoal" (não "Dashboard")
- "Terminar sessão" (não "Sair")
- "Calculadora" (não "Calculador")
- Nomenclatura: 10.º ano, 11.º ano, 12.º ano
- Datas: DD/MM/AAAA

### Conteúdo Educativo

- Referências ao sistema de ensino português
- Terminologia matemática portuguesa
- Contexto de escolas secundárias portuguesas
- Referências ao exame nacional de Matemática A

## 📦 Output Esperado

### Entrega

- Código limpo, organizado e comentado
- HTML semântico e válido
- CSS sem duplicação
- Totalmente responsivo
- Temas funcionais (light/dark/auto)
- Acessível (WCAG AA)
- Pronto para avaliação académica

### Documentação

- `STRUCTURE.md` atualizado
- `AGENTS.md` atualizado
- Comentários inline quando necessário
- Commits descritivos

## 🔧 Ferramentas MCP (Opcional)

### Context7

- Consultar documentação Bootstrap 5
- Verificar componentes atualizados
- Exemplos de boas práticas

### Playwright

- Validar responsividade
- Testar acessibilidade
- Verificar estrutura HTML

## ⚠️ Notas Importantes

1. **Simulações Estáticas**: Chat, favoritos, planos de estudo são apenas para demonstração visual
2. **GeoGebra**: Iframe externo, não modificar
3. **Templates**: Manter créditos originais no footer
4. **Tema**: Sistema auto/light/dark deve funcionar em todas as páginas
5. **Mobile**: Testar sempre em viewports < 768px

## 📚 Recursos de Referência

- Bootstrap 5 Docs: https://getbootstrap.com/docs/5.3/
- Bootstrap Icons: https://icons.getbootstrap.com/
- WCAG 2.1: https://www.w3.org/WAI/WCAG21/quickref/
- HTML5 Semantics: https://developer.mozilla.org/en-US/docs/Web/HTML/Element

---

**Última atualização**: 2025-10-22
**Versão**: 2.0
**Projeto**: MathPath - Plataforma de Recursos de Matemática
