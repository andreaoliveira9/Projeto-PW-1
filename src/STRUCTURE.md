# Estrutura do Projeto MathPath

## Organização de Ficheiros

### Páginas HTML
- `index.html` - Página principal
- `catalog.html` - Catálogo de recursos por ano
- `resource.html` - Visualização de recurso individual
- `contact.html` - Página de contactos
- `account.html` - Área pessoal do utilizador
- `calculator.html` - Calculadora GeoGebra integrada

### Ficheiros CSS

#### `main.css` (31KB, 1,351 linhas)
Contém **APENAS** estilos globais e comuns a todas as páginas:
- Variáveis CSS (cores, tipografia, espaçamentos)
- Estilos base (body, headings, links)
- Header e navegação
- Footer
- Botões globais
- Cards globais
- Badges e alertas globais
- Tabelas base
- Formulários
- Utilitários e helpers
- Tema (light/dark/auto)
- Media queries globais

#### `index.css` (5KB, 255 linhas)
Estilos específicos da página inicial:
- Hero section (background dinâmico por tema)
- Call-to-action buttons (btn-get-started, hero-secondary-btn)
- Intro figure com efeitos hover
- Testimonials section (carousel, cards, quotes)
- Responsividade específica

#### `contact.css` (978B, 52 linhas)
Estilos específicos da página de contactos:
- Info wrapper (background, shadow, padding)
- Info items (ícones, texto, hover effects)
- Responsividade específica

#### `account.css` (4.5KB, 217 linhas)
Estilos específicos da página de conta:
- Secções da conta (intro, summary, planner)
- Badge e navegação da conta
- Tabela de plano semanal
- Ajustes de tema escuro
- Responsividade específica

#### `catalog.css` (3.1KB, 169 linhas)
Estilos específicos do catálogo:
- Accordion do catálogo
- Tabelas do catálogo
- Hero do catálogo com carousel
- Overlays e filtros
- Navegação móvel específica

#### `resource.css` (4.2KB, 203 linhas)
Estilos específicos da página de recursos:
- Viewer de recursos (iframe)
- Controlos de navegação de recursos
- Chat da turma
- Animações de tabs
- Scrollbars personalizados

#### `calculator.css` (354B, 21 linhas)
Estilos específicos da calculadora:
- Container do iframe
- Iframe responsivo
- Ajustes de altura

## Princípios de Organização

### 1. Separação Estrita de Responsabilidades
- **Global** → `main.css` (APENAS estilos usados em todas as páginas)
- **Específico de página** → ficheiro CSS individual

### 2. Zero Duplicação
- Cada regra CSS existe em apenas um ficheiro
- Estilos comuns consolidados em `main.css`
- Estilos únicos isolados nos ficheiros de página

### 3. Nomenclatura Consistente
- Classes BEM-like quando aplicável
- Prefixos de página para estilos específicos (.hero, .contact, .catalog-, etc.)
- Variáveis CSS para valores reutilizáveis

### 4. Estrutura de Comentários
```css
/* Secção Principal */

/* Subsecção */
.classe {
  /* propriedades */
}

/* Responsive Design */
@media (max-width: 767.98px) {
  /* ajustes móvel */
}
```

### 5. Ordem de Propriedades CSS
1. Posicionamento (position, top, left, etc.)
2. Display e Box Model (display, width, height, padding, margin)
3. Tipografia (font, text-align, etc.)
4. Visual (background, border, etc.)
5. Outros (transition, animation, etc.)

## Assets

### Estrutura de Pastas
```
assets/
├── css/
│   ├── main.css          # Estilos globais
│   ├── index.css         # Página inicial
│   ├── contact.css       # Página de contactos
│   ├── account.css       # Página de conta
│   ├── catalog.css       # Catálogo
│   ├── resource.css      # Recursos
│   └── calculator.css    # Calculadora
├── js/
│   ├── main.js           # JavaScript principal
│   └── theme.js          # Gestão de tema
├── vendor/
│   ├── bootstrap/        # Framework CSS
│   ├── bootstrap-icons/  # Ícones
│   └── aos/              # Animações on scroll
└── img/                  # Imagens do site
```

## Dependências

### CSS
- Bootstrap 5.3.3 (framework base)
- Bootstrap Icons (iconografia)
- AOS (Animate On Scroll)

