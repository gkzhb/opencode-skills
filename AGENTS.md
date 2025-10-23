# Agent Guidelines for opencode-skills

## Build/Test Commands
- `bun run build` - Compile TypeScript to dist/
- `bun run typecheck` - Run TypeScript type checking without emitting files
- `bun run prepublishOnly` - Build before publishing (runs build)

## Code Style
- **TypeScript**: ES2022 modules, bundler resolution, strict mode disabled
- **Formatting**: No semicolons (Prettier config: `{ "semi": false }`)
- **Imports**: Use ES modules with explicit `.js` extensions in compiled output
- **Error Handling**: Log errors with context, continue gracefully on skill parsing failures
- **Naming**: 
  - Functions: camelCase (`generateToolName`, `parseSkill`)
  - Constants: UPPER_CASE for schemas (`SkillFrontmatterSchema`)
  - Tools: snake_case with `skills_` prefix (`skills_brand_guidelines`)

## Key Patterns
- Use `zod` for validation with descriptive error messages
- Parse YAML frontmatter with `gray-matter`
- Generate tool names from relative paths using underscores
- Return structured skill data with execution instructions
- Handle missing directories gracefully with warnings
- **Package Manager**: Use Bun (package-lock.json removed, bun.lockb created)