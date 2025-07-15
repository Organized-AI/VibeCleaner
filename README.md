# VibeCleaner: MCP-Powered Developer Cleanup Tool

*A specialized cleanup tool for vibe coders learning MCP tools and modern development workflows*

## 🎯 Vision

VibeCleaner is designed specifically for developers who are experimenting with MCP (Model Context Protocol) tools, AI-assisted development, and modern coding workflows. Unlike generic cleaners like CleanMyMac, VibeCleaner understands developer workflows, Git repositories, and the unique challenges of learning new tools.

## 🚀 Core Features

### 1. **Intelligent Project Detection**
- **Git Repository Scanning**: Automatically detects all Git repos across the system
- **MCP Server Discovery**: Finds MCP-related projects, configs, and unused servers
- **Framework Recognition**: Identifies React, Node.js, Python, Docker projects
- **Dependency Analysis**: Scans `node_modules`, `venv`, `.next`, build artifacts

### 2. **Smart Cleanup Recommendations**

#### **Git Repository Cleanup**
- Detect repositories with uncommitted changes
- Find duplicate clones of the same repository
- Identify stale branches and suggest cleanup
- Locate large files that should be in Git LFS
- Find repositories that can be safely archived

#### **Development Environment Cleanup**
```
🔍 Scanning Development Projects...

📁 /Users/vibe-coder/Projects/
├── ✅ active-mcp-server/ (Git: clean, Last commit: 2 days ago)
├── ⚠️  old-react-app/ (Git: 15 uncommitted files, Last commit: 3 months ago)
├── 🔄 duplicate-project/ (Duplicate of: ~/Downloads/project/)
├── 📦 node_modules-heavy/ (node_modules: 847MB - can be regenerated)
└── 🗄️  archived-experiment/ (No commits in 6 months - archive candidate)

Recommendations:
• Archive old-react-app after reviewing uncommitted changes
• Remove duplicate-project (keeping the newer version)
• Clean node_modules in 3 unused projects (saves 2.1GB)
• Move archived-experiment to cold storage
```

### 3. **MCP-Specific Intelligence**

#### **MCP Server Management**
- Detect unused MCP servers and configurations
- Find outdated MCP server installations
- Identify conflicting Claude Desktop configurations
- Clean up failed MCP deployment artifacts

#### **Development Artifact Cleanup**
- Remove build directories (`.next`, `dist`, `build`)
- Clean temporary files from development tools
- Identify duplicate environment configurations
- Remove unused Docker images and containers

### 4. **Cloud Storage Integration**

#### **Smart Migration Suggestions**
- Recommend moving inactive projects to cloud storage
- Integrate with GitHub for repository archiving
- Suggest Google Drive backup for important non-code files
- Automatic zip and upload of completed projects

#### **Version Control Optimization**
```javascript
// Example: Smart Git cleanup suggestions
{
  "repository": "/Users/coder/my-app",
  "issues": [
    {
      "type": "large_files",
      "files": ["video-demo.mp4", "dataset.csv"],
      "suggestion": "Move to Git LFS or cloud storage",
      "impact": "Reduces repo size by 85MB"
    },
    {
      "type": "stale_branches",
      "branches": ["feature/old-idea", "experiment/failed-approach"],
      "suggestion": "Archive or delete branches",
      "impact": "Cleanup git history"
    }
  ]
}
```

## 🛠 Technical Architecture

### **Filesystem MCP Integration**
```typescript
// Core MCP integration for filesystem operations
interface VibeCleanerMCP {
  scanProjects(): Promise<ProjectScanResult[]>
  analyzeGitRepos(): Promise<GitAnalysis[]>
  detectDuplicates(): Promise<DuplicateGroup[]>
  recommendCleanup(): Promise<CleanupRecommendation[]>
  executeCleanup(recommendations: CleanupRecommendation[]): Promise<CleanupResult>
}

// Filesystem MCP Server Integration
class FilesystemAnalyzer {
  async scanForProjects(rootPath: string): Promise<CodeProject[]> {
    // Use Filesystem MCP to safely traverse directories
    // Detect Git repos, package.json files, requirements.txt, etc.
  }
  
  async analyzeDiskUsage(projects: CodeProject[]): Promise<UsageAnalysis> {
    // Calculate actual impact of cleanup recommendations
  }
  
  async safeDelete(paths: string[]): Promise<DeletionResult> {
    // Execute deletions with proper backup and rollback
  }
}
```

### **Safety-First Architecture**
- **Dry Run Mode**: Show exactly what will be cleaned before execution
- **Backup Creation**: Automatic backups before any destructive operations
- **Rollback System**: Ability to undo cleanup operations
- **Git Integration**: Never delete uncommitted work without explicit user consent

## 💻 User Interface Design

### **Dashboard Overview**
```
┌─────────────────────────────────────────────────────────────┐
│ VibeCleaner Dashboard                            💾 2.3GB free │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│ 🎯 Quick Wins (Safe to clean now)                          │
│ ├── Remove node_modules from 5 unused projects    [1.2GB]  │
│ ├── Clean build artifacts from 8 projects         [445MB]  │
│ └── Remove duplicate downloads                     [234MB]  │
│                                                             │
│ ⚠️  Needs Review (Check before cleaning)                    │
│ ├── old-mcp-experiments/ (uncommitted changes)    [89MB]   │
│ ├── Important-project/ (no recent commits)        [156MB]  │
│ └── learning-playground/ (mixed files)            [67MB]   │
│                                                             │
│ 📊 Project Health Overview                                 │
│ ├── Active Projects: 12 ✅                                 │
│ ├── Stale Projects: 8 ⚠️                                   │
│ └── Archived Candidates: 4 📦                              │
│                                                             │
│ [🧹 Start Quick Cleanup]  [🔍 Deep Analysis]  [⚙️ Settings] │
└─────────────────────────────────────────────────────────────┘
```

