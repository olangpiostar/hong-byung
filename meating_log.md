# hong-byung
this repository is for meeting Log

# 8.FEB.2021
#import
import numpy as np
import pandas as pd

#file reading
data = pd.read_csv('./data/train.csv')

#Mr, Mrs, Miss & etc name sorting
list_name = data.Name
test1 = list(map(lambda x:x.split('.')[0],list(data['Name'])))
test2 = list(map(lambda x:x.split(' ')[-1],test1))

#count name as dict type
count = {}
for i in test2:
    try: count[i] +=1
    except: count[i] = 1
print(count)

#Dataframe describing
data['Name_2']=test2
data.groupby('Name_2').describe()
----------------------------------------------------------------------------------
test = pd.read_csv('./data/test.csv')
test['Name']

test1 = list(map(lambda x:x.split('.')[0],list(test['Name'])))
test2 = list(map(lambda x:x.split(' ')[-1],test1))
count = {}
for i in test2:
    try: count[i] +=1
    except: count[i] = 1
print(count)
# Count Nan Data
df_train = pd.read_csv('./data/train.csv',na_values = ['',' ','na','nan'])
df_train.isna().sum()

# filtering age float type
age = data['Age'].dropna()
subage = list(map(lambda x:(x-x//1)>0,age))
subage.count(True)
