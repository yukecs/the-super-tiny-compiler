1.将commander框架集成到该compiler中，实现命令行控制
node /bin/compiler -o output.js input.js
将output进行编译，输入 input.js
node /bin/compiler -h
输出帮助 seens like
Options:

  -h, --help                   output usage information
  -t, --source-maps-inline     Append sourceMappingURL comment to bottom of code
  -s, --source-maps            Save source map alongside the compiled code when using --out-file and --out-dir flags
  -w, --whitelist [whitelist]  Whitelist
  -b, --blacklist [blacklist]  Blacklist
  -o, --out-file [out]         Compile all input files into a single file
  -d, --out-dir [out]          Compile an input directory of modules into an output directory
  -V, --version                output the version number