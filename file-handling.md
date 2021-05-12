# file handling

### package and compress
`zip` command: package and compress files

    zip <new-zip-file>.zip <file-to-compress>


file encryption with zip

    zip -e <file-encrypted.zip> <file-to-be-encrypted.txt>


directory encryption with zip

    zip -er <dir-encrypted.zip> <dir-to-be-encrypted/>


fix error in zip file: troubleshooting zip error `End-of-central-directory signature not found`

    zip -FF <file-with-errors.zip> --out <fixed-file-with-errors.zip>


### splitting and joining files
split for large file size

    split -b <size-of-split-pieces> <file-to-split> <split-file-prefix>


join files

    cat <split-file-prefix>* > <file-reasembled>


### integrity validation
validate file checksum (should be the same that the original file)

    md5sum <file-reasembled>
