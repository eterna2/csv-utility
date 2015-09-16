# csv-utility
A simple package to guess the separator and linebreak characters for a "csv" file.

### Installation
#### Node
```
npm install csv-utility
```
#### Bower
```
bower install csv-utility
```

### Quick start
#### Node
```
var csvUtility = require('csv-utility');
var fs = require('fs');
var sample = fs.readFileSync('someFile.csv',{encoding:'utf8'});
var result = csvUtility.guessCSV(sample,{
  linebreak: [';'],
  sep: [':']
});
```

### Browser
```
var result = csvUtility.guessCSV(sample,{
  linebreak: [';'],
  sep: [':']
});
```

### Functions
#### csvUtility.guessCSV(sample[,opts])
* `sample` - a sample string of the raw csv (auto-cropped to 100kb)
* `opts` (optional) - a configuration to specify additional possible separator or linebreak characters
  * `linebreak` - an array of possible linebreak characters (default: ["\r\n", "\r", "\n"])
  * `sep` - an array of possible separator characters (default: [",", "\t", "|", ";"])
* `return` 
  * `linebreak` - the most possible linebreak characters
  * `sep` - the most possible separator characters

#### csvUtility.guessLinebreak(sample[,opts])
* `sample` - a sample string of the raw csv (auto-cropped to 100kb)
* `opts` (optional) - an array of possible linebreak characters (default: ["\r\n", "\r", "\n"])
* `return` - the most possible linebreak characters

#### csvUtility.guessSeparator(sample[,opts])
* `sample` - a sample string of the raw csv (auto-cropped to 100kb)
* `opts` (optional) - an array of possible separator characters (default: [",", "\t", "|", ";"])
* `return` - the most possible separator characters
