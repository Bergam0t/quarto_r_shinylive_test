Playing around with publishing options from https://github.com/coatless-quarto/r-shinylive-demo

Notes:

- Does not work truly standalone (e.g. you couldn't email this out)
- Does work on Posit Cloud Connect when hosting through the 'quarto' route.


Issues encountered:

- Didn't work with Quarto 1.6.36. Needed to upgrade to 1.6.40. Seems to be related to deno imports. Seen in https://github.com/coatless-quarto/r-shinylive-demo/issues/14, https://github.com/quarto-dev/quarto-cli/issues/11219. Something that's appeared and disappeared a few times across quarto releases.

- Would not compile from within VSCode. Running render constantly telling me there were issues with shinylive not being installed. Running from within RStudio instead seemed to correctly trigger the downloads relating to deno.

```
Error running filter C:/Users/Bergam0t/AppData/Local/Programs/Quarto/share/filters/main.lua:
...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:40: Error running 'Rscript' command. Perhaps you need to install / update the 'shinylive' R package?

stack traceback:
        ...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:40: in global 'throw_quarto_error'
        ...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:86: in global 'callRShinylive'
        ...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:113: in global 'callShinylive'
        ...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:286: in global 'ensureBaseSetup'
        ...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:315: in global 'ensureLanguageSetup'
        ...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:424: in function <...live_test\_extensions\quarto-ext\shinylive\shinylive.lua:408>
        [C]: in ?
        [C]: in method 'walk'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:558: in local 'checked_walk'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:610: in function 'run_emulated_filter'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1297: in local 'callback'
        [string "..."]:1888: in field 'withScriptFile'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1313: in upvalue 'run_emulated_filter_chain'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1351: in function <...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1348>
stack traceback:
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:558: in local 'checked_walk'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:610: in function 'run_emulated_filter'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1297: in local 'callback'
        [string "..."]:1888: in field 'withScriptFile'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1313: in upvalue 'run_emulated_filter_chain'
        ...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1351: in function <...mmi/AppData/Local/Programs/Quarto/share/filters/main.lua:1348>
```
