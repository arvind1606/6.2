# 6.2

import matplotlib.pyplot as plt
import pandas as pd

url='https://raw.githubusercontent.com/Geoyi/Cleaning-Titanic-Data/master/titanic_original.csv'
titanic = pd.read_csv(url)
df = pd.DataFrame(titanic)
x= df.sex
m=f=0
for i in x:
    if i=='male':
        m+=1
    elif i=='female':
        f+=1
slices=[m,f]
plt.pie(slices,labels=['Male','Female'],colors=['r','b'],autopct='%1.1f%%',startangle=90)
plt.title('Pie Chart')
plt.show()
cols=[]
for y in df.sex:
    if y=='male':
        cols.append('b')
    else:
        cols.append('r')
plt.scatter(df['age'], df['fare'],c=cols, alpha=0.5)
plt.colorbar();
