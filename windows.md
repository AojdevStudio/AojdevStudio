function gitflow {
    $folder = "prompt-library"
    if (-not (Test-Path $folder)) {
        New-Item -ItemType Directory -Path $folder | Out-Null
    }

    Set-Content "$folder/gitflow-setup.xml" @'
<prompts>
  <prompt id="gitflow-setup">
    <description>Initialize the complete Git Flow branch structure.</description>
    <instructions>
      <![CDATA[
      You are a Git assistant. Initialize the complete Git Flow branch structure:
      
      1. Ensure you're on main branch:
         git checkout main
      
      2. Create and switch to develop branch:
         git checkout -b develop
      
      3. Push develop branch to remote:
         git push -u origin develop
      
      4. Return to main (optional):
         git checkout main
      
      🎉 Git Flow structure initialized with main and develop branches!
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/gitflow-start-develop.xml" @'
<prompts>
  <prompt id="gitflow-start-develop">
    <description>Initialize Git Flow by starting with the develop branch.</description>
    <instructions>
      <![CDATA[
      You are a Git assistant. Initialize the project using the `develop` branch as the default working branch.

      1. Create and switch to develop:
         git checkout -b develop

      2. Set develop as the upstream:
         git push -u origin develop

      🎉 Now you're working safely in `develop`.
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/gitflow-create-feature.xml" @'
<prompts>
  <prompt id="gitflow-create-feature">
    <description>Create a feature branch from develop and merge it back when complete.</description>
    <instructions>
      <![CDATA[
      You are a Git assistant. Follow this feature branch workflow:

      1. Start a new feature branch (replace `user-auth` with your feature name):
         git checkout -b feature/user-auth develop

      2. Do your work and commit changes:
         git add .
         git commit -m "feat: implement user auth"

      3. Push the feature branch:
         git push -u origin feature/user-auth

      4. When ready, merge it into develop:
         git checkout develop
         git merge feature/user-auth
         git push

      5. Optionally delete the remote and local feature branch:
         git branch -d feature/user-auth
         git push origin --delete feature/user-auth
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/gitflow-promote-to-main.xml" @'
<prompts>
  <prompt id="gitflow-promote-to-main">
    <description>Merge stable develop branch into main to prepare for production.</description>
    <instructions>
      <![CDATA[
      You are a Git assistant. When the `develop` branch is stable and ready for production, follow these steps:

      1. Switch to main:
         git checkout main

      2. Merge changes from develop:
         git merge develop

      3. Push main:
         git push

      🎯 Your production-ready code is now in `main`.
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/gitflow-tag-main-release.xml" @'
<prompts>
  <prompt id="gitflow-tag-main-release">
    <description>Create a version tag on the main branch.</description>
    <instructions>
      <![CDATA[
      You are a release assistant. After merging into `main`, tag the release for tracking and deployment.

      1. Create a new tag (example: v1.0.0):
         git tag v1.0.0

      2. Push the tag to GitHub:
         git push origin v1.0.0

      ✅ Release v1.0.0 is now tagged and available on GitHub.
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/gitflow-auto-commit.xml" @'
<prompts>
  <prompt id="gitflow-auto-commit">
    <description>Auto-generate and push a commit message using aicommits.</description>
    <instructions>
      <![CDATA[
      You are a Git assistant. Automate commits with AI.

      ✅ Step 1: Stage your changes:
      git add .

      ✅ Step 2: Auto-generate a commit message using GPT:
      aicommits

      ✅ Step 3: Push to the current branch:
      git push origin $($(git rev-parse --abbrev-ref HEAD))

      💡 Tip: You must have your OpenAI key stored in the environment variable AICOMMIT_OPENAI_KEY.
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/gitflow-fetch.xml" @'
<prompts>
  <prompt id="gitflow-fetch">
    <description>Fetch and update all branches from remote repository.</description>
    <instructions>
      <![CDATA[
      You are a Git assistant. Keep your local branches in sync with remote:

      1. Fetch all branches and prune stale ones:
         git fetch --all --prune

      2. Pull latest changes for current branch:
         git pull

      3. Update develop (if exists):
         git checkout develop
         git pull
         
      4. Update main:
         git checkout main
         git pull

      ✨ All branches are now up to date!
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/repomix-pack-ai-optimized.xml" @'
<prompts>
  <prompt id="repomix-pack-ai-optimized">
    <description>Pack specific folders with AI optimizations using @repomix-pack-ai-optimized [folder_path]</description>
    <instructions>
      <![CDATA[
      You are a Repomix CLI expert. When called with @repomix-pack-ai-optimized [folder_path], analyze and pack the specified folder:

      📂 FOLDER ARGUMENT HANDLING:
      - If no folder specified: Pack current directory
      - If folder specified: Pack that specific folder
      - Examples:
        @repomix-pack-ai-optimized src/components
        @repomix-pack-ai-optimized my-project/
        @repomix-pack-ai-optimized .  (current directory)

      1. 🎯 Analyze Target Directory
         # First, analyze the specified directory
         ls -R {folder_path}  # List contents recursively
         find {folder_path} -type f  # Get all files

      2. 🎨 Smart Packing Strategy
         # Choose the best strategy based on folder content:
         
         a) For source code folders:
         repomix {folder_path} --compress --include "**/*.{js,jsx,ts,tsx,py,java,cpp,cs,go,rs,rb,php,swift,kt}" --output ai-source.xml

         b) For web folders:
         repomix {folder_path} --include "**/*.{html,css,scss,less,vue,svelte}" --output ai-web.xml

         c) For documentation folders:
         repomix {folder_path} --include "**/*.{md,txt,rst,adoc,wiki}" --style markdown --output ai-docs.md

         d) For mixed content folders:
         repomix {folder_path} --compress --remove-comments --output-show-line-numbers --output ai-context.xml

      3. 🔍 Content-Aware Options
         # Apply these based on folder content:
         
         For Web Development:
         repomix {folder_path} --include "**/*.{html,css,js,ts,jsx,tsx,vue,svelte}" --compress --output web-context.xml

         For Backend Development:
         repomix {folder_path} --include "**/*.{py,java,go,rs,rb,php}" --compress --output backend-context.xml

         For Mobile Development:
         repomix {folder_path} --include "**/*.{swift,kt,java,xml}" --output mobile-context.xml

         For Documentation:
         repomix {folder_path} --include "**/*.{md,rst,txt,adoc}" --style markdown --output docs-context.md

         For Configuration:
         repomix {folder_path} --include "**/*.{json,yaml,yml,toml,ini}" --output config-context.xml

         For Shell Scripts:
         repomix {folder_path} --include "**/*.{sh,bash,zsh,fish,ps1}" --output scripts-context.xml

      4. 🛡️ Safety Checks
         # Before processing:
         - Check for .env files
         - Look for sensitive data
         - Verify .gitignore rules
         - Estimate output size
         - Scan for credentials or tokens
         - Check for database connection strings

      💡 Pro Tips:
      - Use --compress for large folders
      - Add --output-show-line-numbers for better reference
      - Use --copy to quickly paste into AI tools
      - Check output size before using with AI
      - Combine multiple include patterns for comprehensive coverage

      ✅ Best Practice Workflow:
      1. Analyze folder content type
      2. Choose appropriate packing strategy
      3. Apply safety checks
      4. Generate optimized output
      5. Verify output before AI use

      Example Commands:
      # For a Python backend:
      repomix src/backend --compress --include "**/*.{py,sql}" --output ai-backend.xml

      # For a full-stack app:
      repomix src --compress --include "**/*.{py,js,html,css,sql}" --output ai-fullstack.xml

      # For a mobile app:
      repomix app --compress --include "**/*.{swift,kt,java,xml}" --output ai-mobile.xml

      # For infrastructure code:
      repomix infra --include "**/*.{tf,yaml,sh}" --output ai-infra.xml

      Remember: I'll analyze the folder content and choose the most appropriate command based on what I find!
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/task-atomicity.xml" @'
<prompts>
  <prompt id="task-atomicity">
    <description>Break down tasks into atomic units and implement progressively using MCP tools.</description>
    <instructions>
      <![CDATA[
      You are a Task Breakdown assistant. Use these MCP tools for atomic and progressive task management:

      1. Task Atomicity Analysis:
         📋 Use Sequential MCP Breakdown:
            mcp_sequentialthinking_tools
            - Define smallest unit of work
            - Map file paths and dependencies
            - List precise inputs/outputs
            - Track progress through steps

         🔍 Validation Questions:
            mcp_think_think
            - "Is this the smallest possible unit?"
            - "Are all dependencies identified?"
            - "Is the scope clearly defined?"
            - "What could go wrong?"

      2. Progressive Implementation Plan:
         📈 Use MCP Think for Each Stage:
            1. Core Functionality:
               mcp_think_think "Core Implementation Analysis"
               - Minimal working implementation
               - Critical paths
               - Deferrable components

            2. Edge Cases:
               mcp_think_think "Edge Case Analysis"
               - Boundary conditions
               - Error scenarios
               - Required validations

            3. Optimization:
               mcp_think_think "Optimization Analysis"
               - Performance bottlenecks
               - Enhancement opportunities
               - Refactoring needs

         ✅ Validation Strategy:
            1. Global Search Validation:
               mcp_brave_brave_web_search
               - Search for similar implementations
               - Find common pitfalls
               - Discover best practices
               - Verify approach validity

            2. Local Search Validation:
               mcp_brave_brave_local_search
               - Find relevant local examples
               - Check existing patterns
               - Verify consistency

            3. Documentation Validation:
               mcp_context7_resolve-library-id
               - Identify relevant library documentation
               - Verify package versions
               - Check compatibility

               mcp_context7_get-library-docs
               - Review official documentation
               - Validate implementation approach
               - Check for known limitations
               - Find recommended patterns

      💡 Remember:
      - Use mcp_think_get_thoughts to review your analysis
      - Combine sequential thinking with brave search for comprehensive validation
      - Document all decisions in the thought chain
      - Keep atomic units independently testable
      - Verify against official documentation using Context7
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/error-loop-analysis.xml" @'
<prompts>
  <prompt id="error-loop-analysis">
    <description>Systematic approach to break out of error loops and prevent recurring issues using MCP tools.</description>
    <instructions>
      <![CDATA[
      You are an Error Analysis assistant. Use these MCP tools to systematically analyze and resolve error loops:

      1. Error Pattern Recognition:
         📊 Document Error Pattern Using Memory:
            mcp_memory_create_entities [{
              "name": "error_pattern",
              "entityType": "error",
              "observations": [
                "Error message: {exact_error}",
                "Occurrence count: {count}",
                "Trigger changes: {changes}",
                "Constants: {constants}"
              ]
            }]

         🔄 Analyze Pattern with MCP Think:
            mcp_think_think "Error Pattern Analysis"
            - "What patterns emerge from the error messages?"
            - "Are there hidden correlations between occurrences?"
            - "What environmental factors coincide with errors?"
            - "What successful states can we learn from?"

      2. Root Cause Analysis:
         🔍 Sequential Analysis of Sources:
            mcp_sequentialthinking_tools
            - Break down potential causes
            - Analyze each source systematically
            - Track investigation progress
            - Document findings

         📚 Research Similar Issues:
            mcp_brave_brave_web_search "specific_error_message implementation issues"
            - Search for known solutions
            - Find common pitfalls
            - Identify best practices
            - Discover related patterns

         🔎 Search Historical Context:
            mcp_memory_search_nodes "error_pattern"
            - Review similar past errors
            - Check previous solutions
            - Identify recurring patterns
            - Compare current vs past context

      3. Validation Strategy:
         📝 Document Thinking Process:
            mcp_think_get_thoughts
            - Review analysis chain
            - Validate assumptions
            - Check logical flow
            - Identify gaps in reasoning

         📖 Check Library Documentation:
            mcp_context7_resolve-library-id
            mcp_context7_get-library-docs
            - Review official documentation
            - Check known issues
            - Find recommended practices
            - Verify implementation details

      4. Prevention Framework:
         🛡️ Implementation Safeguards:
            mcp_think_think "Prevention Strategy"
            - Design error boundaries
            - Plan circuit breakers
            - Define timeout strategies
            - Structure retry logic

         📈 Monitoring Implementation:
            mcp_memory_create_entities [{
              "name": "error_monitoring",
              "entityType": "monitor",
              "observations": [
                "Error thresholds: {thresholds}",
                "Alert conditions: {conditions}",
                "Frequency patterns: {patterns}",
                "Performance metrics: {metrics}"
              ]
            }]

      💡 Remember:
      - Use mcp_think_get_thoughts regularly to review your analysis
      - Create memory entities to track patterns and decisions
      - Combine brave search with library docs for comprehensive research
      - Document all assumptions and validations in the thought chain
      - Keep the sequential thinking process focused and systematic
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Set-Content "$folder/install-repomix.xml" @'
<prompts>
  <prompt id="install-repomix">
    <description>Install Repomix and configure it for use.</description>
    <instructions>
      <![CDATA[
      You are a Repomix assistant. Install Repomix and configure it for use:

      1. Download and install Repomix:
         https://github.com/your-project/repomix

      2. Configure Repomix:
         - Set up your project repository
         - Configure Repomix settings

      🎉 Repomix is now installed and configured!
      ]]>
    </instructions>
  </prompt>
</prompts>
'@

    Write-Host "✅ GitFlow prompts added to 'prompt-library/'"
}

function commit { code prompt-library/gitflow-auto-commit.xml }
function feature { code prompt-library/gitflow-create-feature.xml }
function promote { code prompt-library/gitflow-promote-to-main.xml }
function develop { code prompt-library/gitflow-start-develop.xml }
function tag { code prompt-library/gitflow-tag-main-release.xml }
function setup { code prompt-library/gitflow-setup.xml }
function fetch { code prompt-library/gitflow-fetch.xml }
function task { code prompt-library/task-atomicity.xml }
function error { code prompt-library/error-loop-analysis.xml }
function repomix { code prompt-library/install-repomix.xml }

Set-Alias supasetup "C:\Users\chiny\scripts\supabase-setup.ps1"

Set-Alias scripts "C:\Users\chiny\scripts\scripts.ps1"

function clean       { pnpm run clean       @args }
function dev         { pnpm run dev         @args }
function build       { pnpm run build       @args }
function start       { pnpm run start       @args }
function check-types { pnpm run check-types @args }
function commit      { pnpm run commit      @args }
function format      { pnpm run format      @args }
function lint        { pnpm run lint        @args }
function lint-fix    { pnpm run lint:fix    @args }
function knip        { pnpm run knip        @args }
function validate    { pnpm run validate    @args }
function db-status   { supabase status }
function db-start    { supabase start }
function db-stop     { supabase stop }
function db-reset    { supabase db reset --local }
function db-link     { supabase link }
function db-lint     { supabase db lint }
function db-types    { supabase gen types typescript --local > supabase/types/database.types.ts }
function db-migration{ supabase db diff || supabase migration new latest }




