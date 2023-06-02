# My Overleaf CV for multiple languages

## MY CV
Russian: https://drive.google.com/file/d/179wzwh2AWMVSTo6pG8054Sy-GXuuOaie/view?usp=sharing <br>
English: https://drive.google.com/file/d/1o57UFoVIgtvRPAa014atTuv550rcGLJO/view?usp=sharing

## Project Link in Overleaf
https://www.overleaf.com/read/qmmwmmhxkmyw

## Adding more languages
1. Add your language from `babel` package.
2. Add `if` statements for your language like in code provided:
https://github.com/LicBoy/overleaf-multilang-CV/blob/b7daf87b2600402d667162d69bdb62912152e41e/cv.tex?#L18-L27

### Example
For example, to add **French**: <br>
In `cv.tex` file:
1. Add french language from `babel` package.
2. Add `\newif\iffr` statement.
3. Add `\frtrue` trigger, and comment all others language triggers.
4. Add command for language:<br>
  `\newcommand{\langfr}[1]{\iffr\selectlanguage{french}#1\fi}`
5. Make sure that commands from dictionary.tex are imported: `\input{dictionary.tex}`
  
In `dictionary.tex` file:
- You actually create dictionary with your texts in different languages, e. g. `name` command for showing your name in different languages:<br>
https://github.com/LicBoy/overleaf-multilang-CV/blob/b7daf87b2600402d667162d69bdb62912152e41e/dictionary.tex#L1-L2 <br>
So, to add french writing in the `name` command, you can do: 
  ```
  \newcommand{\name}
  {
    \langen{Ruslan Akhmetvaleev}
    \langru{Руслан Ахметвалеев}
    \langfr{Sauvignon Blanc}
  }
  ```
Note, that `\langfr` command should be the same as command you added in `cv.tex`, step 4.

Finally, in your main tex file (`cv.tex` in my case) you can use your created commands to display and compile overleaf document in different languages.
