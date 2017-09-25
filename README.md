# i3-workspace-annotate
## About
Annotate an i3 workspace with a Font Awesome icon

## Prerequisites
This script utilizes the following applications:
 * `bash`
 * `cut`
 * `dmenu`
 * `grep`
 * `jp`

## Font Awesome
The script searches for [human readable names of Font Awesome icons](https://github.com/FortAwesome/Font-Awesome/blob/master/less/variables.less). The files `variables` and `icons` were extracted as follows.

### `variables`
```bash
curl -s "https://raw.githubusercontent.com/FortAwesome/Font-Awesome/master/less/variables.less" | grep '@fa-var-' | sed -r 's/@fa-var-([^:]+): "([^"]+)";/\1/' > variables
```

### `icons`
```bash
curl -s "https://raw.githubusercontent.com/FortAwesome/Font-Awesome/master/less/variables.less" | grep '@fa-var-' | sed -r 's/@fa-var-([^:]+): "\\([^"]+)";/\2/' > icons
```
