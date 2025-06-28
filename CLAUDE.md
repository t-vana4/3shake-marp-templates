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
# Convert to PDF (if marp is installed locally)
marp slides/[presentation].md --pdf --allow-local-files

# Convert to PDF (using npx)
npx @marp-team/marp-cli@latest slides/[presentation].md --pdf --allow-local-files

# Convert to PowerPoint
marp slides/[presentation].md --pptx --allow-local-files

# Convert to HTML
marp slides/[presentation].md --html --allow-local-files
```

### Watch Mode (Live Reload)
```bash
# Watch mode with automatic browser opening
marp slides/[presentation].md --html --allow-local-files --watch & open slides/[presentation].html

# Example for specific presentation
marp slides/2025/claude-code-beyond.md --html --allow-local-files --watch & open slides/2025/claude-code-beyond.html
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

## Presentation Creation Best Practices

### Content Strategy
- **Follow the narrative arc**: Introduction → Problem → Solution → Conclusion
- **One message per slide**: Keep each slide focused on a single concept
- **Use concrete examples**: Replace abstract concepts with specific data and real-world examples
- **Audience-appropriate content**: Adjust technical depth based on audience expertise

### Visual Design Principles
- **Leverage contrast**: Use color, size, and positioning to highlight key information
- **Embrace white space**: Avoid cramming too much content; prioritize readability
- **Maintain consistency**: Standardize fonts, colors, and layouts throughout
- **Strategic image use**: Combine text with relevant visuals for better retention

### Technical Implementation Tips
```markdown
<!-- Effective slide layouts -->
<!-- _class: lead -->          # Title slides
<!-- _class: split -->         # Two-column layouts  
<!-- _class: invert -->        # Dark theme slides
<!-- _backgroundColor: #f0f0f0 --> # Custom backgrounds

<!-- Proper image referencing -->
![Alt text](./assets/images/2025/presentation-name/diagram.png)

<!-- Structured emphasis -->
**Primary emphasis** (bold)
*Secondary emphasis* (italic)
`Code elements` (inline code)

<!-- Hierarchical lists -->
1. Main point
   - Supporting detail
   - Additional context
     - Granular information

<!-- Advanced image and text layouts -->
<!-- Image left, text right layout -->
## <span class="highlight-blue">Section Title</span>

<div style="display: flex; gap: 40px;">
<div style="width: 35%;">
<img src="../../assets/images/2025/presentation-name/image.jpg" alt="description" style="width: 100%; height: fit-content;">
<div style="font-size: 0.7em; text-align: left; margin-top: 5px;">
Source: Image attribution or description
</div>
</div>

<div style="flex: 1;">
Main content goes here.</br></br>

1. **Point 1**
2. **Point 2**  
3. **Point 3**
</div>
</div>

<!-- Centered image layout -->
<div style="text-align: center;">
<img src="diagram.png" alt="diagram" style="max-width: 80%; height: auto;">
</div>

**Figure 1: Diagram description**

<!-- Multiple images side by side -->
<div style="display: flex; gap: 20px; justify-content: center;">
<div style="text-align: center;">
<img src="image1.png" alt="desc1" style="width: 300px;">
<div style="font-size: 0.8em;">Caption 1</div>
</div>
<div style="text-align: center;">
<img src="image2.png" alt="desc2" style="width: 300px;">
<div style="font-size: 0.8em;">Caption 2</div>
</div>
</div>

<!-- Advanced styling -->
<span class="highlight-blue">Highlighted text</span>
<span class="highlight-yellow">Warning text</span>

<!-- Custom blockquotes -->
<blockquote style="border-left: 4px solid #4AADDD; padding-left: 1em; font-style: italic;">
Important quotation or emphasis
</blockquote>
```

### Performance and Organization
- **Optimize image sizes**: Use appropriately sized images for web delivery
- **Maintain file structure**: Follow `assets/images/year/presentation-name/` convention
- **Choose appropriate themes**: Select themes that match presentation context
- **Test across formats**: Verify appearance in HTML, PDF, and PPTX outputs
- **HTML/CSS flexibility**: Leverage direct HTML and CSS for advanced layouts beyond standard Markdown

### Time Management Guidelines
- **1-2 minutes per slide**: Calculate total slides based on presentation duration
- **Include buffer time**: Account for Q&A and potential technical issues
- **Practice with timing**: Rehearse presentation to validate pacing

### Engagement Strategies
- **Repeat key messages**: Reinforce important points multiple times
- **Interactive elements**: Include polls, questions, or discussion prompts
- **Backup materials**: Prepare appendix slides for detailed Q&A responses