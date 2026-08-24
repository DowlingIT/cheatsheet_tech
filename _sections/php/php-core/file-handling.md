---
title: File Handling
subtopic: php-core
group: File & DateTime
order: 1
---

#### Simple read / write

```php
$text  = file_get_contents('/path/to/file.txt');
file_put_contents('/path/to/file.txt', $text);
file_put_contents('log.txt', $line . PHP_EOL, FILE_APPEND);
$lines = file('/path/file.txt', FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
```

#### Stream-based (large files)

```php
$fh = fopen('/path/to/file.txt', 'r');  // modes: r  r+  w  a  a+  x
while (!feof($fh)) {
    $line = fgets($fh);
}
fclose($fh);

fwrite($fh, 'data');
rewind($fh);          // seek to start
fseek($fh, 100);      // seek to byte 100
```

#### Filesystem ops

```php
file_exists($p)  is_file($p)  is_dir($p)  is_readable($p)  is_writable($p)
filesize($p)     filemtime($p)             // size in bytes, modified timestamp
mkdir('/path', 0755, recursive: true)
rmdir('/path')   unlink('/path/file.txt')
copy($src, $dst) rename($old, $new)
glob('/path/*.txt')                        // wildcard file list
```
