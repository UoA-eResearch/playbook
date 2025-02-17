# Special Projects Playbook

This playbook outlines the best practices for managing special projects at the Centre for eResearch, University of Auckland. These practices ensure consistency, maintainability, and accessibility across all projects.

---

## **Project Management**
- **Tracking**: All projects are tracked in [JIRA](https://jira.auckland.ac.nz). Use it to monitor progress, and track tasks. Log issues related to the code in the GitHub Issues in the repo, anything else (meta) in JIRA.
- **Repository Hosting**:
  - Repositories are hosted on GitHub.
  - By default, repositories are open-source and use the MIT license. Exceptions should be justified and documented.

---

## **Repository Guidelines**

### **README File**
Every repository must include a `README.md` file that provides:
1. **Project Overview**: A concise description of the project.
2. **Installation Instructions**: Step-by-step guide to install required dependencies.
3. **Running the Code**: Clear instructions for running the code.
4. **Example Usage**: Include a runnable example, along with any necessary data files (use Git LFS for large files).

### **Dependency Management**
- Use a `requirements.txt` file to list all Python dependencies. Use `uv` to install them.
- For JavaScript projects, use `package.json`.

---

## **Coding and Development Practices**

### **Version Control**
- As a default, follow **Semantic Versioning (semver)** (e.g., `v1.2.3`). If this is not appropriate, such as for a dataset representing a collection at a given time, use an ISO8601 timestamp (e.g., `2025-02-07` or `2025-01-31T11-18-28Z`).
- Use **GitHub releases** to tag and document major updates.
- Consider using ```git fetch``` in place of ```git pull``` to minimise merge difficulties

### **Commits**
- Commit often, ensuring each commit represents a meaningful change (e.g., new feature, bug fix).
- Write succinct commit messages that clearly describe the change. See https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/ for some examples of good commit messages.

### **Coding Standards**
- Use [VS Code](https://code.visualstudio.com/) as the recommended editor.
  - Leverage the **GitHub Copilot** extension for AI-assisted coding.
  - Use the **Remote-SSH** extension for working on remote VMs, such as NeCTAR VMs.
- Use [Black](https://black.readthedocs.io/) for Python code formatting.
- JavaScript code should follow modern ES6+ standards.
- Don't Repeat Yourself (DRY) - don't copy paste code, use functions instead.
- Keep It Simple - your code should be as simple as possible, but no simpler.
- Don't do things manually that can be automated.
- Follow Separation of Concerns (SoC) - separate code into logical modules.
- Don't reinvent the wheel - if there's a good package to do what you want to do, use it. If it's missing a feature, consider contributing to it.

---

## **Hosting and Deployment**

### **Websites**
- Host project websites using **GitHub Pages**.
- Load libraries via **CDN** for efficient performance.
- Setup Google Analytics using the shared UoA-eResearch account for tracking website usage. It's best to set this up *before* you need it.

### **Jupyter Notebooks**
- Render large Jupyter notebooks to HTML and serve them with GitHub Pages.

### **Raster tile/vector services**
Use ArcGIS Online in preference to a NeCTAR VM

---

## **Automation and CI/CD**
- Use **GitHub Actions** for CI/CD workflows where possible.
- Prefer GitHub Actions over NeCTAR VMs for routine automation tasks.

---

## **Example Project Structure**
```bash
project/
├── README.md          # Project description and usage instructions
├── requirements.txt   # Python dependencies
├── data/              # Example data (use Git LFS for large files)
├── src/               # Source code
│   ├── main.py        # Main script
│   └── utils.py       # Helper functions
├── notebooks/         # Jupyter notebooks (if any)
├── .github/           # GitHub workflows and configurations
│   └── workflows/
└── LICENSE            # MIT License file
```

By following these guidelines, we ensure our projects are FAIR (Findable, Acessible, Interoperable, and Reproducible), maintainable, and useful to the wider research community.