### **Project Detail View**
```
┌─────────────────────────────────────────────────────────────┐
│ Project: awesome-mcp-server                                 │
├─────────────────────────────────────────────────────────────┤
│ 📍 Location: ~/Projects/awesome-mcp-server/                │
│ 🌳 Git Status: Clean (last commit: 2 days ago)             │
│ 📦 Size: 45MB (node_modules: 32MB, src: 13MB)              │
│ 🔧 Type: MCP Server (TypeScript/Node.js)                   │
│                                                             │
│ 🧹 Cleanup Opportunities:                                  │
│ ├── ✅ node_modules can be regenerated           [32MB]    │
│ ├── ✅ .next build directory                     [8MB]     │
│ ├── ⚠️  Old log files in /logs                  [2MB]     │
│ └── ℹ️  No issues found with Git history                   │
│                                                             │
│ 🔄 Recommended Actions:                                    │
│ • Keep active (recently modified)                          │
│ • Clean build artifacts to save 40MB                       │
│ • Add .gitignore rules for log files                       │
│                                                             │
│ [🧹 Clean Build Files]  [📦 Archive Project]  [❌ Skip]    │
└─────────────────────────────────────────────────────────────┘
```

## 🎓 Learning-Focused Features

### **Educational Insights**
- **Best Practices Tips**: Teach proper `.gitignore` usage
- **Workflow Optimization**: Suggest better development setups
- **Tool Recommendations**: Introduce relevant MCP servers and tools
- **Progress Tracking**: Show improvement in workspace organization over time

### **Interactive Cleanup Guidance**
```
💡 Learning Moment: Git Best Practices

We found large files in your Git history. Here's what we recommend:

❌ Don't do this:
git add video-demo.mp4  # Large binary files slow down clones

✅ Do this instead:
1. Move large files to /assets folder
2. Use Git LFS for version-controlled binaries
3. Or upload to cloud storage and link in README

[📚 Learn More] [🔧 Auto-Fix] [⏭️ Skip This Time]
```

## 🔧 Implementation Roadmap

### **Phase 1: Core Functionality**
- [ ] Filesystem MCP integration
- [ ] Basic project detection
- [ ] Git repository analysis
- [ ] Safe cleanup operations
- [ ] Simple CLI interface

### **Phase 2: Intelligence Layer**
- [ ] Duplicate detection algorithms
- [ ] MCP-specific cleanup rules
- [ ] Cloud storage integration
- [ ] Advanced Git analysis

### **Phase 3: User Experience**
- [ ] Desktop GUI application
- [ ] Interactive cleanup wizard
- [ ] Learning-focused tutorials
- [ ] Progress tracking and analytics

### **Phase 4: Advanced Features**
- [ ] CI/CD integration
- [ ] Team workspace management
- [ ] Custom cleanup rules
- [ ] Integration with popular IDEs

## 🎯 Target Use Cases

### **The Learning Vibe Coder**
- Just discovered MCP tools and Claude coding
- Downloads lots of example projects and tutorials
- Experiments with different frameworks
- Needs help organizing growing project collection

### **The MCP Experimenter**
- Building custom MCP servers
- Testing different deployment strategies
- Accumulates lots of configuration files
- Wants to keep only working solutions

### **The AI-Assisted Developer**
- Uses Claude, Cursor, and other AI tools
- Generates lots of prototype projects
- Needs help distinguishing keepers from experiments
- Values automated workflow optimization

## 📦 Technical Stack

```typescript
// Core Dependencies
{
  "dependencies": {
    "@modelcontextprotocol/filesystem": "^1.0.0",
    "simple-git": "^3.20.0",
    "glob": "^10.3.0",
    "chalk": "^5.3.0",
    "inquirer": "^9.2.0"
  },
  "devDependencies": {
    "@types/node": "^20.0.0",
    "typescript": "^5.3.0",
    "electron": "^28.0.0" // For desktop app
  }
}
```

## 🚀 Getting Started (Proposed)

```bash
# Install VibeCleaner
npm install -g vibe-cleaner

# Quick scan
vibe-cleaner scan

# Interactive cleanup
vibe-cleaner clean --interactive

# Dry run (safe preview)
vibe-cleaner clean --dry-run

# Focus on specific directory
vibe-cleaner scan ~/Projects --mcp-only
```

## 🎉 Value Proposition

VibeCleaner bridges the gap between generic system cleaners and developer-specific needs. It understands:

- **Git workflows** and won't delete uncommitted work
- **MCP ecosystem** and helps optimize tool configurations  
- **Learning patterns** of developers exploring new technologies
- **Modern development** with build tools, package managers, and AI assistance

By combining Filesystem MCP integration with intelligent analysis, VibeCleaner becomes an essential tool for developers who want to stay organized while exploring the cutting edge of AI-assisted development.

## 📚 Documentation

- [StartStacks Workshop Tutorial](./docs/StartStacks-Workshop.md) - Live coding tutorial for building VibeCleaner
- [Contributing Guide](./CONTRIBUTING.md) - How to contribute to the project
- [API Documentation](./docs/API.md) - Technical API reference

## 🤝 Contributing

We welcome contributions! Whether you're:
- A vibe coder learning MCP tools
- An experienced developer optimizing workflows
- A UI/UX designer improving user experience
- A technical writer enhancing documentation

Check out our [Contributing Guide](./CONTRIBUTING.md) to get started.

## 📄 License

MIT License - see [LICENSE](./LICENSE) for details.

---

*Ready to help vibe coders keep their digital workspace as clean as their code!* 🎯✨