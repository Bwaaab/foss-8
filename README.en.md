# Introduction

A CLI tool that supports team project work in the Open Source Software course at Pukyong National University.

It aims to provide easy access from the terminal to the templates, evaluation criteria, and weekly schedules scattered throughout the project guide.

## Team

| Name | Role | GitHub | Responsibilities |
|---|---|---|---|
| 박상재 | Team lead | @sangjaepark0000 | Template retrieval |
| 양하윤 | Development lead | @sheep-ship-it | Current week and task lookup |
| 백지훈 | Documentation | @jihun31 | Evaluation criteria and completion checks |


## Team Project Guide

See the [full table of contents](docs/guide/README.md) for schedules, deliverables, evaluation criteria, collaboration rules, templates, and FAQs. The full guide and [team-Specific decisions](docs/guide/team-context.md) are both available.


## Usage

Requires Python 3.12 or later. Once installed, the tool can also run from other teams' project directories.
The weekly schedule and evaluation criteria follow this course's project guide.

### Installation

Follow the [pipx installation instructions](https://pipx.pypa.io/stable/how-to/install-pipx.html) to install pipx, then run `pipx ensurepath`.
Restart your terminal if needed, then install the tool with the following command. Git is also required.

```bash
pipx install git+https://github.com/sangjaepark0000/foss-8.git
```

After installation, navigate to your team's project directory and run:

```bash
cd 팀-프로젝트
oss --help
oss week --list
oss check                 # Check the basic files in the current directory
oss format minutes        # Display the meeting minutes template
```

With `oss` installed, replace `python main.py` with `oss` in the examples below.
Run `pipx upgrade foss8` to update the tool, or `pipx uninstall foss8` to uninstall it.

### Development Setup

Clone the repository to run the tool directly, or install it in editable mode in a virtual environment.

```bash
git clone https://github.com/sangjaepark0000/foss-8.git
cd foss-8
python3 -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
python -m pip install -e .
oss --help
```

The `oss` command is available while the virtual environment is active. You can also run `python main.py` without installing the tool.

### Displaying Templates

Requires Python 3.12 or later. Displaying templates requires no third-party libraries.

```bash
python main.py format             # List available templates
python main.py format minutes     # a blank meeting minutes template
python main.py format proposal    # the project proposal template
python main.py format midterm     # the interim report template
python main.py format final       # the final report template
python main.py format --help
```

The meeting minutes template preserves the headings and table columns from Appendix B of the guide, with example names, dates, progress entries, and completion marks left blank.
The report templates use the guide's seven proposal sections, six interim report sections, eight final report sections, and appendices
to provide cover pages, tables of contents, fields to fill in, required content, length requirements, submission criteria, and links to the source material.

Fill in the generated Markdown, then convert it to PDF for submission.
Blank templates remain available. You can also use the commands below to save meeting minutes with basic information filled in.
