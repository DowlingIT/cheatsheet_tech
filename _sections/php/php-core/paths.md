---
title: Paths & File Info
subtopic: php-core
group: File & DateTime
order: 2
---

#### Path functions

```php
dirname('/foo/bar/baz.txt')              // '/foo/bar'
basename('/foo/bar/baz.txt')             // 'baz.txt'
basename('/foo/bar/baz.txt', '.txt')     // 'baz'
realpath('../relative/path')             // absolute path or false
pathinfo('/foo/bar.txt')
// ['dirname'=>'/foo', 'basename'=>'bar.txt', 'extension'=>'txt', 'filename'=>'bar']
```

#### Magic constants (path-related)

```
__FILE__    absolute path to the current file
__DIR__     directory of the current file  (= dirname(__FILE__))
```

#### OS-aware constants & functions

```php
DIRECTORY_SEPARATOR   // '/' on Unix, '\\' on Windows
PATH_SEPARATOR        // ':' on Unix, ';' on Windows

sys_get_temp_dir()    // system temp directory
getcwd()              // current working directory
chdir('/path')        // change working directory
```
