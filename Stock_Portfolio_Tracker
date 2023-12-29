import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import random

from google.colab import files
files.upload()

df=pd.read_csv('my_portfolio.csv')

#Get total invested money
Total_amount=sum(df['Amount']*df['Average Price'])
Total_amount=round(Total_amount,2)
Total_amount

#Visualise and some addnl information
stock_tickers=df['Ticker'].values
sizes=df['Amount']*df['Average Price']

listOfZeros=[0]*df.shape[0]
n=random.randint(0,df.shape[0]-1)
listOfZeros[n]=0.1
explode = listOfZeros

#Create Figure
fig1,ax1=plt.subplots(figsize=(10,10))

#Plot the pie chart
ax1.pie(sizes,explode=explode,labels=stock_tickers,autopct='%.2f%%',shadow='True',startangle=360)

#set title
ax1.set_title('Portfolio Pie Chart',color='Purple',fontsize=22)

#Add text to the visual
x=-1.75
y=1
ax1.text(x,y,'Overview: ',fontsize=24,color='Purple')
y_counter=0.12
for i in range (0,df.shape[0]):
  ax1.text(x,0.88 - y_counter,df['Ticker'][i]+': $ '+str(round(df['Amount'][i]*df['Average Price'][i],2)),fontsize=16,color='Black')
  y_counter=y_counter+0.12
