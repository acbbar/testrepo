# testrepo

## editing the file

import matplotlib.pyplot as plt

# Define cash flows and time points
time = [0, 1, 2, 3, 4, 5]  # Time points
cash_flows = [-500, 100, 100, 100, 100, 100]  # Cash flow values

# Set up the plot
fig, ax = plt.subplots()
ax.axhline(0, color='black', linewidth=1)  # Horizontal axis

# Plot cash flows using arrows
for t, flow in zip(time, cash_flows):
    if flow < 0:
        ax.annotate(f'${flow}', xy=(t, flow), xytext=(t, flow - 50),
                    arrowprops=dict(facecolor='red', shrink=0.05),
                    fontsize=12, ha='center', color='red')
    else:
        ax.annotate(f'${flow}', xy=(t, flow), xytext=(t, flow + 20),
                    arrowprops=dict(facecolor='blue', shrink=0.05),
                    fontsize=12, ha='center', color='blue')

# Label the axes
ax.set_xlabel("Time Periods")
ax.set_ylabel("Cash Flow ($)")
ax.set_title("Project Cash Flow Diagram")

# Set the limits
ax.set_xlim(-0.5, 5.5)
ax.set_ylim(-600, 200)

# Display the plot
plt.show()
