# Python Hacks

### Concate two row from separate CSV file into one csv file
```python
import pandas as pd
temp1 = pd.read_csv("file1.csv")
col1=temp1['headername']
temp2 = pd.read_csv("file2.csv")
col2=temp2['headername']
finaldf= pd.concat([col1, col2], axis=1, ignore_index=True)
finaldf.to_csv('output.csv')
```

### Split lines from files based on range
```python
with open("srcfilename", "r") as f:
    with open("tgtfilename", "a") as f1:
        rows = f.readlines()[100001:]   //give your range
        f1.writelines(rows)
```

### Remove duplicate lines from texts
```python
import pandas as pd
file = open('filename.txt', 'r') 
store = file.readlines()
elements = set(store)
list= []
for s in elements:
    list.append(s.rstrip('\n'))
df = pd.DataFrame(list)
df.to_csv('filename.csv', index=False, header=False)
```
### Remove lines having less than 1 word
```python
file = open('input.txt','r')
data = []
for i in file:
    res = len(i.split())
    if res > 1:
        data.append(i)
file = open('out.txt', 'a') #write to file
for line in data:
     file.write(line)
file.close()
```

### Show applications on Left
```
gsettings set org.gnome.shell.extensions.dash-to-dock show-apps-at-top true
```
