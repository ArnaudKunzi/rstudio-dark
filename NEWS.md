## RStudio 2024.11.0 "Kousa Dogwood" Release Notes

### New
#### RStudio
- RStudio now supports the inclusion of environment variables when publishing applications to Posit Connect (#13032)
- RStudio now supports new features from the R graphics engine (groups, glyphs) when supported by the underlying device (#14613)
- The .Rproj.user folder location can now be customized globally both by users and administrators (#15098)
- RStudio now supports code formatting using the 'styler' R package, as well via other external applications (#2563)
- Added www-socket option to rserver.conf to enable server to listen on a Unix domain socket (#14938; Open-Source Server)
- RStudio now supports syntax highlighting for Fortran source files (#10403)
- Display label "Publish" next to the publish icon on editor toolbar (#13604)
- RStudio supports `usethis.description` option values when creating projects via the RStudio New Project wizard (#15070)
- The font size used for the document outline can now be customized [Accessibility] (#6887)
- The RStudio diagnostics system now supports destructuring assignments as implemented and provided in the `dotty` package
- The "Insert Chunk" button now acts as a menu in Quarto documents as well as R Markdown documents (#14785)
- Improved support for highlighting of nested chunks in R Markdown and Quarto documents (#10079)
- Improved support for variable-width chunk headers and footers in R Markdown / Quarto documents (#15191)
- The "Include all function arguments in completion list" user preference can be used to control whether RStudio includes function arguments which appear to have already been used in the current context (#13065)
- Available environment variables are now provided as completion suggestions within `Sys.unsetenv()` (#15215)
- RStudio IDE User Guide and RStudio & Posit Workbench Release Notes now includes release version in navigation bar reference URLs (#15223)
- Rename in Scope now operates across chunks within R Markdown and Quarto documents (#4961)
- RStudio now respects the chunk 'dpi' option when generating plots in R Markdown / Quarto documents (#11649)
- RStudio now supports the display of an HTML table of contents for R help files when `options(help.htmltoc = TRUE)` is set (#14523)
- RStudio now includes `.env` files in the fuzzy finder, and also displays these files in the Files pane
- Quarto documents now have a gear icon for editing cell (chunk) options (#11745)
- Added "Copy RStudio Version" command to command palette for copying RStudio version, commit, and build date to the clipboard
- RStudio User Guide and RStudio & Posit Workbench Release Notes now include versioned URLs in the Guides drop-down menu in the navigation bar(rstudio-pro#6151)
- RStudio now provides executed chunk code as a single multi-line entry in the Console history (#3520)
- RStudio now provides snippet completions within function calls and subset calls (#13441)
- RStudio now supports zooming the IDE via Meta + NumpadAdd and Meta + NumpadSubtract (#12242)

#### Posit Workbench

- Posit Workbench Administration Guide, Posit Workbench User Guide, and Posit Workbench Licenses guide now include versioned URLs in the Guides drop-down menu in the navigation bar (rstudio-pro#6151)
- Posit Workbench User Guide underwent a reorganization of how the individual IDE guides are presented. Each guide was migrated from the left-hand navigation to the upper (main) navigation bar. Now, when a guide is selected from the navigation bar, only that guide's contents display in the left-hand navigation. Additionally, the Posit Workbench guide was renamed to "Workbench Setup" in the navigation bar to prevent confusion between the title of the guide and to create more distinction between the home page of the guide and the Posit Workbench Overview. Lastly, the links for the four IDEs were updated to navigate to the corresponding guide within the Posit Workbench User Guide (instead of the IDE's external site) and are displayed as buttons (rstudio-pro#6069)
- Restrict Positron and VS Code sessions for insecure (non-SSL) contexts. These editors do not work properly otherwise. (rstudio-pro#3741)
- Added support for HTTP Proxy variables in rserver and rsession to enable managed credentials features in Workbench environments behind a proxy server. (rstudio-pro#5893)

### Fixed
#### RStudio
- "Run All" now only executes R chunks when "Chunk Output in Console" is set (#11995)
- Fixed an issue where the R session could crash on connect while generating console output (#15330)
- Fixed an issue where the Rename File command did not write unsaved changes before performing the rename (#15242)
- Fixed an issue where the chunk options popup didn't recognize chunk labels preceded by a comma (#15156)
- Fixed an issue where the chunk options popup was confused by quoted strings containing spaces (#6829)
- Fixed an issue where the chunk options popup was confused by spaces around equals signs (#2673)
- Fixed an issue where an R Markdown chunk label containing dashes was truncated in Visual Editor (#15162)
- Fixed an issue in the data viewer where list-column cell navigation worked incorrectly when a search filter was active (#9960)
- Fixed an issue where debugger breakpoints did not function correctly in some cases with R 4.4 (#15072)
- Fixed an issue where autocompletion results within piped expressions were incorrect in some cases (#13611)
- Fixed being unable to save file after cancelling the "Choose Encoding" window (#14896)
- Fixed problems creating new files and projects on a UNC path (#14963, #14964; Windows Desktop)
- Prevent attempting to start Copilot on a non-main thread (#14952)
- Reformat Code no longer inserts whitespace around '^' operator (#14973)
- Prompt for personal access token instead of password when using github via https (#14103)
- RStudio now forward the current 'repos' option for actions taken in the Build pane (#5793)
- Executing `options(warn = ...)` in an R code chunk now persists beyond chunk execution (#15030)
- Remove focus-visible polyfill and instead use native browser :focus-visible pseudoclass [Accessibility] (#14352)
- Fixed an issue where completion types for objects with a `.DollarNames` method were not properly displayed (#15115)
- Fixed an issue where the Console header label was not properly layed out when other tabs (e.g. Terminal) were closed (#15106)
- Auto-saves will no longer trim trailing whitespace on the line containing the cursor (#14829)
- Fixed an issue where pressing Tab would insert a literal tab instead of indenting a multi-line selection (#15046)
- Fixed scroller behavior in Data Viewer when viewing very large datasets (#12834)
- Fixed an issue where quoted variable names were not completed properly in dplyr pipes (#15161)
- Fixed issue with highlight of `tikz` code chunks in R Markdown documents (#15019)
- RStudio now uses current session repositories when installing package dependencies via background jobs (#10016)
- Fixed issue where collapsed raw chunks were displayed with an incorrect label in the Visual Editor (#14594)
- Fixed issue where test errors were duplicated when presented in Issues tab of Build pane (#14564)
- Fixed issue where certain Python variable names were incorrectly quoted when inserted via autocompletion (#14560)
- Fixed an issue where RStudio over-aggressively required packages to be rebuilt when setting breakpoints (#15201)
- RStudio now includes Markdown headers without any label in the document outline (#14552)
- Clicking in the editor gutter to toggle a breakpoint no longer also selects the associated line (#15226)
- RStudio no longer logs warning / error messages related to disabled R actions (e.g. ReadConsole) in forked sessions (#15221)
- RStudio Desktop now forwards `LD_LIBRARY_PATH` when detecting available R installations (#15044)
- Fixed an issue with incorrect completions provided in `readline()` context (#15238)
- Fixed an issue where ghost text could not be inserted in non-chunk parts of an R Markdown / Quarto document (#14507)
- Fixed Mac Desktop Pro so it starts on an ARM (Mx) Mac that doesn't have Rosetta2 installed (rstudio-pro#3558)
- Fixed Windows Desktop Pro so it starts up after using the Choose R dialog (rstudio-pro#6062)
- Fixed an issue where updating the Copilot agent on Windows could fail if Copilot was already in use (#14850)
- Fixed an issue where RStudio could autosave files on blur even while a Save As... modal was active (#15303)
- Fixed an issue where some output from `uv` could be rendered blurry in the RStudio Console (#15282)
- Fixed an issue where the IDE could hang when changing the file type of an R Markdown document (#15313)
- Fixed the chunk options popup to work in Visual Mode for non-R chunks (#15312)
- Fixed an issue with the splash screen appearing on top of the Desktop Pro Manage License dialog (rstudio-pro#6962)
- Fixed an issue where column names starting with numbers were not properly quoted when inserted as a completion (#13290)
- Fixed an issue where right-clicking on the console history did not present Paste as an option (#14538)

#### Posit Workbench

- Fixed an issue with Workbench login not respecting "Stay signed in when browser closes" when using Single Sign-On (rstudio-pro#5392)
- Fixed several cross-reference links in the Posit Workbench Administration Guide and Posit Workbench User Guide - VS Code sections (#rstudio-pro#6678)
- Fixed heading anchor ID issue in Posit Administration Guide - VS Code PWB Code Server section (#rstudio-pro#6961)

### Upgrade Instructions

#### Posit Workbench

If running Workbench behind a proxy server, you may need to update your `NO_PROXY` configuration. HTTP Proxy variables are now supported in rserver and rsession, so it is important to include local addresses to Job Launcher sessions and other internal services in your `NO_PROXY` list. See the [Outgoing Proxies](https://docs.posit.co/ide/server-pro/access_and_security/outgoing_proxies.html) section of the Workbench Admin Guide for more information. (rstudio-pro#5893)

### Dependencies
- Updated GWT to version 2.10.1 (#15011)
- Updated Electron to version 31.7.2 (#14982; Desktop)

### Deprecated / Removed
- Removed user preference for turning off focus indicator rectangles (#14352)
- Removed support for `rsconnect-jupyter`; publish Jupyter Notebooks to Connect using `rsconnect-python`. See the [Publishing Jupyter Notebooks to Connect](https://docs.posit.co/ide/server-pro/integration/jupyter-multiple-python-versions.html#publishing-jupyter-notebooks-to-connect) section of the Posit Workbench Administration Guide for more information(rstudio-pro#6989)
