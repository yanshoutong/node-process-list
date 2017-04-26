# process-list [![Build Status](https://travis-ci.org/reklatsmasters/node-process-list.svg?branch=master)](https://travis-ci.org/reklatsmasters/node-process-list) [![Build status](https://ci.appveyor.com/api/projects/status/oy0sbnie2a0d5hou?svg=true)](https://ci.appveyor.com/project/ReklatsMasters/node-process-list) [![npm](https://img.shields.io/npm/v/process-list.svg)](https://npmjs.org/package/process-list) [![license](https://img.shields.io/npm/l/process-list.svg)](https://npmjs.org/package/process-list) [![downloads](https://img.shields.io/npm/dm/process-list.svg)](https://npmjs.org/package/process-list) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

Cross-platform native method to receive the list of the launched processes.

### Install
You need build tools for native module.

1. Install Python 2.7
2. _Windows_: Install MSVC 2013 or newer
3. _Unix_: install GCC to 4.8 or newer
4. install node build tool `npm i -g node-gyp` See [node-gyp](https://npmjs.org/package/node-gyp) for more details.

```bash
npm i process-list
# or
yarn add process-list
```

### Supported OS

* `Windows` Windows 7+, Windows Server 2008 R2+
* `Linux` any Linux-based distributives
* `OS X` *Soon...*

### Usage
```js
const { snapshot } = require("process-list");

snapshot('pid', 'name').then(tasks => console.log(tasks))

// output
// [{
//    name: "1.exe",
//    pid: 1234,
// }, ... ]
```

### API

##### `snapshot(...field: String): Promise<[]Object>`
Returns the list of the launched processes.

##### `allowedFields: []String`
List of allowed fields.

* `pid: Number` - process pid
* `ppid: Number` - parent process pid
* `name: String` - process name (title)
* `path: String` - full path to the process binary file
* `threads: Number` - threads per process
* `owner: String` - the owner of the process
* `priority: Number` - an os-specific process priority
* `cmdline: String` - full command line of the process
* `starttime: Date` - the process start date / time
* `vmem: String` - virtual memory size in bytes used by process
* `pmem: String` - physical memory size in bytes used by process
* `cpu: Number` - cpu usage by process in percent

## License

MIT, Copyright (c) 2014 Dmitry Tsvettsikh
