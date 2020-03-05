# installe-generate-rsa-keypair-fial
installe generate-rsa-keypair fial

## Error
```
> generate-rsa-keypair@0.2.1 install /Users/me_project/soft/xxxx-sample-master/functions/node_modules/generate-rsa-keypair
> node-gyp rebuild

xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance

xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance

Traceback (most recent call last):
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/gyp_main.py", line 16, in <module>
    sys.exit(gyp.script_main())
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/__init__.py", line 545, in script_main
    return main(sys.argv[1:])
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/__init__.py", line 538, in main
    return gyp_main(args)
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/__init__.py", line 523, in gyp_main
    generator.GenerateOutput(flat_list, targets, data, params)
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/generator/make.py", line 2170, in GenerateOutput
    part_of_all=qualified_target in needed_targets)
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/generator/make.py", line 795, in Write
    self.Pchify))
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/generator/make.py", line 1190, in WriteSources
    cflags = self.xcode_settings.GetCflags(configname)
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/xcode_emulation.py", line 551, in GetCflags
    archs = self.GetActiveArchs(self.configname)
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/xcode_emulation.py", line 420, in GetActiveArchs
    xcode_archs_default = GetXcodeArchsDefault()
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/xcode_emulation.py", line 118, in GetXcodeArchsDefault
    xcode_version, _ = XcodeVersion()
  File "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib/gyp/xcode_emulation.py", line 1265, in XcodeVersion
    version = re.match(r'(\d\.\d\.?\d*)', version).groups()[0]
AttributeError: 'NoneType' object has no attribute 'groups'
gyp ERR! configure error 
gyp ERR! stack Error: `gyp` failed with exit code: 1
gyp ERR! stack     at ChildProcess.onCpExit (/usr/local/lib/node_modules/npm/node_modules/node-gyp/lib/configure.js:336:16)
gyp ERR! stack     at emitTwo (events.js:126:13)
gyp ERR! stack     at ChildProcess.emit (events.js:214:7)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:198:12)
gyp ERR! System Darwin 19.0.0
gyp ERR! command "/usr/local/bin/node" "/usr/local/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /Users/me_project/soft/thermoworks-iot-core-sample-master/functions/node_modules/generate-rsa-keypair
gyp ERR! node -v v8.11.2
gyp ERR! node-gyp -v v3.6.2
gyp ERR! not ok 
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.11 (node_modules/fsevents):
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.11 install: `node-gyp rebuild`
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: Exit status 1

npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! generate-rsa-keypair@0.2.1 install: `node-gyp rebuild`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the generate-rsa-keypair@0.2.1 install script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/admin/.npm/_logs/2020-03-05T01_24_13_482Z-debug.log

```
According to the prompt, there is a problem with Xcode's path

xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance

1. 执行运行脚本的命令：报错如下“

xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance

”

2. 执行“

xcodebuild -showsdks

”，报错如下“
xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance

”

3. 执行“

sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer/

”切换到当前Xcode路径下

4. 执行"

 xcodebuild -showsdks

"：


5. 执行"

xcrun --sdk iphoneos --show-sdk-path

"

success “

/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS11.2.sdk

”

然后再到cmd模式下 执行 nmp install 成功

look at link https://blog.csdn.net/li15809284891/article/details/79629190


