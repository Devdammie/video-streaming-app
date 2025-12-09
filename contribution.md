# Contribution Guidelines

Thank you for contributing to the Video Streaming App! This guide will walk you through the entire contribution process, from forking the repository to creating your first pull request.

## 📖 Table of Contents

1. [Quick Start Guide](#quick-start-guide)
2. [Step-by-Step Contribution Process](#step-by-step-contribution-process)
3. [Code of Conduct](#code-of-conduct)
4. [Coding Standards](#coding-standards)
5. [Commit Guidelines](#commit-guidelines)
6. [Testing Requirements](#testing-requirements)
7. [Getting Help](#getting-help)

---

## 🚀 Quick Start Guide

**New to contributing?** Follow these steps:

1. Fork the repository
2. Clone your fork
3. Create a feature branch
4. Make your changes
5. Commit with a clear message
6. Push to your fork
7. Open a pull request

**Detailed instructions below!** ⬇️

---

## 📝 Step-by-Step Contribution Process

### Step 1: Fork the Repository

1. Navigate to the main repository: `https://github.com/Devdammie/video-streaming-app`
2. Click the **"Fork"** button in the top-right corner
3. This creates a copy of the repository in your GitHub account

### Step 2: Clone Your Fork

Open your terminal and clone your forked repository:

```bash
# Replace YOUR-USERNAME with your GitHub username
git clone https://github.com/YOUR-USERNAME/video-streaming-app.git

# Navigate into the project directory
cd video-streaming-app
```

### Step 3: Set Up the Upstream Remote

Connect your local repository to the original repository (upstream) to keep it in sync:

```bash
# Add the original repository as upstream
git remote add upstream https://github.com/Devdammie/video-streaming-app.git

# Verify the remotes
git remote -v
```

You should see:
```
origin    https://github.com/YOUR-USERNAME/video-streaming-app.git (fetch)
origin    https://github.com/YOUR-USERNAME/video-streaming-app.git (push)
upstream  https://github.com/Devdammie/video-streaming-app.git (fetch)
upstream  https://github.com/Devdammie/video-streaming-app.git (push)
```

### Step 4: Install Dependencies

```bash
# Install project dependencies
npm install

# Or if you're using yarn
yarn install
```

### Step 5: Set Up Environment Variables

```bash
# Copy the example environment file
cp .env.example .env

# Open .env and configure your local settings
# Add your API keys, database URLs, etc.
```

### Step 6: Create a Feature Branch

**Always create a new branch for your work!** Never commit directly to `main`.

```bash
# Make sure you're on the main branch first
git checkout main

# Pull the latest changes from upstream
git pull upstream main

# Create and switch to a new feature branch
git checkout -b feature/your-feature-name
```

**Branch Naming Conventions:**
- `feature/add-video-upload` - New features
- `bugfix/fix-login-error` - Bug fixes
- `docs/update-readme` - Documentation updates
- `refactor/optimize-player` - Code refactoring
- `test/add-auth-tests` - Test additions

### Step 7: Make Your Changes

Now you can start coding! Make your changes following these guidelines:

1. **Write clean, readable code** following the [Coding Standards](#coding-standards)
2. **Test your changes** locally to ensure everything works
3. **Add comments** for complex logic
4. **Update documentation** if needed

```bash
# Run the development server to test your changes
npm run dev
```

### Step 8: Check Your Code Quality

Before committing, ensure your code meets quality standards:

```bash
# Check for linting errors
npm run lint

# Fix auto-fixable linting issues
npm run lint:fix

# Format your code
npm run format

# Run tests
npm test
```

### Step 9: Stage Your Changes

```bash
# Check which files have changed
git status

# Add specific files
git add path/to/file1.js path/to/file2.js

# Or add all changed files
git add .
```

### Step 10: Commit Your Changes

Write a clear, descriptive commit message following the [Commit Guidelines](#commit-guidelines):

```bash
# Commit with a descriptive message
git commit -m "feat(video-player): add subtitle support"

# For multi-line commits
git commit -m "feat(video-player): add subtitle support

- Add subtitle upload functionality
- Implement subtitle parsing
- Add subtitle toggle in player controls

Closes #123"
```

### Step 11: Sync with Upstream (Important!)

Before pushing, make sure your branch is up to date with the main repository:

```bash
# Fetch the latest changes from upstream
git fetch upstream

# Rebase your branch on top of upstream/main
git rebase upstream/main

# If there are conflicts, resolve them, then:
git add .
git rebase --continue
```

### Step 12: Push to Your Fork

```bash
# Push your feature branch to your fork
git push origin feature/your-feature-name

# If you rebased and need to force push (be careful!)
git push origin feature/your-feature-name --force-with-lease
```

### Step 13: Create a Pull Request

1. Go to your fork on GitHub: `https://github.com/YOUR-USERNAME/video-streaming-app`
2. You'll see a banner saying **"Compare & pull request"** - click it
3. If you don't see the banner:
   - Click **"Contribute"** then **"Open pull request"**
   - Or go to the original repository and click **"New pull request"**

### Step 14: Fill Out the Pull Request Template

Provide the following information in your PR:

```markdown
## Description
Brief description of what this PR does

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## Related Issues
Closes #123
Relates to #456

## Changes Made
- Added subtitle upload endpoint
- Implemented subtitle parsing
- Added subtitle controls in video player UI
- Updated API documentation

## Testing Completed
- [ ] Tested on Chrome desktop
- [ ] Tested on Firefox desktop  
- [ ] Tested on mobile (iOS/Android)
- [ ] All existing tests passing
- [ ] New tests added and passing

## Screenshots/Videos
[Add screenshots or screen recordings if applicable]

## Checklist
- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have updated the documentation accordingly
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
```

### Step 15: Wait for Review

- Your PR will be reviewed by at least 2 team members
- **Be patient** - reviews may take 24-48 hours
- **Be responsive** - address feedback promptly
- **Be open** to suggestions and constructive criticism

### Step 16: Address Review Feedback

If reviewers request changes:

```bash
# Make the requested changes in your local branch
# Then stage and commit them
git add .
git commit -m "fix: address review feedback"

# Push the updates to your fork
git push origin feature/your-feature-name
```

The PR will automatically update with your new commits!

### Step 17: Merge and Celebrate! 🎉

Once your PR is approved:
- A maintainer will merge it into the main repository
- Your feature branch will be deleted (optional)
- Congratulations! You've successfully contributed!

### Step 18: Sync Your Fork (Post-Merge)

After your PR is merged, update your local repository:

```bash
# Switch to main branch
git checkout main

# Pull the latest changes from upstream
git pull upstream main

# Push to your fork to keep it in sync
git push origin main

# Delete your local feature branch (optional)
git branch -d feature/your-feature-name

# Delete the remote feature branch (optional)
git push origin --delete feature/your-feature-name
```

---

## 🤝 Code of Conduct

All contributors are expected to:

- **Be Respectful**: Treat everyone with respect and professionalism
- **Be Collaborative**: Work together to solve problems
- **Be Constructive**: Provide helpful feedback
- **Be Patient**: Remember everyone is learning
- **Be Inclusive**: Welcome contributors of all skill levels

### Unacceptable Behavior

- Harassment, discrimination, or offensive comments
- Trolling or insulting others
- Publishing others' private information
- Taking credit for others' work
- Any conduct that would be inappropriate in a professional setting

---

## 🔧 Troubleshooting Common Issues

### Issue: "Permission denied" when pushing

**Solution**: Make sure you're pushing to your fork, not the upstream repository:
```bash
git remote -v  # Check your remotes
git push origin feature/your-branch-name  # Push to YOUR fork
```

### Issue: Merge conflicts during rebase

**Solution**: Resolve conflicts manually:
```bash
# Open conflicted files and resolve conflicts
# Look for markers: <<<<<<< HEAD, =======, >>>>>>>

# After resolving, stage the files
git add .

# Continue the rebase
git rebase --continue

# If you want to abort the rebase
git rebase --abort
```

### Issue: Need to change commit message

**Solution**:
```bash
# For the most recent commit (not yet pushed)
git commit --amend -m "new commit message"

# For the most recent commit (already pushed)
git commit --amend -m "new commit message"
git push origin feature/your-branch-name --force-with-lease
```

### Issue: Accidentally committed to main branch

**Solution**:
```bash
# Create a new branch from current state
git checkout -b feature/your-feature-name

# Reset main to match upstream
git checkout main
git reset --hard upstream/main
```

### Issue: Need to update branch with latest changes

**Solution**:
```bash
git fetch upstream
git rebase upstream/main
```

---

## 📝 Coding Standards

### General Principles

- Write clean, readable, and maintainable code
- Follow the DRY principle (Don't Repeat Yourself)
- Keep functions small and focused (single responsibility)
- Use meaningful variable and function names
- Add comments for complex logic

### JavaScript/TypeScript Style Guide

```javascript
// ✅ Good: Use const by default
const config = { api: 'https://api.example.com' };

// ✅ Good: Use let only when reassignment is needed
let counter = 0;
counter++;

// ✅ Good: Use arrow functions
const sum = (a, b) => a + b;

// ✅ Good: Use template literals
const message = `Hello, ${userName}!`;

// ✅ Good: Use destructuring
const { user, data } = response;

// ✅ Good: Use async/await for promises
async function fetchVideos() {
  try {
    const videos = await api.get('/videos');
    return videos;
  } catch (error) {
    console.error('Failed to fetch videos:', error);
    throw error;
  }
}

// ❌ Bad: Unclear naming
const d = new Date();
const x = getStuff();

// ✅ Good: Clear, descriptive naming
const currentDate = new Date();
const userVideos = getUserVideos();
```

### File and Folder Structure

```
src/
├── components/        # Reusable UI components
│   ├── VideoPlayer/
│   ├── Navbar/
│   └── Footer/
├── pages/            # Page components
├── services/         # API calls and external services
├── hooks/            # Custom React hooks
├── utils/            # Helper/utility functions
├── styles/           # Global styles and themes
├── constants/        # Constants and configuration
├── types/            # TypeScript type definitions
└── tests/            # Test files
```

### Naming Conventions

| Type | Convention | Example |
|------|-----------|---------|
| **Components** | PascalCase | `VideoPlayer.jsx` |
| **Utility Files** | camelCase | `formatDate.js` |
| **Variables** | camelCase | `userName`, `videoList` |
| **Constants** | UPPER_SNAKE_CASE | `API_URL`, `MAX_UPLOAD_SIZE` |
| **Classes** | PascalCase | `UserManager` |
| **Functions** | camelCase (verb) | `getUserData()`, `formatTime()` |
| **Private Methods** | _camelCase | `_calculateTotal()` |

### Code Documentation

```javascript
/**
 * Converts seconds to a human-readable time format
 * @param {number} seconds - Total seconds to convert
 * @returns {string} Formatted time string (HH:MM:SS)
 * @example
 * formatTime(125) // Returns "00:02:05"
 * formatTime(3665) // Returns "01:01:05"
 */
function formatTime(seconds) {
  const hours = Math.floor(seconds / 3600);
  const minutes = Math.floor((seconds % 3600) / 60);
  const secs = seconds % 60;
  return `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
}
```

### Linting & Formatting

Before committing, always run:

```bash
# Check for linting errors
npm run lint

# Auto-fix linting issues
npm run lint:fix

# Format code with Prettier
npm run format

# Run all checks
npm run check
```

---

## ✍️ Commit Guidelines

Good commit messages help everyone understand the project history. Follow these guidelines:

### Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Commit Types

| Type | Description | Example |
|------|-------------|---------|
| **feat** | New feature | `feat(player): add playback speed control` |
| **fix** | Bug fix | `fix(auth): resolve login redirect issue` |
| **docs** | Documentation only | `docs(readme): update installation steps` |
| **style** | Code style/formatting | `style(css): fix indentation in navbar` |
| **refactor** | Code refactoring | `refactor(api): simplify video upload logic` |
| **perf** | Performance improvement | `perf(player): optimize video buffering` |
| **test** | Adding/updating tests | `test(auth): add login unit tests` |
| **chore** | Build/dependencies | `chore(deps): update react to v18` |

### Commit Message Examples

#### ✅ Good Commit Messages

```bash
# Feature with detailed description
git commit -m "feat(video-player): add subtitle support

- Add subtitle file upload endpoint
- Implement SRT/VTT subtitle parsing
- Add subtitle toggle in player controls
- Support multiple languages

Closes #45"

# Simple bug fix
git commit -m "fix(auth): resolve token expiration issue

The JWT token was expiring too early due to incorrect 
timezone calculation. Fixed by using UTC timestamps.

Fixes #123"

# Documentation update
git commit -m "docs(contributing): add pull request template"

# Quick fix
git commit -m "fix(ui): correct button alignment on mobile"
```

#### ❌ Bad Commit Messages

```bash
# Too vague
git commit -m "fixed stuff"
git commit -m "updates"
git commit -m "wip"

# No context
git commit -m "changed file"
git commit -m "bug fix"

# Multiple concerns
git commit -m "added feature, fixed bug, updated docs"
```

### Commit Best Practices

#### ✅ DO

- Commit frequently (small, logical changes)
- Write clear, descriptive messages
- Use present tense ("add feature" not "added feature")
- Reference issue numbers (`Closes #123`, `Fixes #456`)
- Keep commits focused on one concern
- Explain "why" in the body, not just "what"

#### ❌ DON'T

- Mix unrelated changes in one commit
- Commit commented-out code
- Commit console.log() debugging statements
- Commit sensitive information (API keys, passwords)
- Use vague messages like "fix" or "update"
- Commit large files unnecessarily

### How to Write a Good Commit Message

1. **First line (subject)**:
   - Maximum 50 characters
   - Start with type and scope
   - Use imperative mood: "add" not "added" or "adds"
   - No period at the end

2. **Body (optional)**:
   - Wrap at 72 characters
   - Explain what and why, not how
   - Use bullet points for multiple changes

3. **Footer (optional)**:
   - Reference issues: `Closes #123`
   - Note breaking changes: `BREAKING CHANGE: ...`

---

## 🧪 Testing Requirements

All contributions should include appropriate tests. This ensures code quality and prevents regressions.

### Test Coverage Goals

- Aim for **80%+ code coverage**
- **100% coverage** for critical features (authentication, payments, etc.)
- All new features **must include tests**

### Running Tests

```bash
# Run all tests
npm test

# Run tests in watch mode (for development)
npm run test:watch

# Run with coverage report
npm run test:coverage

# Run specific test file
npm test -- VideoPlayer.test.js

# Run unit tests only
npm run test:unit

# Run integration tests
npm run test:integration

# Run end-to-end tests
npm run test:e2e
```

### Writing Tests

Follow the **AAA pattern**: Arrange, Act, Assert

```javascript
// Example test structure
describe('VideoPlayer Component', () => {
  beforeEach(() => {
    // Setup: runs before each test
  });

  afterEach(() => {
    // Cleanup: runs after each test
  });

  it('should play video when play button is clicked', () => {
    // Arrange: Set up test conditions
    const mockVideo = { src: 'test.mp4', duration: 120 };
    const { getByTestId } = render(<VideoPlayer video={mockVideo} />);
    
    // Act: Perform the action
    fireEvent.click(getByTestId('play-button'));
    
    // Assert: Verify the outcome
    expect(getByTestId('video')).toHaveClass('playing');
    expect(getByTestId('play-button')).toHaveAttribute('aria-label', 'Pause');
  });

  it('should display video duration correctly', () => {
    const mockVideo = { src: 'test.mp4', duration: 125 };
    const { getByTestId } = render(<VideoPlayer video={mockVideo} />);
    
    expect(getByTestId('duration')).toHaveTextContent('00:02:05');
  });
});
```

### Test Checklist

Before submitting your PR, ensure:

- [ ] All existing tests pass
- [ ] New tests cover your changes
- [ ] Edge cases are tested
- [ ] Tests are readable and well-documented
- [ ] No tests are skipped (`.skip`)
- [ ] Coverage hasn't decreased

---

## ❓ Getting Help

### Where to Ask Questions

- **GitHub Discussions**: For general questions and discussions
- **GitHub Issues**: For bug reports and feature requests
- **Project Discord/Slack**: For quick questions and real-time help
- **Stack Overflow**: For technical questions (tag with project name)

### Before Asking for Help

1. Check the [README](./README.md)
2. Search existing [GitHub Issues](https://github.com/Devdammie/video-streaming-app/issues)
3. Review this contribution guide
4. Check the documentation in `/docs`

### How to Ask Good Questions

**❌ Bad Question:**
> "It doesn't work. Help!"

**✅ Good Question:**
> "When I try to upload a video larger than 50MB, I get a 413 error. I'm using the `/api/upload` endpoint. I've checked my .env file and `MAX_UPLOAD_SIZE=100MB`. Here's my code: [code snippet]. Any ideas?"

Include:
- What you're trying to do
- What you expected to happen
- What actually happened
- Error messages (full stack trace)
- Your environment (OS, Node version, etc.)
- What you've already tried

---

## 📚 Additional Resources

- **Git Help**:
  - [GitHub Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
  - [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
  - [Git Book](https://git-scm.com/book/en/v2)

- **Pull Request Best Practices**:
  - [How to Write a Perfect Pull Request](https://github.blog/2015-01-21-how-to-write-the-perfect-pull-request/)
  - [Code Review Guidelines](https://google.github.io/eng-practices/review/)

- **Testing**:
  - [Jest Documentation](https://jestjs.io/docs/getting-started)
  - [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)

---

## 🎉 Recognition

We value all contributions! Contributors will be:
- Added to our [Contributors List](https://github.com/Devdammie/video-streaming-app/graphs/contributors)
- Mentioned in release notes for significant contributions
- Eligible for team recognition and awards

## ❓ Questions?

- Check the FAQ in docs
- Ask in Slack/Discord
- Reach out to team leads
- Open a discussion issue

---

**Thank you for contributing! Let's build something amazing together! 🚀**