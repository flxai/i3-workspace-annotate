# i3-workspace-annotate
## About
Annotate an i3 workspace with a Font Awesome icon

## Prerequisites
This script utilizes the following applications:
 * `bash`
 * `cut`
 * `dmenu`
 * `grep`
 * `jq`

## Font Awesome
The script searches for [human readable names of Font Awesome icons](https://github.com/FortAwesome/Font-Awesome/blob/master/less/variables.less). The file `fa` was extracted as follows:

```bash
url="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/master/less/variables.less"
echo > fa
while read -r line; do
    printf "$line\n" >> fa
done <<< $(curl -s "$url" | grep '@fa-var-' | sed -r 's/@fa-var-([^:]+): "\\([^"]+)";/\1 \\u\2/')
```
