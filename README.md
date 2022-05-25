# Graphlet Structure Analysis of the Real Networks

###### Master's thesis

> Bc. Michal Puškel  
> supervisor: doc. RNDr. Mária Markošová, PhD.

> 2022  
> FMFI UK

## Task description

Student will create new software
or will improve already existing software
for graphlet structure analysis of the complex networks.
By the use of this software,
student will analyse graphlet structure of real data networks
and will enumerate all measures related to this structure.
Student will analyse graphlet structure of artificialy generated networks, as well,
and will compare measured data.

## Task goal

Analyse graphlet structure of real networks by the use of improved or own created software.

#### Description

This Master's thesis is a direct sequel to our former Bachelor's thesis _Probability Comparison of Functional Brain Networks_:

- https://github.com/michalpuskel/diplomka/blob/master/michal_puskel_bak_praca.pdf
- https://github.com/michalpuskel/diplomka/blob/master/poster_algoritmy.pdf
- https://github.com/michalpuskel/diplomka/blob/master/poster_algoritmy_2.pdf

#### Goals

- Implement combinatorial approach to graphlet counting (ORCA) algorithms to create software for counting GDD.
- Create software for counting and comparing GDD agreement of networks.
- Compare some trivially distinguishable artificialy generated networks to validate GDD agreement.
- Find out if an attribute of a functional brain network
  „to suffer from the Alzheimer disease”
  shows off in the structure of its graph.

#### Results

- GDD agreement measure can not distinguish graph structure of graphs with different node or edge count.
- We assumne Alzheimer’s disease is not projected to functional brain networks graph structure.

#### PDF

https://github.com/michalpuskel/diplomka/blob/master/michal_puskel_dip_praca.pdf

#### Presentation

https://github.com/michalpuskel/diplomka/blob/master/prezentacia.zip

#### Source code

https://gitlab.com/michal.puskel/gdd

#### Video presentation

- https://youtu.be/VezPTKmdfNE
- https://github.com/michalpuskel/diplomka/blob/master/Graphlet_Structure_Analysis_of_the_Real_Networks.mp4.zip

#### Quick start guide

- Install `GO` on your computer.
- https://go.dev/doc/install

&nbsp;

- (There are many images in this quide, open them in new tab with `middle mouse button` to view them in full resolution.)
- (Read all guide regardless of your OS. Some steps are explained in more detail for Windows guide.)

##### [Windows]

- Download (and unzip) repository.

<img src="/readme/win/1_download.png" alt="download" />

- Open Windows PowerShell in `app/src` folder of repository.
- To invoke context menu with Windows PowerShell option, hold `Shift` on keyboard + click with `right mouse button`.

<img src="/readme/win/2_powershell_invoke.png" alt="powershell" />

- You can check your `GO` enviroment variables (settings) with `go env` command.

<img src="/readme/win/3_go_env.png" alt="go_env" />

- Set `GO111MODULE` to `off`.
- `$env:GO111MODULE="off"`
- This is very important setting for `GO` to recognize `PATH` in packages in the correct (old) way.

<img src="/readme/win/4_go111module_off.png" alt="111module" />

- Now we need to setup `GOPATH` for our repository correctly.
- Navigate in `app` folder with Windows explorer (window browsing and clicking manager).
- Click with `left mouse button` in upper address bar of Windows explorer to reveal full path of `app` directory.
- Copy it to clipboard (into memory) with `Ctrl + C` keys of keyboard.

<img src="/readme/win/5_left_mouse_click.png" alt="path_left_click" />
<img src="/readme/win/6_copy_path.png" alt="copy_path" />

- Now set `GOPATH` correctly.
- `$env:GOPATH="[Ctrl + V]"`

<img src="/readme/win/7_set_gopath.png" alt="set_GOPATH" />

- Check settings were done correctly with `go env`.
- `GOROOT` is path where `GO` is installed, it will be set correctly automatically after fresh installation of `GO`.

