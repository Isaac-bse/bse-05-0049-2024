# bse-05-0049-2024
assignment 1

import matplotlib.pyplot as plt
import numpy as np
months = ['07/2019','08/2019','09/2019','10/2019','11/2019']
searches = [50, 53, 59, 56, 62]
direct = [39, 47, 42, 51, 51]
social = [70, 80, 90, 87, 92]
x = np.arange(len(months))
width = 0.25  # width of each bar
fig, ax = plt.subplots(figsize=(8,6))
bars1 = ax.bar(x - width, searches, width, label='Searches', color='#1f77b4')  # Blue
bars2 = ax.bar(x, direct, width, label='Direct', color='#e377c2')              # Pink
bars3 = ax.bar(x + width, social, width, label='Social Media', color='#ffbf00') # Yellow
def annotate_bars(bars):
    for bar in bars:
        height = bar.get_height()
        ax.annotate(f'{height}',
                    xy=(bar.get_x() + bar.get_width()/2, height),
                    xytext=(0,3),  # offset above bar
                    textcoords="offset points",
                    ha='center', va='bottom')

annotate_bars(bars1)
annotate_bars(bars2)
annotate_bars(bars3)
ax.set_title('Visitors by web traffic sources', fontsize=14)
ax.set_ylabel('visitors\nin thousands', fontsize=10, rotation=0, labelpad=40)
ax.set_xlabel('months', fontsize=10)
ax.set_xticks(x)
ax.set_xticklabels(months)
ax.set_ylim(0, 110)
ax.legend()
plt.tight_layout()
plt.show()