### Fonts
- Google Fonts: Roboto, Poppins, Raleway

### JavaScript
- Bootstrap JS (componentes interativos)
- AOS JS (animações)
- Custom JS (tema e navegação)

## Boas Práticas Implementadas

1. ✅ Código limpo e organizado
2. ✅ Zero duplicação de estilos
3. ✅ Comentários informativos
4. ✅ CSS específico por página
5. ✅ Variáveis CSS para consistência
6. ✅ Design responsivo
7. ✅ Suporte para tema escuro
8. ✅ Acessibilidade (aria-labels, semantic HTML)
9. ✅ Performance (defer, lazy loading)
10. ✅ SEO (meta tags, alt text)
11. ✅ Separação estrita: global vs específico

## Mapa de Uso de CSS

| Página | CSS Principal | CSS Específico | Total Estilos |
|--------|--------------|----------------|---------------|
| index.html | main.css (31KB) | index.css (5KB) | 36KB |
| catalog.html | main.css (31KB) | catalog.css (3.1KB) | 34KB |
| resource.html | main.css (31KB) | resource.css (4.2KB) | 35KB |
| contact.html | main.css (31KB) | contact.css (978B) | 32KB |
| account.html | main.css (31KB) | account.css (4.5KB) | 36KB |
| calculator.html | main.css (31KB) | calculator.css (354B) | 31KB |

## Manutenção Futura

### Para Adicionar Novos Estilos

1. **Estilo usado em TODAS as páginas?**
   - Adicionar a `main.css`
   - Comentar adequadamente
   - Verificar que não existe duplicado

2. **Estilo específico de UMA página?**
   - Adicionar ao CSS da página específica
   - Nunca adicionar a `main.css`
   - Verificar se não pode ser reutilizado

3. **Nova página?**
   - Criar novo ficheiro CSS (nome da página)
   - Incluir apenas estilos únicos
   - Seguir padrão de organização existente
   - Adicionar link no HTML

### Checklist de Validação

- [ ] Sem estilos inline
- [ ] Sem !important desnecessário
- [ ] Comentários claros
- [ ] Testado em mobile
- [ ] Testado em tema escuro
- [ ] Sem duplicação entre ficheiros
- [ ] Incluído no HTML correto
- [ ] Estilo é realmente específico (não global)

### Testes de Qualidade

```bash
# Verificar duplicação entre ficheiros
cd assets/css
for file in *.css; do
  echo "Analisando $file..."
  # Verificar se regras existem em main.css e noutro ficheiro
done

# Verificar se há estilos não utilizados
grep -o 'class="[^"]*"' *.html | # Extrair todas as classes
  sort -u | # Remover duplicados
  # Comparar com classes nos CSS
```

### Estatísticas do Projeto

**Total de CSS**: ~50KB (sem minificação)
**Total de Linhas CSS**: 2,268 linhas

**Distribuição**:
- main.css: 60% (1,351 linhas) - **Apenas global**
- index.css: 11% (255 linhas)
- account.css: 10% (217 linhas)
- resource.css: 9% (203 linhas)
- catalog.css: 7% (169 linhas)
- contact.css: 2% (52 linhas)
- calculator.css: 1% (21 linhas)

**Redução de main.css**:
- Antes: 1,664 linhas (40KB)
- Depois: 1,351 linhas (31KB)
- **Redução: 19% em tamanho, 313 linhas removidas**

## Validação de Organização

### Como Verificar se CSS está Bem Organizado

1. **main.css não deve ter**:
   - Classes começadas por `.hero` (exceto se usadas em todas as páginas)
   - Classes começadas por `.contact`
   - Classes começadas por `.catalog-`
   - Classes começadas por `.account-`
   - Classes começadas por `.resource-`
   - Classes começadas por `.testimonial`
   - Qualquer seletor específico de uma página

2. **Ficheiros específicos devem ter**:
   - Apenas estilos usados naquela página
   - Comentários explicativos
   - Seções organizadas
   - Responsividade quando necessário

3. **Todos os CSS devem**:
   - Seguir o mesmo padrão de formatação
   - Ter comentários de cabeçalho
   - Usar variáveis CSS quando possível
   - Estar referenciados corretamente no HTML

---

**Última atualização**: 2025-10-22
**Versão**: 3.0
**Status**: ✅ Totalmente organizado e otimizado
