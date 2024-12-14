# Dummy Check Reference Guide 
*"You should always do a dummy check to see if you forgot something. If you did, you successfully found a dummy: you." - LOCAL*
## Downloading Python Packages
- Accomplihed using `cmd.exe`.
- To install a module: `py -m pip install sampleModule`
- To update pip: `py -m pip install update pip`
- *Memory:* Sometimes, it calls for `python.exe` or `python3` instead of `py`. There is a way to assign the program as `py`, somewhere.
## Converting to .EXE File
- Accomplished using `PyInstaller` with `cmd`.
- Create conversion (single file): `pyinstaller C://DEST//TO//FILE.py --onefile`
- *Memory:* pyinstaller may be stlyized as PyInstaller, and/or --onefile is rewritten --oneFile. Can be misdirects but should be simple to know when you have failed.
- Makes a `build` and `dist` folder. Your file will be in `dist`.
## Adding files to `PATH` library
- Accomplished using `sys` directly in `python`.
- You can add a folder to your basic library with `sys.path.append('C:\\PATH\\TO\\FOLDER')`.
- You should then be able to import files from that folder.
- Especially useful for importing packages you downloaded on a computer you can't modify.
## Writing to a .txt file
- Accomplished using a build-in `file` module in `python`.
- The following will write a message to `name_of_file.txt`:
```
filename = 'name_of_file.txt'  # Sets the name of the file in the system
logfile = open(filename,'a')   # Opens the file or creates one if it doesn't exist
message = 'hello world'        # Message to be written
logfile.write(message+'\n')    # Write the message and then move onto the next line
logfile.close                  # Close the file
```
## Getting the time and date
- Accomplished using `datetime` module.
- Units: `%Y` for year, `%m` for month. `%d` for day, `%H` for hour, `%m` for minute, and `%S` for seconds.
```
import datetime
now = datetime.datetime.now()
timestamp = now.strftime("%Y-%m-%d %H:%m:%S")
print(timestamp)
>>> 2024-03-12 04:55:21
```
## Ripping information from a webpage
- Used to take raw HTML data, preferrably `UTF-8` with `urlopen`.
- Information for this and the next two sections can be found [here](https://realpython.com/python-web-scraping-practical-introduction/)
- The following will take all the information from Wikipedia's homepage:
```
from urllib.request import urlopen
url = 'https://en.wikipedia.org/wiki/Main_Page'
page = openurl(url)
html_bytes = page.read()
html = html_byted.decode('utf-8')
print(html)
```
## Defining search limits in raw data
- Both `title_index` and `end_index` are integers representing where the search term was found.
- `start_index` takes into account the fact that `.find` 
- *Memory:* This was particularly good at sectioning out different areas of the html for parsing later. *See next section.*
```
# Uses html data from last example
title_index = html.find('<title>')
start_index = title_index + len('<title>')
end_index = html_find('</title>')
title = html[start_index:end_index]
print(title)
>>> 'Wikipedia, the free encyclopedia'
