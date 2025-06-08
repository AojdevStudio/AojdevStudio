# /project:check-health - Dental Dashboard Project Health Assessment

Comprehensive health check of the Dental Practice Analytics Dashboard including code quality, test coverage, dependencies, documentation, and system integration.

## Usage

```
/project:check-health
```

## Implementation

You are an expert DevOps engineer for the Dental Practice Analytics Dashboard project. When the user runs `/project:check-health`, execute the following comprehensive assessment:

### Step 1: Git Repository Health

1. **Repository Status**
   
   ```bash
   git status
   git log --oneline -5
   git branch -vv
   ```
- Check working directory status
- Verify branch alignment with remote
- Check recent commit activity
1. **Branch Analysis**
- Verify on main branch
- Check if ahead/behind remote
- Identify any untracked files

### Step 2: Code Quality Assessment

1. **Linting and Formatting**
   
   ```bash
   pnpm lint
   pnpm type-check
   pnpm format:check
   ```
- Count ESLint issues by severity
- Check TypeScript compilation errors
- Verify Prettier formatting compliance
1. **Test Suite Health**
   
   ```bash
   pnpm test --passWithNoTests --watchAll=false
   pnpm test --coverage --watchAll=false
   ```
- Count total tests
- Check test coverage percentage
- Verify component and integration tests

### Step 3: Dependency Analysis

1. **Dependency Health**
   
   ```bash
   pnpm audit
   pnpm outdated
   pnpm ls --depth=0
   ```
- Check for security vulnerabilities
- Identify outdated dependencies
- Verify dependency tree health
1. **Next.js Build Health**
   
   ```bash
   pnpm build
   pnpm lint:next
   ```
- Verify successful production build
- Check for Next.js specific issues
- Validate bundle size and performance

### Step 4: Database & Integration Health

1. **Database Schema Health**
   
   ```bash
   pnpm prisma validate
   pnpm prisma generate --dry-run
   pnpm db:status
   ```
- Validate Prisma schema
- Check database connection
- Verify migration status
1. **Google Sheets Integration**
   
   ```bash
   node -e "console.log('Testing Google API...')"
   # Custom health check for Google API connectivity
   ```
- Verify Google API credentials
- Test OAuth flow functionality
- Check Sheets API rate limits

### Step 5: Performance Metrics

1. **Build Performance**
   
   ```bash
   time pnpm build
   pnpm analyze
   ```
- Check build time
- Analyze bundle size
- Identify performance bottlenecks
1. **Test Performance**
   
   ```bash
   pnpm test --verbose --detectOpenHandles
   ```
- Monitor test execution time
- Check for memory leaks
- Validate async operations

### Step 6: Documentation Health

1. **Documentation Coverage**
- Check README.md currency
- Verify API documentation
- Validate component documentation
- Check deployment guides
1. **Code Documentation**
- Verify JSDoc coverage
- Check TypeScript interface documentation
- Validate component prop documentation

### Step 7: Project Metrics

1. **Code Statistics**
   
   ```bash
   find src -name "*.ts" -o -name "*.tsx" | xargs wc -l
   find src/components -name "*.tsx" | wc -l
   find src/app/api -name "*.ts" | wc -l
   ```
- Lines of code trends
- Component count
- API endpoint count

## Health Report Format

Generate comprehensive health dashboard:

```
🏥 Dental Dashboard Project Health Report

📊 OVERALL HEALTH: 🟢 EXCELLENT (94/100)

🗂️  GIT REPOSITORY
✅ Clean working directory
✅ Up to date with origin/main
✅ Recent commit activity (8 commits this week)

🔍 CODE QUALITY  
✅ ESLint: 0 errors, 1 warning
✅ TypeScript: No compilation errors
✅ Prettier: All files formatted
⚠️  Complex components: 2 need refactoring

🧪 TEST SUITE
✅ Total tests: 156 
✅ Coverage: 87.3% (components: 92%, utils: 95%)
✅ Component tests: All passing
⚡ Performance: 12.4s (excellent)

📦 DEPENDENCIES
✅ Security: No vulnerabilities
✅ pnpm lockfile: Consistent
⚠️  Outdated: 3 minor updates available
✅ Bundle size: 2.1MB (within target)

🗄️  DATABASE & INTEGRATIONS
✅ Prisma schema: Valid
✅ Database connection: Healthy
✅ Google Sheets API: Connected
⚠️  Migration pending: 1 new migration

🏗️  BUILD HEALTH
✅ Production build: Successful
✅ Build time: 45s (good)
✅ Next.js optimizations: Applied
✅ Bundle analysis: No critical issues

📖 DOCUMENTATION
✅ README: Current
✅ Component docs: 89% coverage
⚠️  API documentation: Needs update
✅ Deployment guide: Complete

📈 PROJECT METRICS
├── Source code: 8,943 lines
├── Components: 47 components
├── API routes: 23 endpoints
├── Pages: 12 pages
└── Test coverage: 87.3%

🎯 RECOMMENDATIONS:
1. Run pending database migration
2. Update API documentation
3. Refactor complex dashboard components
4. Update @types/node to latest version

🏆 PROJECT STATUS: Ready for Phase 2 deployment!
```

## Health Scoring

### Excellent (90-100)

- All builds pass
- High test coverage (>85%)
- No security vulnerabilities
- Database schema valid
- Google integration working

### Good (75-89)

- Minor build warnings
- Good test coverage (>75%)
- No critical vulnerabilities
- Database connected
- Most integrations working

### Needs Attention (60-74)

- Build issues present
- Adequate test coverage (>65%)
- Minor security concerns
- Database connection issues
- Integration problems

### Critical (<60)

- Build failures
- Low test coverage (<65%)
- Security vulnerabilities
- Database offline
- Major integration failures

## Dental Dashboard Specific Checks

### Dashboard Components Health

- Chart component functionality
- KPI widget responsiveness
- Filter system performance
- Data visualization accuracy

### Google Sheets Integration Health

- OAuth token validity
- API quota usage
- Data sync status
- Column mapping accuracy

### Database Performance

- Query performance metrics
- Connection pool health
- Migration status
- Data integrity checks

## Context

- Monitors multi-phase development progress
- Tracks integration health with external services
- Ensures dashboard performance standards
- Validates data pipeline integrity
- Supports phase-based deployment decisions

## Package.json Scripts Reference

Ensure your `package.json` includes these health check scripts:

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "lint:fix": "next lint --fix",
    "type-check": "tsc --noEmit",
    "format": "prettier --write .",
    "format:check": "prettier --check .",
    "test": "jest",
    "test:watch": "jest --watch",
    "test:coverage": "jest --coverage",
    "analyze": "cross-env ANALYZE=true next build",
    "db:generate": "prisma generate",
    "db:push": "prisma db push",
    "db:migrate": "prisma migrate dev",
    "db:status": "prisma migrate status",
    "db:studio": "prisma studio"
  }
}
```