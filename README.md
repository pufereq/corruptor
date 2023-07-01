# corruptor

`corruptor` is a Python script that allows you to easily corrupt files by randomly overwriting bytes within them.

## Why?

I wanted to break some Linux VMs by corrupting some files randomly. First I tried `shred` from GNU coreutils but it corrupts bytes from the beginning and not in random order. So I went ahead and coded this.

## Usage Cases

- Testing and Debugging: Simulate file corruption scenarios to test applications, data recovery mechanisms, and error handling procedures.
- Data Security: Assess the effectiveness of backup systems, data integrity checks, and security measures against data corruption attacks.
- Research and Analysis: Investigate the impact of data corruption on file formats and analyze software behavior when encountering corrupted files.
- Data Recovery: Use controlled corruption to recover inaccessible portions of files.
- Education and Training: Demonstrate file system concepts, error handling, and data recovery techniques in educational settings.
- Fun: Use corruption to break stuff for fun

## Usage

```
usage: corruptor [-h] [-c COUNT] [-v] filename

Corrupt files easily!

positional arguments:
filename path to the file to corrupt

optional arguments:
-h, --help show this help message and exit
-c COUNT, --count COUNT
count of bytes to corrupt (default: 3)
-v, --verbose be verbose
```

## Examples

Corrupting a file with the default count of 3 bytes:

```shell
$ python corruptor.py path/to/file.ext
Getting file size... DONE: 1024 bytes

Pass 1/3
Pass 2/3
Pass 3/3

File corrupted successfully.
```

Corrupting a file with a custom count of 5 bytes and displaying verbose output:


```shell
$ python corruptor.py -c 5 -v path/to/file.ext
Getting file size... DONE: 2048 bytes

Pass 1/5
Generating random offset... DONE: 1016
Byte at offset 1016: b'\x03'
Generating random byte... DONE: b'\xfe'
Overwriting b'\x03' with b'\xfe'... DONE

Pass 2/5
Generating random offset... DONE: 529
Byte at offset 529: b'\x7f'
Generating random byte... DONE: b'\x08'
Overwriting b'\x7f' with b'\x08'... DONE

Pass 3/5
Generating random offset... DONE: 1443
Byte at offset 1443: b'\xc7'
Generating random byte... DONE: b'\x00'
Overwriting b'\xc7' with b'\x00'... DONE

Pass 4/5
Generating random offset... DONE: 1827
Byte at offset 1827: b'\x12'
Generating random byte... DONE: b'\x81'
Overwriting b'\x12' with b'\x81'... DONE

Pass 5/5
Generating random offset... DONE: 768
Byte at offset 768: b'N'
Generating random byte... DONE: b'2'
Overwriting b'N' with b'2'... DONE

File corrupted successfully.
```

## License

This project is licensed under the GNU General Public License v3.0. For more details, see the [LICENSE](LICENSE) file.