<img src="/readme/win/8_check_gopath.png" alt="check_GOPATH" />

- Build your executable binary files with `go build` command.

<img src="/readme/win/9_go_build_windows.png" alt="go_build" />

- Use `orca.exe` to count GDD of input graph.
- Input for ORCA is text file (representing simple undirected connected graph) with first row containing 2 numbers `n e`:
  - number of nodes `n`
  - number of edges `e`
- Next follows `e` lines with definiton of edges.
- Nodes are labelled from `0` to `n-1`.
- Output from ORCA is text file with `n` lines.
- Each line is representing the number of occurence of particular node in all 73 automorphism orbits.
- It means each line contains 73 space-separated numbers, first corresponding to orbit 0, second to orbit 1,... last to orbit 72.
- Input and output from our ORCA is the same as the one from original ORCA implemenation by Tomaž Hočevar.
- https://file.biolab.si/biolab/supp/orca/

<img src="/readme/win/10_orca_exe_windows.png" alt="orca_exe" />
<img src="/readme/win/11_explain_orca_input.png" alt="orca_in" />
<img src="/readme/win/12_explain_orca_output.png" alt="orca_out" />

- Use `gdd_agreement.exe` to generate comparison JSON of compared graphs.
- Enter list of compared file names in text file, each line containing name of one compared graph.
- All these graphs will be compared via GDD agreement one with each other.
- It is optional to label groups of graphs, to be later displayed by custom color in visualized comparison table head column / row.

<img src="/readme/win/13_gdd_agreement_count.png" alt="gdd_agreement_count" />
<img src="/readme/win/14_gdd_agreement_progress.png" alt="gdd_agreement_progress" />
<img src="/readme/win/15_gdd_agreement_finish.png" alt="gdd_agreement_finish" />

##### [Mac]

- Clone repository.

<img src="/readme/mac/1_git_clone.png" alt="download" />
<img src="/readme/mac/2_git_clone.png" alt="git_clone" />

- Set `GO111MODULE` to `off`.
- `$ go env -w GO111MODULE=off`

<img src="/readme/mac/3_GO111MODULE.png" alt="111module" />

- Set `GOPATH` and `GOROOT`, add them to your `PATH` and export all enviroment variables.
- Restart your terminal after editing `.bash_profile` to take effect.

<img src="/readme/mac/4_open_bash_profile.png" alt="open_bashrc" />
<img src="/readme/mac/5_edit_gopath.png" alt="edit_GOPATH" />

- Check settings were done correctly with `go env`.

<img src="/readme/mac/6_check_go_env.png" alt="check_go_env" />

- Build your executable binary files with `go build` command.

<img src="/readme/mac/7_build_binaries.png" alt="build_binaries" />

- Use `orca` binary file to count GDD of input graph.

<img src="/readme/mac/8_orca.png" alt="orca" />

- Use `gdd_agreement` binary file to generate comparison JSON of compared graphs.

<img src="/readme/mac/9_gdd_agreement_init.png" alt="gdd_agreement_init" />
<img src="/readme/mac/10_gdd_agreement_progress.png" alt="gdd_agreement_progress" />
<img src="/readme/mac/11_gdd_agreement_finish.png" alt="gdd_agreement_finish" />

##### [Linux]

- Setup will be very similar to Mac, with little difference e.g. `.bash_profile` is usually called `.bashrc` on Linux...

##### Comparison visualiser

- When generated GDD agreement comparison JSON, paste it (as text) in visualiser.
- https://gdd-agreement-comparison-visualiser.vercel.app/

&nbsp;

- (Visualiser can be served also locally.)
- `$ cd gdd/gdd_agreement_comparison_visualiser`
- `$ yarn start`

&nbsp;

- Generated comparison JSON has following interface:

```typescript
export interface IComparison {
  [fileName: string]: string;
}
export interface IData {
  Id: number;
  File_name: string;
  Group: string;
  Agreement_arithmetic: IComparison;
  Agreement_geometric: IComparison;
}
export interface IAllData {
  [fileName: string]: IData;
}
```

