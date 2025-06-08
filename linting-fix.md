# /project:lint-fix - Comprehensive Code Quality Fix

Run comprehensive linting and auto-fix code quality issues across the Dental Practice Analytics Dashboard codebase.

## Usage

```
/project:lint-fix
```

## Implementation

You are an expert code quality engineer for the Dental Practice Analytics Dashboard project. When the user runs `/project:lint-fix`, execute the following steps:

### Step 1: Pre-flight Check

1. **Verify Clean Working Directory**
   
   ```bash
   git status --porcelain
   ```
- Check for uncommitted changes
- Warn if working directory is not clean
- Suggest stashing changes if needed

### Step 2: Package Manager Verification

1. **Ensure pnpm Consistency**
   
   ```bash
   pnpm install --frozen-lockfile
   ```
- Verify pnpm lockfile integrity
- Ensure all dependencies are installed
- Check for package manager consistency

### Step 3: TypeScript Compilation Check

1. **Pre-lint TypeScript Validation**
   
   ```bash
   pnpm type-check
   ```
- Check for TypeScript compilation errors
- Validate type definitions
- Ensure no blocking type issues before formatting

### Step 4: Biome Formatting and Linting

1. **Apply Biome Formatting**
   
   ```bash
   pnpm biome format --write .
   ```
- Format all TypeScript, JavaScript, JSON, and CSS files
- Standardize quotes, semicolons, and spacing
- Fix line length issues (consistent with Biome config)
- Ensure consistent indentation

### Step 5: Biome Linting with Auto-fix

1. **Fix Linting Issues with Biome**
   
   ```bash
   pnpm biome lint --apply .
   ```
- Sort imports by category (React, external libraries, internal modules)
- Remove unused imports and variables
- Fix auto-fixable linting issues
- Apply performance and correctness fixes
- Organize import groups with proper spacing

### Step 6: Biome Full Check and Fix

1. **Comprehensive Biome Check**
   
   ```bash
   pnpm biome check --apply .
   ```
- Run both formatting and linting in one command
- Apply all safe fixes automatically
- Ensure consistent code style across the project

### Step 7: Component and Hook Validation

1. **React/Next.js Specific Checks**
   
   ```bash
   pnpm biome lint --apply . --reporter=pretty
   ```
- Validate React Hook dependencies
- Check component prop types
- Ensure proper component naming conventions
- Verify custom hook patterns

### Step 8: Database Schema Validation

1. **Prisma Schema Check**
   
   ```bash
   pnpm prisma validate
   pnpm prisma format
   ```
- Validate Prisma schema syntax
- Format schema file consistently
- Check for relationship integrity

### Step 9: Final Type Checking

1. **Complete TypeScript Validation**
   
   ```bash
   pnpm type-check
   ```
- Re-run type checking after all fixes
- Ensure no type regressions introduced
- Validate component prop types

### Step 10: Report Generation

Generate comprehensive quality report:

```
🔧 Dental Dashboard Code Quality Fix Report

✅ FIXES APPLIED:
├── Biome formatting: 34 files reformatted  
├── Import organization: 28 files updated
├── Biome lint auto-fixes: 47 issues resolved
├── Performance optimizations: 12 components updated
├── Prisma schema: Formatted and validated
└── Total files processed: 289

⚠️  MANUAL ATTENTION NEEDED:
├── Complex dashboard component in src/components/dashboards/MetricsOverview.tsx:156
├── Missing error boundary in src/app/(dashboard)/layout.tsx:45
├── Unused Google Sheets helper in src/lib/google/sheets-helpers.ts:23
└── Component missing prop validation in src/components/charts/LineChart.tsx:34

🎯 QUALITY SCORE: 94.7% (excellent)

📁 Run `git diff` to review all changes
💡 Consider running `pnpm test` to ensure no regressions
```

## Error Handling

### Common Issues

- **Import Conflicts**: Resolve circular dependencies in services
- **Type Errors**: Point to specific component prop issues
- **Prisma Schema Errors**: Validate relationship definitions
- **Next.js Routing Issues**: Check dynamic route patterns
- **Google API Type Conflicts**: Resolve external API type mismatches

### Recovery Steps

