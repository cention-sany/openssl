# OpenSSL bindings for Go

Please see http://godoc.org/github.com/spacemonkeygo/openssl for more info

### License

Copyright (C) 2014 Space Monkey, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

### Using on Windows
1. Install [mingw-w64](http://mingw-w64.sourceforge.net/)
2. Install [pkg-config-lite](http://sourceforge.net/projects/pkgconfiglite)
3. Build (or install precompiled) openssl for mingw32-w64
4. Set __PKG\_CONFIG\_PATH__ to the directory containing openssl.pc
   (i.e. c:\mingw64\mingw64\lib\pkgconfig)

### Forked version

This openssl is forked because we need it to be able to compiled with OpenSSL 
0.9.8zg. If you have Openssl development package (on Ubuntu machine 
**sudo apt-get install libssl-dev**) installed then you should not have any 
problem in **go install** this package. You may use Linux terminal command to 
find out where the libssl.pc is, as below:
```
$ locate libssl.pc
$ /usr/lib/x86_64-linux-gnu/pkgconfig/libssl.pc
```

You will find following pkgconfig file for Cention development environment.
```
$ /cention/lib/pkgconfig/libssl.pc
```
We can ask **go install** to use cention-openssl (modified pc file from 
cention-openssl libssl.pc) as its pkg-config path lookup, as below:
```
$ PKG_CONFIG_PATH=$GOPATH/src/github.com/cention-sany/openssl/pkgconfig \
go install github.com/cention-sany/openssl
```
