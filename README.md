# Husky Pre-Commit Setup

This project demonstrates how to set up Husky with lint-staged, ESLint, and Prettier for automated code quality checks on pre-commit.

## Overview

Husky manages Git hooks, lint-staged runs linters on staged files, ESLint checks JavaScript code, and Prettier formats code automatically.

## Setup Phases

### Phase 1: Initialize the Project
- Initialize Git: `git init`
- Initialize Node.js: `npm init -y`
- Setup Husky: `npx husky-init && npm install`

### Phase 2: Install Tools
- Install dependencies: `npm install --save-dev lint-staged eslint prettier globals @eslint/js`

### Phase 3: Configuration Files
- `eslint.config.mjs`: ESLint configuration for JavaScript files.
- `.prettierrc`: Prettier formatting rules.
- `.gitignore`: Ignore unnecessary files.

### Phase 4: Update package.json
Add `lint-staged` configuration to run ESLint and Prettier on staged files.

### Phase 5: Configure Husky
Update `.husky/pre-commit` to run `npx lint-staged`.

### Phase 6: Test and Push
- Create `index.js` with sample code.
- Add Git remote, stage, commit (triggers hooks), and push.

## Usage
- Stage your changes: `git add .`
- Commit: `git commit -m "message"`
- Husky will run lint-staged, fixing issues automatically if possible.

## Expected Behavior
On commit, Husky runs lint-staged, which lints and formats staged files. Commits are blocked on major errors; minor issues are fixed.
