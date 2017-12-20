# scryfalldler
Simple (fast and bad done) php automated script for download and pack card images using [scryfall.com](http://scryfall.com) API site ready for XMage.

## How to run
You only need **php** binary (instaled in your system or uncompressed) with **curl** and **zip** extensions enabled (if not an error message will show and script ends his execution).

### GNU/Unix based
Download the script where you want, for example using:
```
> wget https://raw.githubusercontent.com/nachazo/scryfalldler/master/scryfalldler
```
And then simply run it with the desired options (this is a test command):
```
> php scryfalldler -l
```
This will show a list with the avaiable sets.

### Windows based
Download the script where you want, for example using (this is Windows PowerShell):
```
> wget https://raw.githubusercontent.com/nachazo/scryfalldler/master/scryfalldler -OutFile scryfalldler
```
And then simply run it with the desired options (this is a test command):
```
> php scryfalldler -l
```
This will show a list with the avaiable sets.

If you don't have php installed or path in file system, you could invoke pointing php.exe file, for example using:
```
> C:\myPhpFolder\php scryfalldler -l
```

## Example commands
* This will download "Commander 2017" set cards and zip to "C17.zip" in base folder:
  * `php scryfalldler -s c17`
* This will download "Commander 2017" set cards and zip to "C17.zip" in specified folder:
  * `php scryfalldler -s c17 -f /home/user/xmage/myImages`
* This will download "Commander 2017" cards art crop image set:
  * `php scryfalldler -s c17 -z art_crop`
* This will download "Commander 2017" set cards behind proxy:
  * `php scryfalldler -s c17 -p http://myproxy:8888`
* This will download "Commander 2017" cards from Wizards Gatherer:
  * `php scryfalldler -s c17 -z art_crop`

Of course you can combine parameters, all list in "Help" section (or type `php scryfalldler`).

## Help
Command `php scryfalldler -h` shows:
```yaml
Usage:
  php scryfalldler [arguments] 

Arguments: 
  All arguments also accept "--". 
    -h, -help	Shows help (this info). 
    -l, -list	List avaiable sets for download with codes from Scryfall. 
    -s, -set	Launch download cards operation from the specified set from the site. 
    -z, -size	The size for downloaded images ("image_uris" from Scryfall API).
                Special value "gatherer" downloads Wizards Gatherer image if avaiable. 
                Default value: large. 
                Possible values: small, normal, large, png, art_crop, border_crop, gatherer.  
    -f, -folder	Destination folder for the zip file (not tested with relative ones). 
    -d, -debug	With this, script only show messages but not download or create folder. 
    -t, -test	Test your connection with Scryfall. 
    -p, -proxy	Set proxy for connections (format http://proxy:port). 

Site: 
  https://github.com/nachazo/scryfalldler 
```