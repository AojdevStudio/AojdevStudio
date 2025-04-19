<!-- === WATCHER HEADER START === -->
<!-- File: Claude/project-instructions/dev-starter-kit.md -->
<!-- Managed by file watcher -->
<!-- === WATCHER HEADER END === -->
# Modern Web Development Starter Kit Creator
## Powered by Claude & Desktop Commander MCP

### Introduction
This Claude project serves as an intelligent project scaffolding system that eliminates the complexity of setting up new web development projects. Instead of manually piecing together various initialization commands or remembering different scaffolding tools for different frameworks, you can simply describe your desired project, and Claude will automatically generate a complete, properly structured project following current best practices.

### Key Benefits
- **Instant Setup**: Generate complete project structures in seconds
- **Best Practices Built-in**: Automatically includes current industry standards and patterns
- **Framework Agnostic**: Works with any modern web framework (Next.js, React, Vue, Angular, etc.)
- **Modular by Design**: Creates clean, maintainable project structures
- **Cursor-Optimized**: Includes proper Cursor editor integration and rules
- **Always Current**: Uses latest stable versions of technologies
- **Repeatable**: Create consistent project structures across your team
- **Time-Saving**: Avoid hours of manual setup and configuration

### How to Use
1. Start a new Claude project
2. Add these instructions
3. Tell Claude what type of project you want to build
4. Let Desktop Commander MCP handle the scaffolding
5. Get a production-ready project structure instantly

---

## Project Overview
Create a standardized, up-to-date starter kit generator for web development projects that follows current best practices, uses the latest stable versions of all technologies, and includes proper Cursor editor integration.

## MCP Tools Utilization

### Sequential Thinking MCP
- Break down complex tasks into logical steps
- Maintain context throughout the implementation process 
- Evaluate and revise approaches as needed
- Use for planning directory structures and implementation sequence

### Web Search MCPs
- brave_web_search - For general research on best practices and configurations
- tavily-search - For in-depth technical documentation and examples
- tavily-extract - To analyze specific documentation pages or GitHub repositories
- Always search for up-to-date information before implementing any component

### File System MCPs
- Use directory creation tools to establish proper folder structure
- Create files with appropriate permissions and encoding
- Implement proper nesting according to framework best practices
- Generate configuration files with correct syntax and formatting

### Memory/Knowledge Graph MCP
- Search the knowledge graph for previous successful implementations
- Retrieve best practices from past similar projects
- Learn from previous iterations to improve quality
- Store new learnings for future reference

### Code Execution MCP
- Use REPL when appropriate to validate configurations
- Test snippets before including them in the template
- Verify dependency compatibility

## Process Flow

### 1. Core Technology Selection
- Identify the primary framework/library (e.g., Next.js, React, Vue, Angular)
- Determine complementary technologies based on industry best practices
- Select appropriate styling approach based on framework recommendations
- Include recommended testing, state management, and developer tools

### 2. Research Phase
Use brave_web_search or tavily-search to find:
- Latest stable versions of all selected technologies
- Current best practices for project structure
- Recommended configuration patterns
- Real-world production templates from reputable sources
- Framework-specific optimization techniques

### 3. Cursor Rules Integration
Research Cursor editor integration at cursor.directory
Create a .cursor/rules directory with appropriate .mdc files for:
- Framework-specific coding standards
- Project structure guidelines
- Component patterns
- Best practices specific to the chosen technology stack

Additional requirements:
- Generate rules that enhance code consistency and developer experience
- Include comments explaining the purpose of each rule

### 4. Modular Architecture Design
- Implement a scalable modular architecture:
  - Core modules (shared functionality)
  - Feature modules (isolated business logic)
  - UI modules (presentation components)
  - Data modules (state management, API integration)
  - Utility modules (shared helpers)

- Define clear module boundaries:
  - Public interfaces for module communication
  - Explicit dependency declarations
  - Clear separation of concerns
  - Encapsulated implementation details

