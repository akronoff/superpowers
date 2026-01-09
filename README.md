# Superpowers (Customized)

A streamlined software development workflow for Claude Code, built on composable "skills". This is a customized fork optimized for single-agent usage (Pro plan friendly).

## How it works

It starts from the moment you fire up your coding agent. As soon as it sees that you're building something, it *doesn't* just jump into trying to write code. Instead, it steps back and asks you what you're really trying to do.

Once it's teased a spec out of the conversation, it shows it to you in chunks short enough to actually read and digest.

After you've signed off on the design, your agent puts together an implementation plan that's clear enough for an enthusiastic junior engineer with poor taste, no judgement, no project context, and an aversion to testing to follow. It emphasizes true red/green TDD, YAGNI (You Aren't Gonna Need It), and DRY.

Skills are advisory - use them when they add value, skip them for simple tasks.

## Differences from upstream

This fork removes multi-agent skills to reduce token usage:
- Removed: `subagent-driven-development`
- Removed: `dispatching-parallel-agents`
- Modified: `using-superpowers` - now advisory instead of mandatory

## Credits

Based on [Superpowers](https://github.com/obra/superpowers) by Jesse Vincent. If this helps you, consider [sponsoring Jesse's opensource work](https://github.com/sponsors/obra).

## Installation

### As a local plugin

```bash
# Clone this repo
git clone https://github.com/akronoff/superpowers.git ~/.claude/plugins/local/superpowers

# Enable in Claude Code
/plugin enable superpowers@local
```

### From your fork

```bash
/plugin marketplace add akronoff/superpowers
/plugin install superpowers@akronoff-superpowers
```

## The Basic Workflow

1. **brainstorming** - Activates before writing code. Refines rough ideas through questions, explores alternatives, presents design in sections for validation.

2. **using-git-worktrees** - Creates isolated workspace on new branch, runs project setup, verifies clean test baseline.

3. **writing-plans** - Breaks work into bite-sized tasks (2-5 minutes each). Every task has exact file paths, complete code, verification steps.

4. **executing-plans** - Works through the plan with checkpoints for review.

5. **test-driven-development** - Enforces RED-GREEN-REFACTOR: write failing test, watch it fail, write minimal code, watch it pass, commit.

6. **requesting-code-review** - Reviews against plan, reports issues by severity.

7. **finishing-a-development-branch** - Verifies tests, presents options (merge/PR/keep/discard), cleans up worktree.

## What's Inside

### Skills Library

**Testing**
- **test-driven-development** - RED-GREEN-REFACTOR cycle

**Debugging**
- **systematic-debugging** - 4-phase root cause process
- **verification-before-completion** - Ensure it's actually fixed

**Collaboration**
- **brainstorming** - Socratic design refinement
- **writing-plans** - Detailed implementation plans
- **executing-plans** - Batch execution with checkpoints
- **requesting-code-review** - Pre-review checklist
- **receiving-code-review** - Responding to feedback
- **using-git-worktrees** - Parallel development branches
- **finishing-a-development-branch** - Merge/PR decision workflow

**Meta**
- **writing-skills** - Create new skills following best practices
- **using-superpowers** - Introduction to the skills system

## Philosophy

- **Test-Driven Development** - Write tests first, always
- **Systematic over ad-hoc** - Process over guessing
- **Complexity reduction** - Simplicity as primary goal
- **Evidence over claims** - Verify before declaring success
- **Right-sized process** - Use skills when they help, skip when they don't

## Syncing with upstream

```bash
git fetch upstream
git cherry-pick <commit>  # grab specific improvements
# or
git merge upstream/main   # then remove what you don't want
```

## License

MIT License - see LICENSE file for details

## Support

- **Upstream issues**: https://github.com/obra/superpowers/issues
- **This fork**: https://github.com/akronoff/superpowers/issues
