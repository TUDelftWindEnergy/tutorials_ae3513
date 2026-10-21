# Python Setup

The tutorials can be run in two ways:

- **Online**, with no installation: click the ![](figures/on.png) icon at the top right of a tutorial page to launch it on Binder. Starting can take a few minutes, and your changes are lost when you close the page.
- **On your computer**, by following the instructions below. This is faster and lets you keep your changes.

You need two things: **pixi**, a small program that installs Python and all the required packages for you, and the **tutorial folder**, which tells pixi exactly what to install. If you already have another Python installation (for example Anaconda), it will not interfere. Use the terminal as described below rather than the Anaconda Prompt.

:::{tip} New to Python?
You do not need to be a Python expert to follow the tutorials, but you should know the basics (variables, lists, loops, functions). If you have never used Python, work through the free course [Programming with Python](https://swcarpentry.github.io/python-novice-gapminder/) first.
:::

## Part 1: Installation (once)

### Step 1: Install pixi

::::{tab-set}

:::{tab-item} Windows
:sync: windows

Open the Start menu, type `terminal` and open **Terminal**. This is a window into which you type commands.

Copy the line below, paste it into the terminal, and press Enter:

```
powershell -ExecutionPolicy ByPass -c "irm -useb https://pixi.sh/install.ps1 | iex"
```

Then **close the terminal and open a new one**. Check that pixi is installed and working by typing:

```
pixi --version
```
:::

:::{tab-item} macOS / Linux
:sync: unix

Press Cmd+Space, type `terminal` and press Enter. This is a window into which you type commands.

Copy the line below, paste it into the terminal, and press Enter:

```
curl -fsSL https://pixi.sh/install.sh | sh
```

Then **close the terminal and open a new one**. Check that pixi is installed and working by typing:

```
pixi --version
```
:::

::::

It should print a version number. See the [pixi documentation](https://pixi.sh) if you run into problems.

### Step 2: Download the notebooks folder

The notebooks are in the [notebooks](https://github.com/jennaiori/tutorials_ae3513/tree/main/notebooks) folder of the repository. GitHub cannot download a single folder as a ZIP file, so use the [download-directory](https://download-directory.github.io/?url=https%3A%2F%2Fgithub.com%2Fjennaiori%2Ftutorials_ae3513%2Ftree%2Fmain%2Fnotebooks) tool, which creates a ZIP file of the folder. Unzip it and move the resulting `notebooks` folder somewhere you will keep your work, for example `Documents`.

### Step 3: Install the packages

```
pixi install
```

The first time, pixi downloads Python and all the packages. This can take several minutes and may look like nothing is happening. Wait until the command finishes. Later, starting is instant.

## Part 2: Running the tutorials (every time)

1. Open a terminal in the `notebooks` folder (the folder that contains `pixi.toml`). On Windows, open the folder in File Explorer, type `cmd` in the address bar and press Enter; on macOS, right-click the folder and choose **New Terminal at Folder**. Alternatively, use `cd` to move to the folder in the terminal.
2. Start JupyterLab:

   ```
   pixi run editor
   ```

3. JupyterLab opens in your browser. Double-click a tutorial in the file browser on the left, for example `Tuto_floris.ipynb`.
4. When you are done, save your work, close the browser tab, and press **Ctrl+C** in the terminal.

## Working with a notebook

A notebook is made of **cells**, which contain either text or code.

- Click a code cell and press **Shift+Enter** to run it and move to the next one. Alternatively, click the ▶ button in the toolbar.
- Run the cells **in order from the top**. Later cells use variables defined in earlier ones.
- While a cell runs, `[*]` appears next to it. When it is finished, a number appears.
- Sliders and other widgets become active after the cell that creates them has been run.
- You can edit any code cell and run it again to see the effect of your change.
- If something goes wrong, use **Kernel → Restart Kernel and Run All Cells** to start again from a clean state.

## Troubleshooting

| Problem                                                   | Solution                                                                                                                                                                                                          |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `pixi` is not recognized / command not found              | You did not open a fresh terminal after Step 1. Close the terminal and open a new one.                                                                                                                            |
| `pixi` says it cannot find a `pixi.toml` or workspace     | You are in the wrong folder. Open the terminal in the folder that directly contains `pixi.toml` (see Step 2).                                                                                                     |
| A tutorial shows `ModuleNotFoundError`                    | You started JupyterLab in another way. Close it and start it with `pixi run editor` from the `notebooks` folder.                                                                                                  |

## Acknowledgements

This page is adapted from the [Installing Python](https://www.modelling-energy-systems.org/stable/appendix/installing-python.html) appendix of the TU Delft course *Modelling energy systems* by Stefan Pfenninger and contributors.
