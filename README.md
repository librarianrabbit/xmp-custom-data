# xmp-custom-data
A project that aims to offer tools for storing, extracting and removing files from a image's XMP metadata by interfacing with [ExifTool](https://www.sno.phy.queensu.ca/~phil/exiftool/).

The project is divided between three bash scripts, intended to run on Linux systems with the bash shell script interpreter.

### xmp-store
The file [xmp-store](xmp-store) is the main script of the project. Its function is to store any given number of files (parts of a big file) into a image's XMP metadata on custom tags defined by the EXIFTAG shell variable, which is named *data* by default.

Usage:  
xmp-store *image.jpg* textfile-01.txt textfile-02.txt  
xmp-store *image.jpg* textfile-\*.txt

### xmp-extract
The file [xmp-extract](xmp-extract) is the second most important script. Its function is to retrieve the files and concatenate them, in the order they are present on the file, that is, the order handled by exiftool. The XMP tags are defined by the EXIFTAG shell variable, on the script.

Usage:  
xmp-extract *image.jpg*

### xmp-remove
The file [xmp-remove](xmp-emove) is a utility script that removes *all* XMP tags from an image. This is used to avoid the case in where old files, with higher amount, would be mixed with new files with less parts due to the current method.

Usage:  
xmp-remove *image.jpg*

## To-do and future enhancements
- Handle program arguments in a more flexible way and use command line switches.
- Allow custom tag name, name pattern, type and other variables to be defined by command line arguments.
- General cleanup and detect if exiftool is installed and if required scripts exists and can be called.
- Add scripts for EXIF metadata.
- Split and encode binary files with base64 to reduce required steps.
- Allow modification of the temporary config file template by providing a config file via command line.
- Remove the need of removing *all* XMP tags before adding the new files.
- Add more info to the metadata such as the number of files, total size.
- Allow adding multiple files and parts of file, this might require some extra metadata.
- Allow using different tag names for each file or file parts.
- Allow extracting files by tag or by tag pattern or by file name instead of concatenating entire output.
- Allow automatic decoding of binary files encoded with base64 to simplify the process.

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgements
This project heavily depends on the [ExifTool](https://www.sno.phy.queensu.ca/~phil/exiftool/), developed by Phil Harvey.
