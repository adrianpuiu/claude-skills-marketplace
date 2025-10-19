# I built a Claude Code Skill that turns Claude into a professional project architect - Generate complete requirements, design docs, and implementation plans in minutes (Built with Claude)

**Productivity**

Ever start a project and realize 3 days in that you should have planned better? Or tried to get Claude to help build something complex only to watch it lose track halfway through? I just released the **project-planner** skill that solves this by turning Claude into your personal project architect.

## Why I built this

I was tired of:
- Starting projects with enthusiasm, then getting lost in complexity
- Claude forgetting context in large projects
- Rewriting the same code because requirements weren't clear
- "Just one more feature" turning into complete refactoring
- Having ideas but not knowing how to structure them properly

So I built a skill that makes Claude generate professional-grade planning documents BEFORE writing a single line of code. The kind of docs that $200/hour consultants charge thousands for.

**GitHub:** [https://github.com/adrianpuiu/claude-skills-marketplace]

## Installation (literally 30 seconds):

```bash
cd ~/.claude/skills/user
git clone [your-repo-url] project-planner
```

That's it. Open Claude Code and say "What are my skills?" - it's ready to architect.

## How it works - The Magic Triple:

Tell Claude: **"I want to build [your project idea]"**

Claude immediately generates THREE documents that become your project's DNA:

### 1. Requirements Document
Real user stories with testable acceptance criteria:
```
User Story: As a trader, I want real-time alerts, so that I never miss opportunities

Acceptance Criteria:
✓ WHEN price crosses threshold, THE system SHALL notify within 100ms
✓ THE system SHALL support 10,000 concurrent alerts
✓ IF connection fails, THEN THE system SHALL queue notifications
```

### 2. Technical Design Document
Complete architecture with components, interfaces, and data flow:
```
Claude → "Here's your 3-tier architecture with microservices..."
Claude → "Component responsibilities mapped..."
Claude → "API contracts defined..."
Claude → "Docker config ready..."
```

### 3. Implementation Plan
Hierarchical task breakdown with requirement tracing:
```
- [x] Phase 1: Infrastructure Setup
  - [x] 1.1 Database schema
    - Requirements: REQ-1.2, REQ-3.4
  - [ ] 1.2 Docker configuration
    - Dependencies: Task 1.1
```

## Real Example That Blew My Mind:

**Me:** "I need an order flow trading automation system"

**Claude** (with project-planner): 
1. Generated 15 requirements with 67 acceptance criteria
2. Designed a complete event-driven architecture
3. Created 9 implementation phases with 43 tasks
4. Each task traced back to specific requirements
5. Included WebSocket handlers, risk management, backtesting framework

**Result:** What would have taken me 2 weeks of planning was done in 3 minutes. Then when I said "implement task 1.1", Claude knew EXACTLY what to build because it had the blueprint.

## The Game Changer - Progressive Implementation:

Once you have these documents, watch what happens:

```
You: "Implement phase 1"
Claude: *checks requirements* *follows design* *builds exactly what was planned*

You: "Add feature X"  
Claude: "That impacts requirements 3 and 7. Here's the updated design..."

You: "What's next?"
Claude: *checks task list* "Task 2.3 is ready, it fulfills requirements..."
```

No more Claude forgetting what you're building. No more scope creep. No more "wait, why did we structure it this way?"

## Why This Changes Everything:

| Traditional Approach | With project-planner |
|---------------------|---------------------|
| Start coding immediately | Plan first, code once |
| Claude loses context | Documents maintain context |
| Constant refactoring | Architecture defined upfront |
| "What should I build next?" | Clear task progression |
| Requirements in your head | Requirements in writing |
| $2000 for consultant docs | Free, instant generation |

## It handles EVERYTHING:

- **Web Apps:** Full-stack with auth, CRUD, real-time updates
- **Microservices:** Service decomposition, API contracts, message queues  
- **Trading Systems:** Risk management, order execution, compliance
- **Data Pipelines:** ETL, transformations, quality checks
- **CLI Tools:** Command structure, plugins, configuration
- **ML Systems:** Training pipelines, feature stores, model serving

## The Secret Sauce:

The skill includes:
- 30+ requirement patterns (WHEN/WHERE/IF/THEN formats)
- Architecture templates for different project types
- Task decomposition strategies
- Requirement traceability matrices
- Performance target specifications
- Docker-ready deployment configs

## Try This Right Now (seriously, it's addictive):

1. Install the skill (30 seconds)
2. Tell Claude: "I want to build a [your dream project]"
3. Watch it generate enterprise-grade documentation
4. Pick any task and say "implement this"
5. Watch Claude build EXACTLY what was designed

## Community Challenge:

Post your craziest project idea in the comments. I'll run it through project-planner and share the generated architecture. Let's see how complex we can go!

**Bonus points:** If you've used it, share what kind of project you planned. I'm curious what everyone's building!

## Pro Tips I've Learned:

- Generate docs BEFORE writing any code (seriously, resist the urge)
- Use "expand requirement X" to add detail to specific features
- Say "make this enterprise-grade" for more robust architectures  
- Requirements become your project's source of truth
- The implementation plan literally becomes your project management tool

Built this for myself but realized it could save everyone hundreds of hours. No more abandoned projects. No more lost context. Just clean, planned, progressive implementation.

**Built with Claude** - because who better to help plan Claude projects than Claude itself?

Questions? Feature requests? Horror stories of unplanned projects? Drop them below!

---

*Edit: For those asking about complex projects - I've successfully used this for a 15-microservice financial platform, a real-time multiplayer game, and a complete SaaS with multi-tenancy. The skill scales beautifully.*

*Edit 2: Yes, it works with ANY project type - not just software. People have used it for business plans, course curricula, even wedding planning (that was creative!).*
