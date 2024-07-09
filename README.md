## Auto Archiving Website to Wayback Machine

### Overview

This feature automatically archives your website on the Wayback Machine using GitHub Actions, ensuring that your content is preserved for future reference. The Wayback Machine, provided by the Internet Archive, is a digital archive of the World Wide Web, allowing users to see archived versions of web pages across time.

### Features

- **Automatic Archiving:** Periodically saves snapshots of your website to the Wayback Machine.
- **Scheduled Backups:** Configured to archive your website daily at midnight.
- **Version History:** Easily view and access historical versions of your website.
- **Reliability:** Ensure your website's content is preserved even if the site undergoes changes or goes offline.
- **Ease of Use:** Simple setup with GitHub Actions.

### How It Works

1. **Setup**: Use the provided GitHub Action to automate the archiving process.
2. **Configuration**: The action is scheduled to run daily at midnight by default.
3. **Execution**: The action automatically sends a request to the Wayback Machine to archive your website.
4. **Access Archives**: Visit the Wayback Machine to view and access your archived content.

### GitHub Action Configuration

Here's the GitHub Action code for auto archiving your website:

```yaml
name: Archive Website

on:
  workflow_dispatch:
  schedule:
    - cron: '0 0 * * *' # Runs every day at midnight

jobs:
  archive:
    runs-on: ubuntu-latest
    steps:
    - name: Archive Website with Wayback Machine
      run: |
        curl -s http://web.archive.org/save/https://example.com
```

### Setting Up the GitHub Action

1. **Create or Edit GitHub Workflow File**:
   - Navigate to your repository on GitHub.
   - Go to `Actions` > `New workflow` > `Set up a workflow yourself` or edit an existing workflow.
   - Copy and paste the above GitHub Action code into your workflow file (e.g., `.github/workflows/archive-website.yml`).

2. **Customize the URL**:
   - Replace `https://example.com` with your actual website URL.

3. **Commit and Push**:
   - Commit the changes to your repository and push them to GitHub.

### Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.
