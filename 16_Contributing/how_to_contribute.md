# How to Contribute

## Before You Start

Read content_guidelines.md before writing anything. It explains the writing standards, tone, and formatting rules this guide uses. A contribution that does not follow these standards will need revision before it can be merged, which slows things down for everyone.

---

## The Two Ways to Contribute

### Option 1 — Open a GitHub Issue (for corrections and suggestions)

If you have found an error, have a suggestion, or want to flag something that is missing but do not want to write the fix yourself, open an Issue on the repository.

Go to: https://github.com/Zeyad-Mustafa/photonics-gt2-guide/issues
Click: New Issue
Choose the appropriate template (see issue_templates/ folder)
Fill in the template and submit

Issues are reviewed by the maintainer and either resolved directly or converted into tasks for a future pull request.

### Option 2 — Submit a Pull Request (for actual content changes)

If you want to add or edit content directly, use a pull request.

Step 1 — Fork the repository
Go to https://github.com/Zeyad-Mustafa/photonics-gt2-guide and click Fork. This creates your own copy of the repository under your GitHub account.

Step 2 — Clone your fork to your computer
Open a terminal and run:

    git clone https://github.com/YOUR_USERNAME/photonics-gt2-guide.git
    cd photonics-gt2-guide

Step 3 — Create a new branch for your change
Do not make changes directly on the main branch. Create a descriptive branch name:

    git checkout -b fix-ip-s-development-time

or for new content:

    git checkout -b add-electrospinning-application

Step 4 — Make your changes
Edit or create the relevant Markdown files. Follow the content guidelines.

Step 5 — Commit your changes with a clear message

    git add .
    git commit -m "Fix IP-S development time for large structures (was 20 min, corrected to 30 min)"

Step 6 — Push your branch to your fork

    git push origin fix-ip-s-development-time

Step 7 — Open a Pull Request
Go to your fork on GitHub. You will see a prompt to open a pull request for your recently pushed branch. Click it, fill in the PR description (what you changed and why), and submit.

---

## What Happens After You Submit

The maintainer will review the pull request. Feedback may be left as comments on specific lines. You can respond to comments and push additional commits to your branch — the pull request updates automatically.

If the contribution is accepted, it will be merged into the main branch. Your GitHub username will appear in the repository's commit history as a contributor.

If a pull request sits without response for more than two weeks, follow up via LinkedIn or leave a comment on the PR.

---

## Submitting Images and SEM Results

If you want to contribute a photograph of a printed structure, an SEM image, or a diagram, include the image file in your pull request in the relevant section folder.

Required with every image submission:
- The image file (PNG or JPG, maximum 5 MB per file)
- A brief caption (one or two sentences describing what is shown)
- A statement that the image is your own work or is licensed for reuse (specify the license)
- The objective, resin, and approximate structure dimensions if it is a print result

Images will be linked from the relevant Markdown file with a caption. They will not be embedded inline if they make the Markdown file too heavy to load quickly on a mobile connection.

Do not submit images that are:
- Taken from a paper without explicit permission from the publisher
- From a Nanoscribe marketing brochure or website (copyright applies)
- Unlabeled or without a scale bar (for microscopy images)

---

## A Note on Parameters

If you are submitting a correction or addition that involves specific printing parameters (laser power, scan speed, development times), you do not need to cite your institution or machine serial number. Just provide the corrected value and a brief explanation of why the current value is wrong or incomplete.

If your parameters only apply to a specific resin lot or a specific machine configuration that differs from a standard GT2, note that context briefly so readers understand the scope of the information.

---

Proceed to: content_guidelines.md
