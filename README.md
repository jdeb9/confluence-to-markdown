# Confluence to Markdown converter that works right now but probably not in a few months time

⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠿⠿⠿⠿⠿⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿<br>
⣿⣿⣿⣿⣿⣿⣿⣿⣿⠟⣉⡥⠶⢶⣿⣿⣿⣿⣷⣆⠉⠛⠿⣿⣿⣿⣿⣿⣿⣿<br>
⣿⣿⣿⣿⣿⣿⣿⡿⢡⡞⠁⠀⠀⠤⠈⠿⠿⠿⠿⣿⠀⢻⣦⡈⠻⣿⣿⣿⣿⣿<br>
⣿⣿⣿⣿⣿⣿⣿⡇⠘⡁⠀⢀⣀⣀⣀⣈⣁⣐⡒⠢⢤⡈⠛⢿⡄⠻⣿⣿⣿⣿<br>
⣿⣿⣿⣿⣿⣿⣿⡇⠀⢀⣼⣿⣿⣿⣿⣿⣿⣿⣿⣶⣄⠉⠐⠄⡈⢀⣿⣿⣿⣿<br>
⣿⣿⣿⣿⣿⣿⣿⠇⢠⣿⣿⣿⣿⡿⢿⣿⣿⣿⠁⢈⣿⡄⠀⢀⣀⠸⣿⣿⣿⣿<br>
⣿⣿⣿⣿⡿⠟⣡⣶⣶⣬⣭⣥⣴⠀⣾⣿⣿⣿⣶⣾⣿⣧⠀⣼⣿⣷⣌⡻⢿⣿<br>
⣿⣿⠟⣋⣴⣾⣿⣿⣿⣿⣿⣿⣿⡇⢿⣿⣿⣿⣿⣿⣿⡿⢸⣿⣿⣿⣿⣷⠄⢻<br>
⡏⠰⢾⣿⣿⣿⣿⣿⣿⣿⣿⣿⡿⠟⢂⣭⣿⣿⣿⣿⣿⠇⠘⠛⠛⢉⣉⣠⣴⣾<br>
⣿⣷⣦⣬⣍⣉⣉⣛⣛⣉⠉⣤⣶⣾⣿⣿⣿⣿⣿⣿⡿⢰⣿⣿⣿⣿⣿⣿⣿⣿<br>
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣧⡘⣿⣿⣿⣿⣿⣿⣿⣿⡇⣼⣿⣿⣿⣿⣿⣿⣿⣿<br>
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣇⢸⣿⣿⣿⣿⣿⣿⣿⠁⣿⣿⣿⣿⣿⣿⣿⣿⣿<br>
So you want to quit Confluence eh?
## Requirements

Setup
Clone and run `yarn` in root directory

## Usage

It's a good idea to create an 'output' folder somewhere to target with the `pathResult` parameter (where the output files will go)

In the converter's directory:

```
yarn start <inputPath> <outputPath> <runPostProcessScript> <verboseLogging>
```
e.g
`yarn start /Users/john/Downloads/targetfoldername /Users/john/Downloads/outputfoldername true`

### Parameters

parameter | description
--- | ---
`<inputPath>` | File or directory to convert with extracted Confluence export
`<outputPath>` | Directory to where the output will be generated to. Defaults to current working directory but you should probably specify a folder because I haven't tested it in a long time.
`<runPostProcessScript>` | OPTIONAL 'true' to run the file location cleanup and link fix script, 'false' or omitted to not run the script 
`<verboseLogging>` | OPTIONAL 'true' to log in detail, 'false' or omitted to run with default minimal logging

### Optional

To run the Post Process Script directly:

`bash <pathToUpdateLinksScript> <outputPath> <spaceName>`

When the script is run from the node project, the space name is derived from the root index.html "Space Detail" "Key" field.

### Parameters

| parameter                   | description                                                  |
| --------------------------- | ------------------------------------------------------------ |
| `<pathToUpdateLinksScript>` | Absolute path to `update-links.sh` in the `./src` folder of the project |
| `<outputPath>`              | Directory to the markdown files that need to be processed    |
| `<spaceName>`               | Name of the root confluence space                            |

### 
