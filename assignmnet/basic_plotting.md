# Matplotlib Practice with Pandas Dataset

---

## Step 1: Create a Sample Dataset

We create a small **Sports Watch dataset** containing pulse rate and calories burned.

```python
import pandas as pd

data = {
    "Day": [1, 2, 3, 4, 5, 6, 7],
    "Average_Pulse": [80, 85, 78, 90, 95, 88, 76],
    "Max_Pulse": [120, 130, 125, 140, 150, 138, 118],
    "Calories_Burned": [240, 280, 220, 300, 320, 290, 210]
}

df = pd.DataFrame(data)
print(df)
```

---

## Step 2: Basic Line Plot

```python
import matplotlib.pyplot as plt

x = df["Average_Pulse"]
y = df["Calories_Burned"]

plt.plot(x, y)
plt.title("Basic Line Plot")
plt.xlabel("Average Pulse")
plt.ylabel("Calories Burned")
plt.show()
```

---

## Step 3: Using Different Markers

```python
plt.plot(x, y, marker="o")   # Circle marker
plt.title("Circle Markers")
plt.show()

plt.plot(x, y, marker="*")   # Star marker
plt.title("Star Markers")
plt.show()
```

---

## Step 4: Different Line Styles

```python
plt.plot(x, y, linestyle="dashed")
plt.title("Dashed Line")
plt.show()

plt.plot(x, y, linestyle="dotted")
plt.title("Dotted Line")
plt.show()
```

Shortcut styles:

```python
plt.plot(x, y, ls="--")  # dashed
plt.plot(x, y, ls=":")   # dotted
plt.show()
```

---

## Step 5: Marker Size and Edge Color

```python
plt.plot(x, y, marker="o", ms=10, mec="red")
plt.title("Marker Size and Edge Color")
plt.show()
```

* `ms` → marker size
* `mec` → marker edge color

---

## Step 6: Line Color and Width

```python
plt.plot(x, y, color="green", linewidth=3)
plt.title("Line Color and Width")
plt.show()
```

Short color version:

```python
plt.plot(x, y, c="r")  # red color
plt.show()
```

---

## Step 7: Plot Multiple Lines Together

```python
plt.plot(df["Day"], df["Average_Pulse"], marker="o", label="Average Pulse")
plt.plot(df["Day"], df["Max_Pulse"], marker="*", label="Max Pulse")

plt.legend()
plt.title("Pulse Comparison")
plt.xlabel("Day")
plt.ylabel("Pulse Rate")
plt.show()
```

---

## Step 8: Custom Fonts for Title and Labels

```python
font1 = {'family': 'serif', 'color': 'blue', 'size': 20}
font2 = {'family': 'serif', 'color': 'darkred', 'size': 15}

plt.plot(x, y, marker='o')

plt.title("Sports Watch Data", fontdict=font1, loc='left')
plt.xlabel("Average Pulse", fontdict=font2)
plt.ylabel("Calories Burned", fontdict=font2)

plt.show()
```

* `fontdict` allows custom font styling
* `loc='left'` moves the title to the left

---

## Step 9: Combined Example (Like Practice Code)

```python
ypoints = df["Calories_Burned"]

plt.plot(ypoints, ls='--', c='r')          # dashed red line
plt.plot(ypoints, marker='o')              # markers
plt.plot(df["Average_Pulse"], c='blue')    # second line

plt.title("Sports Watch Data", fontdict=font1, loc='left')
plt.xlabel("Average Pulse", fontdict=font2)
plt.ylabel("Calorie Burnage", fontdict=font2)

plt.show()
```

---