- If auto-fixes break builds: `git checkout -- .` and fix manually
- If type checking fails: Run `pnpm type-check --noEmit` for detailed errors
- If tests break: Run `pnpm test --no-coverage` for faster feedback
- If Prisma schema invalid: Check relationship syntax and field types

## Quality Gates

### Must Pass

- [ ] All auto-fixable Biome issues resolved
- [ ] Biome formatting consistent across all files
- [ ] No TypeScript compilation errors
- [ ] Prisma schema validates successfully
- [ ] Biome lint rules pass

### Should Pass (Warnings)

- [ ] No unused imports or variables
- [ ] Component prop types properly defined
- [ ] React Hook dependencies correct
- [ ] No complex functions (>20 lines)
- [ ] API route handlers properly typed

### Dental Dashboard Specific

- [ ] Chart components properly typed
- [ ] Dashboard widgets follow naming conventions
- [ ] Google Sheets integration types consistent
- [ ] Database entities properly mapped
- [ ] KPI calculation functions well-documented

## Output Examples

### Successful Fix

```
🎉 DENTAL DASHBOARD CODE QUALITY IMPROVED!

✅ All auto-fixes applied successfully
📏 Biome formatting: 100% compliant
🔍 Biome linting: No issues found
🏷️  TypeScript: All types valid
🗄️  Prisma: Schema formatted and valid

Ready for commit! Use:
git add -A && git commit -m "style: fix code quality issues across dashboard"
```

### Issues Requiring Attention

```
⚠️  PARTIAL SUCCESS - MANUAL FIXES NEEDED

✅ Auto-fixes applied: 67 issues
❌ Manual fixes needed: 4 issues

Priority fixes:
1. Simplify MetricsOverview component (too complex)
2. Add error boundary to dashboard layout
3. Remove unused Google Sheets helper function
4. Add prop validation to LineChart component

Run these commands for specific fixes:
# Check specific component
pnpm type-check src/components/dashboards/MetricsOverview.tsx
# Test specific functionality
pnpm test src/components/charts/LineChart.test.tsx
```

### Critical Issues Found

```
🚨 CRITICAL ISSUES DETECTED

❌ Build blocking issues found:
1. TypeScript error in src/lib/google/api.ts:45
   - Missing return type annotation
2. Circular dependency detected:
   - src/services/metrics.ts ↔ src/services/calculations.ts
3. Invalid Prisma schema:
   - Missing required field in MetricValues model

🔧 Quick fixes:
pnpm type-check --noEmit  # See all type errors
pnpm prisma validate     # Check schema issues
```

## Package.json Scripts Reference

Ensure your `package.json` includes these quality scripts:

```json
{
  "scripts": {
    "lint": "biome lint .",
    "lint:fix": "biome lint --apply .",
    "format": "biome format --write .",
    "format:check": "biome format .",
    "check": "biome check .",
    "check:fix": "biome check --apply .",
    "type-check": "tsc --noEmit",
    "quality:check": "pnpm type-check && pnpm check",
    "quality:fix": "pnpm check:fix && pnpm type-check"
  }
}
```

## Biome Configuration

Recommended `biome.json` for the dental dashboard:

```json
{
  "$schema": "https://biomejs.dev/schemas/1.4.1/schema.json",
  "organizeImports": {
    "enabled": true
  },
  "linter": {
    "enabled": true,
    "rules": {
      "recommended": true,
      "style": {
        "useImportType": "error",
        "useExportType": "error"
      },
      "correctness": {
        "useExhaustiveDependencies": "error"
      },
      "suspicious": {
        "noExplicitAny": "warn"
      }
    }
  },
  "formatter": {
    "enabled": true,
    "indentStyle": "space",
    "indentWidth": 2,
    "lineWidth": 100
  },
  "files": {
    "include": ["src/**/*", "app/**/*", "pages/**/*"],
    "ignore": ["node_modules", ".next", "dist", "build"]
  }
}
```

## Context

- Uses Biome for fast, unified linting and formatting
- Uses TypeScript compiler for type checking
- Follows dental dashboard specific conventions
- Integrates with Prisma schema validation
- Maintains Google Sheets integration code quality
- Supports multi-phase development workflow
- Provides single-tool solution for code quality