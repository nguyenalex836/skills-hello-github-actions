<header>

<!--
  <<< Author notes: Course header >>>
  Include a 1280x640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280x640 social image, auto delete head branches.
  Add your open source license, GitHub uses MIT license.
-->

# Hello GitHub Actions

_Create a GitHub Action and use it in a workflow._

</header>

<!--
  <<< Author notes: Step 3 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 3: Add actions to your workflow file

_Nice work adding a job to your workflow! :dancer:_

Workflows have jobs, and jobs have steps. So now we'll add steps to your workflow.

**What are _steps_?**: Actions steps will run during our job in order. Each step is either a shell script that will be executed, or an action that will be run. Each step must pass for the next step to run. Actions steps can be used from within the same repository, from any other public repository, or from a published Docker container image.

In our action, we post a comment on the pull request using a [bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) script and [GitHub CLI](https://cli.github.com/).

### :keyboard: Activity: Add Actions steps to your workflow file

1. Open your `welcome.yml` file.
2. Update the contents of the file to:
   ```yaml
   name: Post welcome comment
   on:
     pull_request:
       types: [opened]
   permissions:
     pull-requests: write
   jobs:
     build:
       name: Post welcome comment
       runs-on: ubuntu-latest
       steps:
         - run: gh pr comment $PR_URL --body "Welcome to the repository!"
           env:
             GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
             PR_URL: ${{ github.event.pull_request.html_url }}
   ```
3. Click **Start commit** in the top right of the workflow editor.
4. Type your commit message and commit your changes directly to your branch.
5. Wait about 20 seconds for actions to run, then refresh this page (the one you're following instructions from) and an action will automatically close this step and open the next one.

<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions/categories/hello-github-actions) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
