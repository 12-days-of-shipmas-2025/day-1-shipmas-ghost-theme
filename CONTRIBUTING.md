# Contributing to Shipmas Ghost Theme

Thanks for your interest in contributing! This guide will help you get started.

## Development Setup

### Prerequisites

- Node.js 18+
- Docker (for local Ghost instance)
- A Ghost site for testing (or use Docker)

### Local Development

1. **Clone the repo**
   ```bash
   git clone https://github.com/12-days-of-shipmas-2025/shipmas-ghost-theme.git
   cd shipmas-ghost-theme
   ```

2. **Start local Ghost instance**
   ```bash
   docker compose up -d
   ```
   Ghost will be available at http://localhost:2368

3. **Install theme dependencies**
   ```bash
   cd source
   npm install
   ```

4. **Start development server**
   ```bash
   npm run dev
   ```
   This watches for changes and live-reloads the theme.

5. **Complete Ghost setup**
   - Visit http://localhost:2368/ghost
   - Create your admin account
   - The theme is auto-mounted via Docker volume

### Building for Production

```bash
cd source
npm run zip
```

The theme zip will be at `source/dist/shipmas.zip`.

## Testing

### Theme Validation

Run GScan to validate the theme:

```bash
cd source
npm run test
```

This checks for Ghost theme compatibility issues.

### Manual Testing Checklist

Before submitting a PR, verify:

- [ ] Homepage displays correctly with 12-day grid
- [ ] Snowflakes animation works (visible Dec-Jan)
- [ ] Dark mode toggle functions
- [ ] Locked cards show for unpublished days
- [ ] Published day posts appear in grid
- [ ] Mobile responsive layout works
- [ ] Subscribe form displays

## Pull Request Process

1. **Fork the repo** and create your branch from `main`
2. **Make your changes** with clear, descriptive commits
3. **Test thoroughly** using the checklist above
4. **Run GScan** to ensure no theme errors
5. **Submit PR** with a clear description of changes

### Commit Messages

Use clear, descriptive commit messages:

```
Add feature X for Y purpose
Fix bug where Z happened
Update documentation for W
```

## Code Style

### Handlebars Templates

- Use `{{#foreach}}` instead of `{{#each}}` (Ghost requirement)
- Add comments for complex logic
- Keep partials focused and reusable

### CSS

- Follow existing naming conventions
- Add new styles at the end of relevant sections
- Use CSS variables for colors and fonts

### JavaScript

- Use IIFE pattern for encapsulation
- Keep functions small and focused
- Add comments for non-obvious logic

## File Structure

```
source/
├── assets/css/screen.css    # Main styles
├── assets/js/               # JavaScript modules
├── partials/
│   ├── shipmas/             # 12 Days components
│   └── components/          # Shared components
└── *.hbs                    # Page templates
```

## Questions?

- Open an issue for bugs or feature requests
- Check existing issues before creating new ones

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
