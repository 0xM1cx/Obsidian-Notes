## Steganography
> Reference: https://0xrick.github.io/lists/stego/#steganography
- Steghide - This is a steganography program that hides data in various kinds of image and audio files, only supports these file formats : `JPEG, BMP, WAV and AU`. but it’s also useful for extracting embedded and encrypted data from other files.
			`steghide info file`: displays info about a file whether it has embedded data or not
			`steghide extract -sf file`: extracts embedded data from a file
- Foremost - Is a program that recovers files based on their headers, footers and internal data structures. this is useful in dealing with png images.
			`foremost -i file`: extracts data from the given file
- Stegsolve - This is a tool that applies color filter on images because there are times where text are hidden in the image and the only way to view it is to apply some color filters or play with color levels. This tool makes it easier unlike GIMP  or Photoshop
-  Exiftool - Sometimes important stuff is hidden in the metadata of the image or the file, exiftool can be very helpful to view the metadata of the files. 
			`exiftool file`: shows the metadata of the give file
- Binwalk - is a tool for searching binary files like images and audio files for embedded files and data. 
			`binwalk file`: Displays the embedded data in the given file
			`binwalk -e file`: Displays and extracts the data from the given file

- Zsteg - tool that detects hidden data in png and bmp files
			`zsteg -a file`: Runs all the methods on the given file
			`zsteg -E file`: Extracts data from the given payload
- Wavsteg - tool that can hide data and files in wav files and can also extract data from wav files.
			`python3 WavSteg.py -r -s soundfile -o outputfile`: extracts data from a wav sound file and outputs the data into a new file
- Sonic visualizer - tool for viewing and analyzing the contents of audio files, however it can be helpful when dealing with audio steganography. You can reveal hidden shapes in audio files

### Web Tools
- Unicode Text Steganography - web tool for unicode steganography, it can encode and decode text
- dcode.fr - there are times when solving steg challenges  you will need to decode some text. This tool has many decoders for a lot of ciphers and can be really helpful

### Bruteforcers
- StegCracker - a tool that bruteforces passwords using steghide
- Fcrackzip - sometimes the extracted data is  a password protected zip, this tool bruteforces zip archives.  
			`fcrackzip -u -D -p wordlist.txt file.zip`: bruteforces the given zip file with the passwords from the given wordlist.


## Web Exploitation

## Digital Forensics
- [DFIR Tools That Are Commonly Used](https://github.com/mikeroyal/Digital-Forensics-Guide#digital-forensics-tools-libraries-and-frameworks)
- 
## Cryptography
- [RsaCtfTool](https://github.com/RsaCtfTool/RsaCtfTool) RSA attack tool (mainly for ctf) - retreive private key from weak public key and/or uncipher data

## Pwning




## COMPLETE LIST:
- [CTF TOOL LIST](https://github.com/zardus/ctf-tools)