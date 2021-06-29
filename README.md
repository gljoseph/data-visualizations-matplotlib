# data-visualizations-matplotlib
#Create basic data visualizations using matplotlib

#import matplotlib and create a variable
import matplotlib.pyplot as plt 
import numpy as np
m = np.linspace(0,10,11)

c = 3 * 10**8 # Speed of Light
E = m*c**2 

import matplotlib.pyplot as plt 
#create a line graph of x axis of Mass and y axis of energy
plt.plot(m, E, color="red", lw=5) 
plt.xlabel('Mass in Grams')
plt.ylabel('Energy in Joules')
plt.title('E=mc^2')
plt.xlim(0,10)

#I've obtained some yield curve data from the US Treasury Dept. The data shows the interest paid for a US Treasury bond for a certain contract length. The labels list shows the corresponding contract length per index position.

labels = ['1 Mo','3 Mo','6 Mo','1 Yr','2 Yr','3 Yr','5 Yr','7 Yr','10 Yr','20 Yr','30 Yr']

july16_2007 =[4.75,4.98,5.08,5.01,4.89,4.89,4.95,4.99,5.05,5.21,5.14]
july16_2020 = [0.12,0.11,0.13,0.14,0.16,0.17,0.28,0.46,0.62,1.09,1.31]

fig = plt.figure()

ax = fig.add_axes([0,0,1,1])

ax.plot(labels, july16_2007, label="july16_2007")
ax.plot(labels, july16_2020, label="july16_2020")
ax.legend()

fig = plt.figure()

ax = fig.add_axes([0,0,1,1])

ax.plot(labels, july16_2007, label="july16_2007")
ax.plot(labels, july16_2020, label="july16_2020")
ax.legend(loc=(1.1,0.5)) #moved the legend outside of the graph for more space


#Used .subplots() to create this plot, which shows one year's yield curve
fig,axes = plt.subplots(nrows=2,ncols=1, figsize=(12,8))

axes[0].plot(labels, july16_2007)
axes[1].plot(labels, july16_2020)

axes[0].set_title('July 16, 2007')
axes[1].set_title('July 16, 2020')

fig.subplots_adjust(left=None,
    bottom=None,
    right=None,
    top=None,
    wspace=0.1,
    hspace=0.5,)
