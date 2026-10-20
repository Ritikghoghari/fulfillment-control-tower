# Learning Log : Fulfillment Control Tower

## Day 1: Project setup (20 Oct 2026)

### What I did
- First of all i have created the GitHub repository `fulfillment-control-tower` and cloned it locally.
- Set up a Python virtual environment (`.venv`) and installed pandas, DuckDB,
  Jupyter, matplotlib and pyarrow. Saved the versions in `requirements.txt`.
- Built the project structure: `data/raw`, `data/processed`, `notebooks`, `src`,
  `sql`, `reports`, `notes`, `tests`.
- Downloaded the Olist Brazilian e-commerce dataset (9 CSV files) into `data/raw`.
- Wrote a first notebook that loads every file and prints its size, to confirm
  the data and the environment work.

## What broke and how I fixed it
- **mkdir failed in PowerShell.** PowerShell needs commas between folder names
  (`mkdir a, b, c`), unlike Command Prompt or Linux.
- **Nested project folder.** I ended up with a folder inside a folder. Fixed by
  opening the inner folder (the one containing `.git`) in VS Code.
- **Notebook kernel did not show `.venv`.** Caused by the wrong folder being open.
  After opening the correct folder, I selected the `.venv` kernel.
- **Packages installed globally.** I ran `pip install` before activating the venv.
  Reinstalled inside `.venv` and regenerated `requirements.txt`.
- **pandas blocked by Windows ("Application Control policy").** Windows Smart App
  Control blocks unsigned compiled files, which pandas uses. I turned it off;
  Defender antivirus and the firewall remain active.

### What I learned
- A virtual environment isolates each project's packages, so updating one project
  cannot break another. `requirements.txt` lets anyone rebuild the same setup.
- Terminal commands depend on the shell. Always check if a command is written for
  PowerShell, Command Prompt or Linux.
- Most setup errors come from being in the wrong folder or the wrong environment.
  Checking `pip -V` and the terminal path first saves time.

### Decisions and why
- **`data/` is excluded from Git (`.gitignore`).** The files are large and belong
  to Olist; the README will link to the original source instead.
- **Folder structure decided on day one.** Separating raw data, processed data,
  notebooks, scripts and SQL keeps the project readable for reviewers and makes
  it possible to rebuild everything step by step.

### Next
Day 2: define the business problem and the warehouse KPIs before writing any analysis code.