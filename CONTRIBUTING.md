# Contributing to NeoGen

Thanks for helping out! NeoGen is a community project and all kinds of contributions are welcome: bug reports, testing, documentation, and code.

By taking part you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md). Contributions are released under the project's [MIT License](LICENSE).

## Reporting bugs

1. Check the [existing issues](https://github.com/VansOnV/NeoGen/issues) first.
2. [Open a new issue](https://github.com/VansOnV/NeoGen/issues/new/choose) and fill in the bug report form.
3. Include the job log. Every job in the GUI writes `neogen_gui.log` next to `NeoGen.exe` (it is overwritten by each job, so copy it right after the problem). The **About & Maintenance** card in Settings shows your version and build.

Please don't attach copyrighted game files. Describe the file type and, if you can, share a minimal sample you made yourself.

## Suggesting features

Open an issue with the feature request form. Explain the problem you're trying to solve before the solution you have in mind.

## Development setup

You need Windows 10/11 (64-bit) and Python 3.12 from [python.org](https://www.python.org/downloads/).

```
git clone https://github.com/VansOnV/NeoGen.git
cd NeoGen
pip install -r requirements.txt
python main.py
```

The external tools (`neogen_misc\`, `vcwxml_winx64\`) are not stored in the repository. Point to them in **Settings** (they are saved in `settings.ini`) or place them next to the app.

### Project layout

| Path | What it is |
| :--- | :--- |
| `main.py` | Entry point (GUI, plus the `--run-job` and `--remove-menu` modes) |
| `app/pages/` | One file per GUI page |
| `app/core/` | The engine (`NeoGen.py`) and the thin `*_ops.py` modules the GUI calls |
| `app/job_runner.py`, `app/job_launcher.py` | Jobs run in a separate process and report progress through files |
| `assets/` | Icon |
| `build_pyinstaller.bat`, `build.bat` | Build the exe (PyInstaller, or Nuitka) |
| `installer.iss`, `build_installer.bat` | Inno Setup installer |

## Making a change

1. Fork the repo and create a branch from `main` (`fix/short-description` or `feature/short-description`).
2. Keep each pull request focused on one change.
3. Test it by running the app and exercising the page you changed. If you fix a bug, say how you reproduced it.
4. Follow the existing code style: type hints, short docstrings that explain *why*, and no behaviour change to the engine unless that is the point of the PR.
5. Update the README feature tables and `CHANGELOG.md` if users will notice the change.
6. Open the pull request and fill in the template.

The CI workflow compiles the code and starts the main window headlessly. It must pass before a PR is merged.

## Building a release (maintainers)

Releases are built by the **Release** workflow (`.github/workflows/release.yml`) when a tag like `v2.0` is pushed:

```
git tag v2.0
git push origin v2.0
```

It builds the portable folder with PyInstaller and, if the `REDIST_URL` secret is set, also bundles the external tools and builds the installer. `REDIST_URL` should point to a zip containing the `redist\` folder described in the README. The workflow creates a **draft** release so you can review and add notes before publishing.

Bump the version in `app/version.py` and add a section to `CHANGELOG.md` before tagging.

## Questions

Ask on [Discord](https://discord.gg/buC9W643tQ).
