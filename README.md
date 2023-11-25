## 1.将commander框架集成到该compiler中，实现命令行控制

### 例子：

#### 将input.js进行编译，输出 output
```node /bin/compiler -o output.js input.js```

#### 输出帮助
```node /bin/compiler -h```
```powershell
Usage: compiler [options] <files ...>

  Options:

    -h, --help                  output usage information
    -o, --out-file [out]        Compile all input files into a single file
    -t, --tokenize-file [out]   tokenize all input files into a single file
    -p, --parse-file [out]      parse all input files into a single file
    -s, --transform-file [out]  transform all input files into a single file
    -g, --generate-file [out]   generate all input files into a single file
    -V, --version               output the version number
```
## 2.实现更多的命令
```js
commander.option("-o, --out-file [out]", "Compile all input files into a single file");
commander.option("-t, --tokenize-file [out]", "tokenize all input files into a single file");
commander.option("-p, --parse-file [out]", "parse all input files into a single file");
commander.option("-s, --transform-file [out]", "transform all input files into a single file");
commander.option("-g, --generate-file [out]", "generate all input files into a single file");
```

## 3.实现packjson script 快速运行

```json
"scripts": {
    "dev": "node ./bin/compiler -o output input",
    "h"  : "node ./bin/compiler -h",
    "t"  : "node ./bin/compiler -t tokens input",
    "p"  : "node ./bin/compiler -p ast tokens",
    "s"  : "node ./bin/compiler -s newAst ast",
    "g"  : "node ./bin/compiler -g output2 newAst",
    "test" : "yarn t && yarn p && yarn s && yarn g"
}
```