- Note that value in `IComparison` is number in range from `0.000000` to `1.000000`,<br />
  but is exported as `string` because it was counted with arbitrary (high) precison arithmetic<br />
  and was treated as text during enumeration.
- Also note that rounding to 6 decimal places was done only for convenient export purposes,<br />
  but GDD agreement enumeration itself was done in high precision.<br />
- We have done computations with `1200 bits` of precision in the mantissa of floating point numbers,<br />
  which gives real numbers with approximately `360 decimal places` in the end (when converted to decimal form).
- All precision parameters are just recommended,<br />
  because they were obtained by empirical way on standard computer with 16GB RAM,<br />
  as a result of best trade-off between high precision result and reasonable computation time.
- Of course, precision can be altered and set by editing source code, on demand.

&nbsp;

- GDD agreement comparison visualiser is simple web app with 1 text input for comparison JSON to paste in.

<img src="/readme/visualiser/1_visualiser_app.png" alt="visualiser" />

- Copy and paste generated GDD agreement comparison JSON.

<img src="/readme/visualiser/2_JSON_copy.png" alt="JSON_copy" />
<img src="/readme/visualiser/3_JSON_paste.png" alt="JSON_paste" />

- Comparison infographic tables are shown immediately after pasting valid comparison JSON.
- Comparison table displays (arithmetic or geometric) GDD agreement values between all compared graphs.
- For convenient display only id labels of graphs are shown in head row / column.
- Id labels are assigned to respective graphs (files) automatically from the definition order in gdd_agreement tool input file.
- Assigned ids can be checked directly in JSON file.
- The more similar are 2 compared graphs in terms of GDD agreement,<br />
  the closer their GDD agreement comparison value is to 1<br />
  and this shows off as more green in infographic.
- Similarly, the less similar compared graphs are, the closer is their GDD agreement value to 0<br />
  and this shows off as more red in the table.
- I.e. _x_ and _y_ coordinates in the table defines compared graphs<br />
  and the color of cell represents value of their GDD agreement.

<img src="/readme/visualiser/4_comparison_tables.png" alt="comparison_tables" />

- Scroll down to show scaled comparison tables,<br />
  where most red value is not 0 but the minimum value amongst all compared GDD agreement values.

<img src="/readme/visualiser/5_comparison_tables_scaled.png" alt="comparison_tables_scaled" />

- Optionally, you can change color of table head column / row for defined group labels,<br />
  if you have defined group labels for some graphs in gdd_agreement tool input file.

<img src="/readme/visualiser/6_group_labels.png" alt="group_labels" />
<img src="/readme/visualiser/7_group_labels_2.png" alt="group_labels_2" />

- Note that generated comparison JSON is exported in minified form.
- If you want to examine it, it is advised to format it nicely, first.
- You can use e.g. _Visual Studio Code_ with built-in Prettier formatter tool and Format Document directive.

<img src="/readme/visualiser/8_format_JSON_VSCode_format_directive.png" alt="VSCode_prettier" />
<img src="/readme/visualiser/9_format_JSON_VSCode.png" alt="VSCode_prettier_formatted" />

- You can abuse any standard web browser with Developer Tools console to format JSON nicely, as well.

<img src="/readme/visualiser/10_format_JSON_Web_browser.png" alt="web_browser_console" />
<img src="/readme/visualiser/11_format_JSON_Web_browser_formatted.png" alt="web_browser_JSON_formatted" />

##### Summary

We can sum up usage of our software into 3 simple steps:

- count GDDs (from input graphs) with ORCA
- generate GDD agreement comparison JSON (from counted GDDs)
- visualize comparison JSON in web app

##### Extra: nth root calculator

Try calculator for extracting the nth root of a positive real number.

<img src="/readme/win/16_win_nth_root_calculator.png" alt="calculator Win" />
<img src="/readme/mac/mac_nth_root_calculator.png" alt="calculator Mac" />
