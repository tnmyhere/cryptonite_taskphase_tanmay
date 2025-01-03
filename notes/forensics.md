# Forensics
## File formats
- Use the command `$ file [file]` from the `libmagic` library to identify the filetype of a file. However, this might lead to no useful information/may be a red herring.
- Files are sometimes embedded within files, in which case the `file` command only tells us about the file contained inside another file, leading to misleading info.
- There are also other available softwares like [TrID](https://mark0.net/soft-trid-e.html) which cover obscure & proprietary data formats and show probability percentages.
- File formats aren't very useful alone usually. Example, a file can be another format, or one file could be appended to another.

## Magic bytes
Magic bytes are unique sequences of bytes at the beginning of a file in the recognized by an operating system, which can be used to recognise a file. We can inspect the file through any hex editor. Then the [list of file signatures](https://en.wikipedia.org/wiki/List_of_file_signatures) is a godsend. The hyperlink showcases a [good explainer](https://www.netspi.com/blog/technical-blog/web-application-pentesting/magic-bytes-identifying-common-file-formats-at-a-glance/) for reference.

## File within file
Tools like [binwalk](https://github.com/ReFirmLabs/binwalk) help us identify files within other files. Simply run `$ binwalk [file]` to obtain the list of potential files.

## Strings
- the  `strings` command to look for printable strings.
- you can use `hexdump` command instead and then grep the output for a particular string or magic bytes.

## Encodings
There are a lot of online decoders, including [dcode.fr](https://dcode.fr/), [cryptii](https://cryptii.com) and [CyberChef](https://gchq.github.io/CyberChef/). These can help you decode from a variety of data formats including hexadecimal, binary, ASCII, base 64, etc. among other decodings. [dcode.fr's cipher identifier](https://www.dcode.fr/cipher-identifier) and [boxentriq](https://www.boxentriq.com/code-breaking/cipher-identifier) also have cipher identifier, which can potentially give ideas about the encoding when stuck at something.
