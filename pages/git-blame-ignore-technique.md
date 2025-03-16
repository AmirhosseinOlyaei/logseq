# Preserving Git Commit History with git-blame-ignore

## The Problem: Formatting Commits Obscure Code History

When working on a team project, code formatting changes (indentation, line breaks, etc.) can create a major issue with `git blame` and similar history tools. When someone runs a formatter on the codebase:

- The formatter modifies many lines across many files
- `git blame` then shows the formatting commit as the "author" of those lines
- The actual author who wrote the original code is obscured
- This makes code archaeology and understanding when/why code was written much harder

For example, if Alice wrote a function in 2022, and Bob reformatted the entire codebase in 2023, `git blame` will show Bob as the author of that function, not Alice.

## The Solution: .git-blame-ignore-revs

Git provides a solution with the `.git-blame-ignore-revs` file. This file lists commit hashes that should be **ignored** when determining the author of each line of code.

## Setting Up git-blame-ignore in Your Project

### 1. Create Essential Files

Add these files to your project:

#### .git-blame-ignore-revs

```
# Formatting changes to ignore in git blame
# Add commit hashes below when you make pure formatting changes
```

#### setup-git-blame.sh

```bash
#!/usr/bin/env bash

# Script to configure Git to properly ignore formatting commits in git blame

echo "Configuring Git to use .git-blame-ignore-revs file..."
git config --local blame.ignoreRevsFile .git-blame-ignore-revs

echo "Configuration complete."
echo ""
echo "To see blame without formatting commits, use: git blame <file>"
echo ""
echo "VS Code with GitLens extension will now respect the ignored formatting commits."
echo ""
echo "=============================================================================="
echo "INSTRUCTIONS FOR THE TEAM:"
echo ""
echo "When making PURE FORMATTING commits (no functional changes):"
echo ""
echo "1. Make your formatting changes"
echo "2. Create a commit with a message that starts with 'style:' or 'format:'"
echo "3. Get the full commit hash using: git rev-parse HEAD"
echo "4. Add the commit hash to .git-blame-ignore-revs file"
echo "5. Push both the formatting commit and the updated .git-blame-ignore-revs file"
echo ""
echo "This will ensure git blame shows the original author of the code,"
echo "not the person who reformatted it."
echo "=============================================================================="
```

#### .vscode/settings.json (add this configuration)

```json
{
  "git.ignoreRevsFile": ".git-blame-ignore-revs"
}
```

#### CONTRIBUTING.md (add a section on formatting)

````markdown
## Git Workflow for Formatting Changes

When making pure formatting changes (with no functional changes), follow these steps to preserve the commit history in git blame:

1. Make your formatting changes
2. Commit them with a message that starts with `style:` or `format:`
   ```bash
   git commit -m "style: format code with prettier"
   ```
````

3. Get the full commit hash
   ```bash
   git rev-parse HEAD
   ```
4. Add the commit hash to `.git-blame-ignore-revs` file
   ```
   # Formatting changes to ignore in git blame
   abcd1234abcd1234abcd1234abcd1234abcd1234  # Format code with prettier
   ```
5. Commit the updated `.git-blame-ignore-revs` file
   ```bash
   git commit -m "chore: update git-blame-ignore-revs with formatting commit"
   ```
6. Push both commits to the repository

````

### 2. Run the Setup Script

Make sure the script is executable and run it:

```bash
chmod +x setup-git-blame.sh
./setup-git-blame.sh
````

## Practical Example: Preserving History When Formatting Code

Here's the step-by-step workflow when applying formatting:

1. **Apply formatting changes**

   ```bash
   # Using Prettier (or your preferred formatter)
   pnpm format
   ```

2. **Commit formatting changes with a special prefix**

   ```bash
   # Stage the changes
   git add .

   # Commit with a style: prefix
   git commit -m "style: format all code with Prettier"
   ```

3. **Get the commit hash**

   ```bash
   git rev-parse HEAD
   # Output: 466a7e14d6d4e2cef48a1a87af748a7a558ed975
   ```

4. **Add the hash to `.git-blame-ignore-revs`**
   Edit `.git-blame-ignore-revs` to add the commit hash:

   ```
   # Formatting changes to ignore in git blame
   # Add commit hashes below when you make pure formatting changes
   466a7e14d6d4e2cef48a1a87af748a7a558ed975 # Initial code formatting with Prettier
   ```

5. **Commit the updated ignore list**

   ```bash
   git add .git-blame-ignore-revs
   git commit -m "chore: update git-blame-ignore-revs with formatting commit hash"
   ```

6. **Push both commits to the repository**
   ```bash
   git push
   ```

## Benefits for Teams

This approach provides several key benefits:

- **Preserved authorship**: Original authors remain credited for their code
- **Better code archaeology**: Easier to determine when and why code was written
- **Cleaner blame view**: Tools like GitLens in VS Code will skip formatting commits
- **Documentation**: Formats changes are still recorded but don't obscure history
- **Team awareness**: Clear process for making formatting changes

## IDE Integration

### VS Code

The `.vscode/settings.json` file with `"git.ignoreRevsFile": ".git-blame-ignore-revs"` ensures VS Code's GitLens respects your ignored commits.

### JetBrains IDEs (IntelliJ, WebStorm, etc.)

JetBrains IDEs respect the `.git-blame-ignore-revs` file when configured. Add this to your project settings or users can add it to their global git config.

## Conclusion

The git-blame-ignore technique is a simple but powerful way to maintain code history clarity while still allowing for consistent formatting. By following this process, teams can keep their codebase clean and well-formatted without sacrificing the ability to understand code provenance.
