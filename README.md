# GITHUB-WORKFLOW

GitHub Actions workflow to scan all repositories for a user/organization and produce a JSON report.

## Usage

1. **Add a repository secret named `GH_PAT`** containing a Personal Access Token with 'repo' scope
   (or appropriate org/repo scopes for private repos):
   - Go to your repository settings
   - Navigate to Secrets and variables > Actions
   - Click "New repository secret"
   - Name: `GH_PAT`
   - Value: Your GitHub Personal Access Token

2. **Put this file in a repo you control** (this repo is ready to use)

3. **Run the workflow**:
   - Go to Actions > Workflows
   - Select "Scan Repos"
   - Click "Run workflow"
   - Enter the GitHub username or organization name to scan
   - Click "Run workflow"

4. **Download the artifact**:
   - Once the workflow completes, click on the workflow run
   - Scroll to the "Artifacts" section
   - Download the `repos` artifact
   - Extract the ZIP file to access `repos-report.json`

## Report Format

The generated `repos-report.json` contains an array of repositories with the following information for each:
- `name`: Repository name
- `full_name`: Full repository name (owner/repo)
- `description`: Repository description
- `private`: Whether the repository is private
- `html_url`: Repository URL
- `created_at`: Creation timestamp
- `updated_at`: Last update timestamp
- `pushed_at`: Last push timestamp
- `size`: Repository size
- `stargazers_count`: Number of stars
- `watchers_count`: Number of watchers
- `language`: Primary programming language
- `forks_count`: Number of forks
- `open_issues_count`: Number of open issues
- `default_branch`: Default branch name
- `topics`: Repository topics/tags