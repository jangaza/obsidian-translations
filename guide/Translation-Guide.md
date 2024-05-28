# Obsidian Translation Guide
*work in progress*

Open issue here or at [official repo](https://www.github.com/obsidianmd/obsidian-translations/issues) to get help

### Translation Guide:
```
#python 3.9.4
import json

file_name = 'cs.json'

with open(file_name, 'r', encoding='utf-8') as f:
    data = json.load(f)

values_list = [value for value in data['plugins']['sync'].values()]

for i in values_list:
    print(i)
```

1. edit file_name and `data['plugins']['sync']` with desired keys
2. copy output
3. paste it into [deepl.com](https://www.deepl.com/translator), free tier has 1500 characters cap
4. with [cs.termbase.md](https://github.com/obsidianmd/obsidian-translations/blob/master/cs.termbase.md) in mind edit lines
```
#python 3.9.4
import json

file_name = 'cs.json'

values_list = """
Synchronizace
Synchronizujte své soubory pomocí Obsidian Sync.
"""

values_to_write = values_list[1:-1].split("\n")

# Load existing data
with open(file_name, 'r', encoding='utf-8') as f:
    data = json.load(f)

keys = list(data['plugins']['sync'].keys())
for i in range(min(len(keys), len(values_to_write))): # Choose whichever length is smaller
    data['plugins']['sync'][keys[i]] = values_to_write[i]

with open(file_name, 'w', encoding='utf-8') as f:
    json.dump(data, f, ensure_ascii=False, indent=4)
```
4. make backup of cs.json
5. fill values_list with the output from deepl and run the script
6. convert to tabs: 
    - ctrl+shift+P ">convert indentation to tabs"
7. compare with old cs.json and en.json
    - replace translated **{{ strings }}**
    - make sure line count is same
    - check for blank or cut lines

<br>
<br>

**TODO**:
- code explanation
- example images