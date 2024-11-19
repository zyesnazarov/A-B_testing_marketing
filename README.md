# A/B Testing of Marketing Campaign

## Introduction

Welcome to the repository for the A/B Testing of  marketing campaigns. This project aims to analyze and compare the performance of two different marketing campaigns (Control and Test) to determine which one performs better based on relevant features. 

A/B testing is a powerful method for making data-driven decisions, as it allows us to understand the impact of different variables on user behavior and campaign outcomes.

In the notebook you'll find detailed insights and analyses based on key performance metrics. By systematically comparing these metrics between the Control and Test campaigns, the test aims to identify the most effective marketing strategies for maximizing user engagement and conversion (two designed key KPIs)

## Visualizations
### Code

```python
fig, axes = plt.subplots(4,3, figsize = (16,12))
fig.suptitle('Control vs Test group comparison')
axes = axes.flatten()

for id, col_name in enumerate(column_list):
    sns.set_theme(style="whitegrid")
    sns.boxplot(data=df_concat, x='Campaign Name', y=col_name, palette='viridis', width=0.6, fliersize=5, ax=axes[id])
    axes[id].set_xlabel('Campaign Name', fontsize=10)
    axes[id].set_ylabel(f'{col_name}', fontsize=10)
    axes[id].set_title(f'{col_name}', fontsize=15)
    axes[id].tick_params(axis='x', labelsize=10)
    axes[id].tick_params(axis='y', labelsize=10)
    axes[id].grid(axis='y', linestyle='--', alpha=0.7)

# Hide unused subplots
for idx in range(len(column_list), len(axes)):
    axes[idx].set_visible(False)

plt.tight_layout(rect=[0, 0, 1, 0.96])
plt.show()
```
!['Control vs Test group feature presentation](