- Create standardized module structure:
  ```
  src/
  ├── modules/
  │   ├── core/
  │   │   ├── interfaces/
  │   │   ├── services/
  │   │   └── types/
  │   ├── features/
  │   │   ├── feature-1/
  │   │   │   ├── components/
  │   │   │   ├── hooks/
  │   │   │   ├── services/
  │   │   │   ├── types/
  │   │   │   └── index.ts
  │   │   └── feature-2/
  │   ├── ui/
  │   │   ├── components/
  │   │   ├── layouts/
  │   │   └── themes/
  │   └── shared/
  │       ├── utils/
  │       ├── constants/
  │       └── types/
  ```

- Implement module communication patterns:
  - Event bus for cross-module communication
  - Dependency injection for service sharing
  - State management for data sharing
  - Module registry for dynamic loading

### 5. Best Practice Structure Implementation
- Create directory structure following modular patterns:
  - Separate concerns into distinct modules
  - Group related functionality
  - Maintain consistent module structure
  - Follow framework-specific module conventions

- Implement module isolation:
  - Each module has its own package.json (if needed)
  - Independent versioning capability
  - Separate test configurations
  - Module-specific documentation

- Set up module development workflow:
  - Module-level build scripts
  - Independent testing capabilities
  - Module-specific linting rules
  - Documentation generation

### 6. Configuration Generation
- Create package.json with proper dependencies and versions
- For JavaScript/TypeScript projects:
  - Configure PNPM as the package manager
  - Include pnpm-lock.yaml in version control
  - Set up Biome with recommended configurations:
    - Configure linting rules in biome.json
    - Configure formatting rules in biome.json
    - Configure type checking rules in biome.json
    - Set up Biome scripts in package.json for lint, format, and type checking
  - Ensure Biome is the sole source of:
    - Code formatting
    - Linting
    - Type checking
- For Python projects:
  - Set up UV for dependency management
  - Include requirements.txt and .uv lockfile
  - Configure UV with optimal settings
- Generate appropriate config files (tsconfig.json, next.config.js, etc.)
- Configure build process with optimal settings
- Add scripts for common development tasks
- Generate module-specific configurations
- Set up module resolution in tsconfig.json
- Configure module aliases for clean imports
- Set up module-level testing configurations

### 7. Example Implementation
- Create sample components demonstrating best practices
- Include example pages/routes with proper patterns
- Provide utility functions that showcase recommended approaches
- Add comments explaining the rationale behind implementation choices
- Create example modules demonstrating:
  - Module communication patterns
  - Feature module implementation
  - Core module setup
  - UI module organization
  - Shared module usage

### 8. Documentation
Generate comprehensive README.md explaining:
- Project structure and organization principles
- Available commands and their purposes
- Best practices for extending the template
- How to use the Cursor integration features
- Links to official documentation
- Document module architecture:
  - Module organization principles
  - Communication patterns
  - Dependency management
  - Module development guidelines
  - Testing strategies per module type

### 9. Quality Assurance
- Validate configurations for syntax errors
- Verify compatibility between dependencies
- Check for security advisories on chosen packages
- Ensure Cursor rules are properly formatted

## Deliverables
- Complete file structure following best practices for the chosen framework
- .cursor/rules directory with properly formatted .mdc files
- Well-documented example code and configuration files
- Comprehensive README with getting started guide
- Optimized default configurations

## Implementation Instructions
- Use sequential thinking to break down each step
- Research each technology component before implementing
- Prioritize Cursor editor integration for improved developer experience
- Follow framework-specific conventions and standards
- Include helpful comments in configuration and example files
- Ensure the template is immediately usable with minimal setup

### Package Manager Requirements
- **Python Projects**: 
  - Must use UV (uv) as the package manager
  - UV must be locked to ensure consistent dependency management
  - No other Python package managers are permitted

- **JavaScript/TypeScript Projects**:
  - Must use PNPM as the package manager
  - PNPM must be locked to ensure consistent dependency management
  - No other JavaScript/TypeScript package managers are permitted (no npm or yarn)

### Mandatory Development Tools
- **Biome Integration**:
  - Required for all JavaScript/TypeScript projects
  - Must be configured for type checking
  - Should be integrated with the project's build and validation processes
  - Configuration should follow best practices for the specific project type

### Licensing Requirements
- Project initialization must prompt for license selection
- Must include a properly formatted LICENSE file
- License information must be correctly reflected in package.json (for JS/TS projects)
- License must be documented in the project README.md
- Must validate that chosen license is compatible with all dependencies
