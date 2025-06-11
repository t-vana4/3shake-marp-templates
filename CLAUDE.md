# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Marp-based presentation template repository for 3-SHAKE Inc. It provides branded templates, themes, and tools for creating consistent, professional presentations using Markdown.

## Common Development Commands

### Development Server
```bash
# Start local server with live reload (default port 8080)
npm start

# Start with preview mode
npm run preview
```

### Building Presentations
```bash
# Convert to PDF
npx @marp-team/marp-cli@latest slides/[presentation].md --pdf --allow-local-files

# Convert to PowerPoint
npx @marp-team/marp-cli@latest slides/[presentation].md --pptx --allow-local-files

# Convert to HTML
npx @marp-team/marp-cli@latest slides/[presentation].md --html --allow-local-files
```

### Neovim Integration (marp.nvim)
```bash
# Setup marp.nvim plugin (lazy.nvim)
{
  'nwiizo/marp.nvim',
  ft = "markdown",
  config = function()
    require("marp").setup {
      marp_command = "/path/to/marp",
      server_mode = false
    }
  end,
}

# Key commands within Neovim:
# :MarpWatch - Start live preview
# :MarpStop - Stop watching
# :MarpExport [format] - Export to various formats
# :MarpTheme [theme] - Switch themes
```

### Testing Mermaid Diagrams
```bash
# Preview with Mermaid support
npm start -- --html
```

## High-Level Architecture

### Directory Structure Purpose
- **`templates/`**: Base presentation templates to copy when creating new presentations
- **`themes/`**: CSS themes that define visual styling and layout rules
- **`slides/`**: Actual presentations, organized by year
- **`assets/images/`**: Shared images, organized by year and presentation

### Theme System
The theming system uses CSS custom properties and class-based styling:
- `3shake-theme.css`: Primary theme with brand colors (#4AADDD, #0a1929, #ECBE30)
- Auto-injects company logo via CSS `::after` pseudo-elements
- Supports custom classes for different slide layouts (`lead`, `split`, etc.)

### Mermaid Integration
Mermaid diagrams are supported with responsive sizing through custom CSS classes:
- `.mermaid-sm`: Small diagrams (300px max height)
- `.mermaid-md`: Medium diagrams (500px max height)
- `.mermaid-lg`: Large diagrams (700px max height)
- `.mermaid-xl`: Extra large diagrams (900px max height)

### Citation System
Uses superscript notation with automatic formatting:
```markdown
Important claim^[1]^
```
Renders with proper styling for academic/professional citations.

## Key Technical Details

### Marp Configuration
- **HTML enabled**: Required for Mermaid diagrams and advanced formatting
- **Local files allowed**: Necessary for accessing theme CSS and images
- **Theme inheritance**: Custom themes extend Marp's default theme

### Editor Integration
The repository supports multiple editors:

**VS Code Integration:**
- Enable HTML in Markdown preview
- Configure Marp preview settings
- Set up proper file associations

**Neovim Integration (marp.nvim):**
- Live preview with `:MarpWatch`
- Export functionality with `:MarpExport [format]`
- Theme switching with `:MarpTheme [theme]`
- Auto-cleanup on buffer close
- Support for HTML, PDF, PPTX, PNG, JPEG formats

### Asset Management
Images are organized by year and presentation to maintain clarity:
```
assets/images/2025/[presentation-name]/[image-name].png
```

## Development Patterns

### Creating New Presentations
1. Copy appropriate template from `templates/`
2. Place in `slides/[year]/[presentation-name].md`
3. Create corresponding image directory if needed
4. Reference theme using frontmatter: `theme: ./themes/3shake-theme.css`

### Theme Customization
When modifying themes:
- Brand colors are defined as CSS variables in `:root`
- Logo placement is handled by `.markdown-body::after`
- Custom slide layouts use class-based selectors

### Mermaid Diagram Best Practices
- Always wrap diagrams in HTML divs with sizing classes
- Use HTML comments to hide Marp directives from Mermaid
- Test diagrams in preview mode before building