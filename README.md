# AI-Assisted WordPress Development Resources

Resources and templates from the WordCamp Netherlands 2025 presentation on **"The Age of the Idea Guy: How AI is Democratizing WordPress Development"**.

## 📚 About This Repository

This repository contains battle-tested templates and configurations for building WordPress plugins with AI assistance. These resources have been used to develop the [WP AI Workflow Automation Pro](https://wpaiworkflowautomation.com/) plugin, demonstrating how AI can be effectively integrated into professional WordPress development workflows.

## 🗂️ Repository Structure

```
wordcamp-ai-development-resources/
├── kiro-templates/              # Spec-driven development templates
│   ├── how_kiro_works.md       # Overview of the Kiro methodology
│   ├── requirements_template.md # User stories and acceptance criteria
│   ├── design_template.md      # Technical architecture documentation
│   └── tasks_template.md       # Implementation task breakdown
│
├── wordpress-security/          # Security analysis configurations
│   ├── phpcs.xml               # WordPress coding standards
│   ├── phpcs-security.xml      # Security-specific PHPCS rules
│   └── psalm.xml               # Static analysis configuration
│
├── claude-agents/               # Claude Code agent definitions
│   └── wordpress-security-auditor.md  # Security audit agent
│
└── MCP Servers                  # Model Context Protocol integrations
    ├── Asana MCP Server         # Project management automation
    ├── Vibe Check MCP           # Sentiment analysis
    ├── WordPress MCP Adapter    # WordPress site management
    ├── Playwright MCP           # Browser automation
    └── GitHub MCP Server        # Repository management
```

## 🎯 What's Included

### 1. Kiro Templates (Spec-Driven Development)

The **Kiro System** is an adaptation of Amazon's spec-driven development methodology, optimized for AI-assisted development with Claude Code.

**Three-Phase Development Process:**
- **Requirements**: Define what needs to be built using user stories and EARS acceptance criteria
- **Design**: Document how it will be built with technical architecture
- **Tasks**: Break down implementation into actionable steps

**Key Benefits:**
- ✅ Structured approach prevents scope creep
- ✅ Clear requirements reduce back-and-forth
- ✅ AI assistant stays aligned with project goals
- ✅ Built-in traceability from requirements to code

**Learn More:** See `kiro-templates/how_kiro_works.md`

### 2. WordPress Security Configurations

Production-ready security tooling configurations for WordPress plugin development:

#### PHPCS (PHP CodeSniffer)
- **`phpcs.xml`**: WordPress coding standards compliance
- **`phpcs-security.xml`**: Security-specific vulnerability scanning

**Usage:**
```bash
# Install dependencies
composer require --dev squizlabs/php_codesniffer
composer require --dev wp-coding-standards/wpcs
composer require --dev automattic/phpcs-security-audit

# Run WordPress coding standards
./vendor/bin/phpcs --standard=phpcs.xml includes/ admin/

# Run security-specific scan
./vendor/bin/phpcs -d memory_limit=512M --standard=phpcs-security.xml includes/ admin/
```

#### PSALM (Static Analysis)
- **`psalm.xml`**: Type safety and taint analysis configuration

**Usage:**
```bash
# Install PSALM
composer require --dev vimeo/psalm

# Run basic static analysis
./vendor/bin/psalm

# Run taint analysis (security vulnerability detection)
./vendor/bin/psalm --taint-analysis

# Generate detailed reports
./vendor/bin/psalm --show-info=true
```

**Security Checks Performed:**
- SQL injection vulnerabilities
- XSS (Cross-Site Scripting) risks
- Unescaped output
- Missing nonce verification
- Capability check violations
- Direct file access issues

### 3. Claude Code Agent Definitions

**WordPress Security Auditor Agent** - An autonomous security review agent that:

- Runs PHPCS and PSALM automated scans
- Performs manual code review of critical sections
- Analyzes React frontend for security issues
- Generates comprehensive security audit reports
- Provides actionable remediation guidance

**When to Use:**
- Before committing changes
- After implementing new features
- When modifying database queries
- After adding REST API endpoints

**Integration:** Place this file in your project's `.claude/agents/` directory to enable automatic security audits with Claude Code.

### 4. MCP Servers (Model Context Protocol)

**MCP Servers** extend Claude Code's capabilities by connecting to external services and APIs. These servers enable Claude to interact with tools, databases, and platforms directly.

**Featured MCP Servers:**

#### 🎯 **Asana MCP Server**
Connect Claude Code to Asana for project management automation.
- **Repository**: [Asana MCP Server Documentation](https://developers.asana.com/docs/using-asanas-mcp-server)
- **Use Cases**: Task creation, project updates, workflow automation
- **Integration**: Manage tasks and projects directly from Claude Code

#### 🎭 **Vibe Check MCP Server**
Sentiment analysis and text analysis capabilities.
- **Repository**: [github.com/PV-Bhat/vibe-check-mcp-server](https://github.com/PV-Bhat/vibe-check-mcp-server)
- **Use Cases**: Content sentiment analysis, tone detection, feedback analysis
- **Integration**: Analyze user feedback, comments, and content tone

#### 🌐 **WordPress MCP Adapter**
Official WordPress MCP adapter for WordPress site management.
- **Repository**: [github.com/wordpress/mcp-adapter](https://github.com/wordpress/mcp-adapter)
- **Use Cases**: WordPress site management, content operations, plugin development
- **Integration**: Direct WordPress site interaction from Claude Code

#### 🎭 **Playwright MCP Server**
Browser automation and testing with Playwright.
- **Repository**: [github.com/microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp)
- **Use Cases**: E2E testing, browser automation, screenshot capture, web scraping
- **Integration**: Automate browser interactions and testing workflows

#### 🐙 **GitHub MCP Server**
Comprehensive GitHub integration for repository management.
- **Repository**: [github.com/github/github-mcp-server](https://github.com/github/github-mcp-server)
- **Use Cases**: Repository management, issue tracking, PR creation, code reviews
- **Integration**: Full GitHub workflow automation from Claude Code

**Why MCP Servers Matter:**

MCP servers transform Claude Code from a development assistant into a fully integrated automation platform:

- ✅ **Extend Capabilities**: Add new skills beyond core functionality
- ✅ **Service Integration**: Connect to any API or external service
- ✅ **Workflow Automation**: Chain multiple services together
- ✅ **Context Awareness**: Claude understands your entire toolchain
- ✅ **Custom Development**: Build your own MCP servers for specific needs

**Getting Started with MCP:**

1. **Install MCP server** following the repository instructions
2. **Configure in Claude Code** settings under MCP servers section
3. **Test connection** by asking Claude to interact with the service
4. **Build workflows** that leverage multiple MCP servers together

**Example Workflow:**
```
You: "Create an Asana task for the bug I just found in my WordPress plugin"
Claude: [Uses GitHub MCP to identify the bug] → [Uses WordPress MCP to verify] → [Uses Asana MCP to create task]
```

## 🚀 Getting Started

### For Kiro Templates

1. **Create `.kiro/kiro-system-templates/` in your project**
2. **Copy templates** from `kiro-templates/` directory
3. **Read `how_kiro_works.md`** to understand the methodology
4. **Start a new feature** by describing your idea to Claude Code

**Example workflow:**
```
You: "I need to add user authentication to my plugin"
Claude: "I'll guide you through the Kiro process. Let me create requirements.md..."
[Claude creates requirements → you review → approve]
[Claude creates design.md → you review → approve]
[Claude creates tasks.md → you review → approve]
[Claude implements tasks one by one with testing]
```

### For WordPress Security

1. **Copy security configs** to your WordPress plugin root
2. **Install dependencies** via composer (see commands above)
3. **Run scans** before committing code
4. **Address findings** based on severity

**Development Workflow:**
```bash
# After writing code
./vendor/bin/phpcs --standard=phpcs.xml [files]
./vendor/bin/phpcs --standard=phpcs-security.xml [files]
./vendor/bin/psalm --taint-analysis

# Fix issues, then commit
git add .
git commit -m "feat: implement feature with security validation"
```

### For Claude Agents

1. **Create `.claude/agents/` directory** in your project
2. **Copy agent definitions** you want to use
3. **Claude Code will automatically detect** and offer these agents
4. **Invoke agents** when needed (e.g., before commits)

## 📖 WordPress Security Best Practices

The security configurations enforce these critical WordPress security rules:

### Input/Output
- ✅ **Always escape output**: `echo esc_html($data)` not `echo $data`
- ✅ **Sanitize all input**: `sanitize_text_field()`, `wp_unslash()` before processing
- ✅ **Validate then sanitize**: Check format first, then clean

### Database
- ✅ **Always use prepared statements**: `$wpdb->prepare("SELECT * FROM %i WHERE id = %d", $table, $id)`
- ✅ **Never interpolate variables in SQL**: No `"SELECT * FROM $table"`

### Authentication/Authorization
- ✅ **Add nonce verification**: `wp_verify_nonce()` before processing forms
- ✅ **Check capabilities**: `current_user_can()` before sensitive operations

### File Security
- ✅ **Block direct access**: `if (!defined('ABSPATH')) exit;` at top of every PHP file
- ✅ **Use `wp_safe_redirect()`**: Never `wp_redirect()` without validation

### WordPress Specific
- ✅ **Follow function preferences**: `rawurlencode()` over `urlencode()`
- ✅ **Use WordPress functions**: `wp_remote_get()` over `curl`

## 🔧 Development Methodology

All resources in this repository follow the **Build → Test → Verify → Commit** cycle:

1. **BUILD**: Write or modify code incrementally
2. **TEST**: Run the code and check for errors
3. **VERIFY**: Confirm the feature works as expected
4. **COMMIT**: Save working code with descriptive message

**Never:**
- Write large amounts of code without testing
- Assume code works without verification
- Move to next task before current one is verified
- Commit broken or untested code

## 💡 Real-World Application

These resources have been used to develop **WP AI Workflow Automation Pro**, a production WordPress plugin with:

- WordPress's first ever visual workflow design plugin
- 22 custom AI workflow nodes
- ReactFlow-based visual editor
- Multi-AI provider integration (OpenAI, Anthropic, OpenRouter)
- Vector database operations
- Human-in-the-loop workflows
- Comprehensive security compliance

## 📝 Contributing

Have improvements or additional templates? Open an issue or pull request!

## 📜 License

MIT License - Feel free to use these templates and configurations in your own projects.

## 🎤 Presentation

These resources accompany the **WordCamp Netherlands 2025** presentation:
**"The Age of the Idea Guy: How AI is Democratizing WordPress Development"**

**Key Takeaways:**
1. AI democratizes development - you don't need to be a coder to build powerful WordPress plugins
2. Spec-driven development keeps AI aligned with your vision
3. Automated security scanning ensures professional-grade code quality
4. MCP servers extend AI capabilities to integrate with your entire toolchain
5. Custom AI agents enforce project-specific best practices automatically

## 🔗 Links

### Main Resources
- **WP AI Workflow Automation Pro**: [wpaiworkflowautomation.com](https://wpaiworkflowautomation.com/)
- **Claude Code**: [claude.com/code](https://claude.com/code)

### Development Tools
- **WordPress Coding Standards**: [developer.wordpress.org/coding-standards](https://developer.wordpress.org/coding-standards/)
- **PHPCS**: [github.com/squizlabs/PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)
- **PSALM**: [psalm.dev](https://psalm.dev)

### MCP Servers
- **Asana MCP**: [developers.asana.com/docs/using-asanas-mcp-server](https://developers.asana.com/docs/using-asanas-mcp-server)
- **Vibe Check MCP**: [github.com/PV-Bhat/vibe-check-mcp-server](https://github.com/PV-Bhat/vibe-check-mcp-server)
- **WordPress MCP**: [github.com/wordpress/mcp-adapter](https://github.com/wordpress/mcp-adapter)
- **Playwright MCP**: [github.com/microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp)
- **GitHub MCP**: [github.com/github/github-mcp-server](https://github.com/github/github-mcp-server)

## 📧 Contact

Questions about these resources or the presentation?

- **X (Twitter)**: [@Navidardakanian](https://x.com/Navidardakanian)

---

**Built with ❤️ for the WordPress community**

*Presented at WordCamp Netherlands 2025*
