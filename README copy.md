
# Setup

## Mac

0. install homebrew?
1. Installing MacTex
2. Installing an IDE (VSCode)
3. Installing LaTeX Workshop Extension
<!-- finish LaTeX setup -->
4. Press `cmd + shift + p` and look for `Snippets: Configure Snippets`, press enter and then look for `latex.json`, press enter again and then copy the content from `vscode_settings_template > latex.json` file into the newly opened file.
5. Press `cmd + shift + p` and look for `Preferences: Open User Settings (JSON)`, press enter and then look for `settings.json`, press enter and then append the content from `vscode_settings_template > settings.json` file into the newly opened file with the correct json syntax.
6. Press `cmd + shift + p` and look for `Preferences: Open Keyboard Shortcuts (JSON)`, press enterSnippets, press enter and then look for `keybindings.json`, press enter and then copy the content from `vscode_settings_template > keybindings.json` file into the newly opened file.
7. RESTART the IDE completely
<!-- finish setup of vscode LaTeX configuration -->


## Windows

LaTeX setup -->


## Overleaf


## Start Working with the template

1. now just work with the folder `latex_summary_template` - feel free to rename it. Whenever you have a new subject you want to write a summary for, just copy the renamed version of `latex_summary_template` into the corresponding course parent-folder.
2. Dont forget to rename `latex_general_summary_template.tex` respectively `latex_HSG_summary_template.tex` as well, the compiled PDF will have the same title as this file.
3. the general style, imports and extra stuff such as a custom fourth heading are defined in `styles/mystyle.sty`. You do not have to look at that or change anything inside that.
4. Inside of `latex_general_summary_template.tex` respectively `latex_HSG_summary_template.tex` you can change more general stuff such as the geometry of the page, the author, title, some pdf-date in hypersetup. you can deactivate and activate the table of contents, list of figures, list of tables, ...
5. all of your content goes inside of `content/main-content.tex` - you dont even have to rename it.
6. TODO: explain what bibliography.tex is for
7. TODO: explain what figures_list.tex is for
8. TODO: explain what the directory "bib" is for
9. TODO: explain that all of the screenshots, images, pdfs go inside of the folder `fig` and will later be added by e.g. the snippet "image"
10. explain that the extra folder `latex_HSG_summary_template` just exists for HSG which will have the HSG logo already filled in. all other students should feel free to delete this folder and vice versa.
11. drag the output pdf to the right side of the screen to work in splitmode beween `main-content.tex` and the output pdf.
12. the user can find a place in the .tex file by clicking "command + mouseclick" on the required text-element inside of the pdf, while being in split mode.
13. explain that by installing latex utilities they can see the word count in the current document.
14. explain what the .chktexrc file does and why the user should not delete it
15. explain that the yellow markings are not dangerous and can be ignored
16. explain that the .gz is just an output file and can be ignored.

# LaTeX Tutorials
- https://www.youtube.com/watch?v=lgiCpA4zzGU
- https://www.youtube.com/playlist?list=PLHXZ9OQGMqxcWWkx2DMnQmj5os2X5ZR73
- https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes

# TODO

[] explain the general functionality of `latex.json`, details about snippets come later
[] explain the general functionality of `keybindings.json`, details about keybindings
[] explain the specific functionality of `settings.json`
[] explain the exact snippets I implemented, what they do and what they are useful for
[] explain the exact shortcuts I implemented, what they do and what they are useful for