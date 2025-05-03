
# Git Assignment: HeroVired

This repository contains the solutions and demonstration for the Git assignment from HeroVired. The assignment requires you to utilize Git and GitHub to manage the development of a simple Python application. You will implement various essential Git concepts, including branching, merging, pull requests, code review, adding new features, handle bug fixes, manage large binary files with Git LFS and use Git stash to switch between incomplete tasks.

---

## 📁 Project Overview

This repository contains three main components:

- **CalculatorPlus**: A simple calculator supporting basic arithmetic operations and square root functionality.
- **Large File Handling**: Implements Git LFS for managing large files (>200MB).
- **Geometry Calculator**: Calculates the area of a circle and a rectangle.

---

## 🛠️ Repository Setup & Usage

1. **Cloning the Repository:**
```bash
git clone https://github.com/govind02420/git_assignment_HeroVired.git
cd git_assignment_HeroVired
```
2. **Installing Dependencies:**
- Ensure Python is installed.
- No external dependencies are required for the calculator scripts.

---

## 🧑‍💻 Branching Strategy

### Main Branch (`main`)
- Stable, production-ready code.
- Releases are tagged here (`v1.0`, `v2.0`).

### Development Branch (`dev`)
- Integrates features and bug fixes.
- Merges from feature branches.
- Final testing before release.

### Feature Branches
- `feature/sqrt`: Adds square root functionality.
- `feature/circle-area`: Adds circle area calculation.
- `feature/rectangle-area`: Adds rectangle area calculation.
- `lfs`: For handling large files with Git LFS.

---
## 🔄 Workflow

### 1. CalculatorPlus Workflow Summary

It focus on implementing a new feature (square root) and handling a critical bug fix in the `CalculatorPlus` application using Git branching, merging, and pull requests.

### Project Files

The core file for this project is `calculator.py`.

```python
import math

class Calculator:

    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def multiply(self, a, b):
        return a * b

    def divide(self, a, b):
    #    if b == 0:
    #       raise ValueError("Cannot divide by zero.")
        return a / b
# TODO: Implement the following function to calculate the square root of a number.
#     def square_root(self, x):
#         return math.sqrt(x)
# You need to uncomment the above function and complete its implementation to add the square root feature.

if __name__ == "__main__":
    calculator = Calculator()

num1 = 16
num2 = 4

print(f"{num1} + {num2} = {calculator.add(num1, num2)}")
print(f"{num1} - {num2} = {calculator.subtract(num1, num2)}") 
print(f"{num1} * {num2} = {calculator.multiply(num1, num2)}")
print(f"{num1} / {num2} = {calculator.divide(num1, num2)}")

# TODO: Uncomment and test the square root feature.
# num3 = 25
# print(f"The square root of {num3} = {calculator.square_root(num3)}")
```

### Steps:
1. **Repository Setup**
   - Created private repo: `git_assignment_HeroVired`
   - Added collaborator for code review
   
2.  **Create a `dev` branch and add initial code:**
    *   Create a new branch named `dev` from the `main` branch.
    *   Create a file named `calculator.py` in the root of the repository.
    *   Paste the initial `Calculator` class code into `calculator.py`.
    *   Add and commit the changes to the `dev` branch.
    *   Push the `dev` branch to GitHub.

    ```bash
    git checkout -b dev
    # Create calculator.py and add the code
    git add calculator.py
    git commit -m "Add CalculatorPlus basic operations code"
    git push origin dev
    ```

3.  **Merge `dev` into `main` and create Release v1:**
    *   Switch to the `main` branch.
    *   Merge the `dev` branch into `main`.
    *   Push the `main` branch to GitHub.
    *   On GitHub, create a Release named `CalculatorPlus - Version 1` with the tag `v1.0`.

``` bash
    git checkout main
    git merge dev
    git push origin main
```

- Create a GitHub Release (`Version 1`) for the **CalculatorPlus app**

> To create a new release for this project on GitHub, follow these steps:
>
> 1.  Navigate to your repository on GitHub.
> 2.  Click on the **Releases** tab (usually found near the top of the page, under the repository name).
> 3.  Click the **Draft a new release** button.
> 4.  In the **Tag version** field, enter `v1.0`.
> 5.  In the **Release title** field, enter `CalculatorPlus - Version 1`.
> 6.  In the **Description** field, add a brief summary of the release : `Initial release of CalculatorPlus app with basic arithmetic operations.`
> 7.  Click the **Publish release** button.
>
> This will create a new release tag (`v1.0`) and a release entry on your repository's releases page.

4.  **Create `feature/sqrt` branch and implement the feature:**
    *   Create a new branch named `feature/sqrt` from the `main` branch.
    *   Uncomment the `square_root` function in `calculator.py`.
    *   Add and commit the changes to the `feature/sqrt` branch.

    ``` bash
    git checkout -b feature/sqrt main
    # Uncomment the square_root function in calculator.py
    git add calculator.py
    git commit -m "Add squre root functionality"
    git push origin feature/sqrt
    ```

   - Implemented `square_root` function
   
```python
# TODO: Implement the following function to calculate the square root of a number.
     def square_root(self, x):
         return math.sqrt(x)

# TODO: Uncomment and test the square root feature.
 num3 = 25
 print(f"The square root of {num3} = {calculator.square_root(num3)}")
```

5.   **Handle critical bug fix (Simulated Scenario):**
 * **Switch to `dev` branch:** Imagine a critical bug is reported in the `main` branch that needs immediate fixing. Switch to the `dev` branch.
 * **Implement the bug fix:** Modify the `divide` function in `calculator.py` on the `dev` branch to handle division by zero.
 * **Commit the bug fix:** Add and commit the bug fix to the `dev` branch.
 * **Push the bug fix:** Push the `dev` branch to GitHub.
 * **Merge bug fix into `main`:** Switch to the `main` branch, merge the `dev` branch, and push `main`.
 * **Update `feature/sqrt` with the bug fix:** Switch back to the `feature/sqrt` branch and merge the `main` branch to incorporate the bug fix.

```bash
    git checkout dev
    # Modify the divide function in calculator.py
    git add calculator.py
    git commit -m "Fix divide function to prevent division by zero"
    git push origin dev

    git checkout main
    git merge dev
    git push origin main

    git checkout feature/sqrt
    git merge main # Incorporate the bug fix from main
    ```
   - Fixed division by zero bug in `dev`

 ```python
   # You need to uncomment the if in divide function and Fixed division by zero bug.
    def divide(self, a, b):
        if b == 0:
           raise ValueError("Cannot divide by zero.")
        return a / b   
   ```

6.  **Create Pull Request for `feature/sqrt` to `dev`:**
    *   Push the `feature/sqrt` branch to GitHub.
    *   On GitHub, create a pull request from the `feature/sqrt` branch targeting the `dev` branch.

```bash
    git push origin feature/sqrt
    # Go to GitHub and create the Pull Request
```

7.  **Request Code Review and Merge:**
    *   Request a code review from your added collaborator.
    *   Address any review feedback and make necessary improvements.
    *   Once the pull request is approved, merge the `feature/sqrt` branch into the `dev` branch through the GitHub UI.


8.  **Test in `dev` and Merge into `main`:**
    *   Switch back to your local `dev` branch and pull the latest changes from GitHub to get the merged `feature/sqrt` code.
    *   Perform final testing in the `dev` branch to ensure everything works as expected.
    *   Switch to the `main` branch, pull the latest changes, and merge the `dev` branch into `main`.
    *   Push the `main` branch to GitHub.

    ```bash
    git checkout dev
    git pull origin dev

    # Perform final testing

    git checkout main
    git pull origin main
    git merge dev
    git push origin main
    ```

9. **Create Release v2:**
    *   On GitHub, create a new Release named `CalculatorPlus - Version 2` with the tag `v2.0`.

---
---
---
### 2. Git LFS Integration Workflow Summary

### Creating a Large File
- Create or copy a large file (>200MB), e.g. a dummy ZIP file.

### Steps:

1.  **Install Git LFS:**
    *   If you haven't already, install Git LFS on your system. Follow the instructions on the official Git LFS website ([https://git-lfs.github.com/](https://git-lfs.github.com/)).

2.  **Create `lfs` branch:**
    *   Create a new branch named `lfs` from the `main` branch.

    ```bash
    git checkout -b lfs
    ```

3.  **Initialize Git LFS for the repository:**
    *   Run the following command in your repository's root directory:

    ```bash
    git lfs install
    ```

4.  **Track large binary files:**
    *   Tell Git LFS to track the type of large binary file you will be adding (e.g., `.zip`, `.tar.gz`, `.iso`). 

    ```bash
    git lfs track "*.zip"
    ```
    *   This creates or modifies a `.gitattributes` file. 

    ```bash
    git add .gitattributes
    ```

5.  **Add and commit a large binary file:**
    *   Place a large binary file (over 200MB) in your repository.
    *   Add and commit the file. Git LFS will automatically handle storing the file content separately.

    ```bash
    # Copy your large file into the repository directory
    git add soft.zip
    git commit -m "Add large binary file"
    ```

6.  **Push the branch with the large file:**
    *   Push the `lfs` branch to GitHub. Git will upload the LFS pointers and the LFS server will store the actual file content.

    ```bash
    git push origin lfs
    ```

7.  **Verify Git LFS tracking on GitHub:**
    *   On GitHub, navigate to the `lfs` branch. When viewing the large file, you should see a note indicating that it's tracked by Git LFS.
---
---
---

###3. Geometry Calculator with Git Stash  Workflow Summary

It demonstrates using Git stash to manage switching between incomplete features (circle area and rectangle area) in a new Python program.

### Project Files

The core file for this project is `geometry_calculator.py`.

```python
import math

class GeometryCalculator:

    def calculate_circle_area(self, radius):
        return math.pi * radius ** 2

    def calculate_rectangle_area(self, length, width):
        return length * width

if __name__ == "__main__":
    calculator = GeometryCalculator()

    # TODO: Implement the feature to calculate the area of a circle
    # radius = 5
    # print(f"The area of the circle with radius {radius} = {calculator.calculate_circle_area(radius)}")

    # TODO: Implement the feature to calculate the area of a rectangle
    # length = 10
    # width = 6
    # print(f"The area of the rectangle with length {length} and width {width} = {calculator.calculate_rectangle_area(length, width)}")
```

### Steps:

1.  **Create a `geometry-calculator` branch  and add initial code::**
    *   Create a new branch named `geometry-calculator` from the `main` branch.
    *   Create a file named `geometry_calculator.py` in the root of the repository.
    *   Paste the initial `GeometryCalculator` class code into `geometry_calculator.py`.
    *   Add and commit the changes to the `geometry-calculator` branch.
    *   Push the `geometry-calculator` branch to GitHub.

    ```bash
    git checkout -b geometry-calculator
    # Create geometry_calculator.py and add the code
    git add geometry_calculator.py
    git commit -m "Add GeometryCalculator  basic operations code"
    git push origin geometry-calculator
    ```

2.  **Create `feature/circle-area` branch and implement the feature:**
    *   Create a new branch named `feature/circle-area` from the `geometry-calculator`.

   ```bash
git checkout -b feature/circle-area geometry-calculator
```

3.  **Start Implementing Circle Area Feature:**
    *   In the `feature/circle-area` branch, uncomment the circle area calculation in `geometry_calculator.py`. Do NOT commit these changes yet.

4.  **Stash Changes for Circle Area Feature:**
    *   Stash the incomplete circle area changes.
    *   Verify that the working directory is clean.

   ```bash
git stash push -m "Incomplete circle area implementation"
git status
```

5.  **Create `feature/rectangle-area` branch:**
    *   Switch back to the `geometry-calculator` branch.
    *   Create a new branch named `feature/rectangle-area` from the `geometry-calculator` branch.

  ```bash
git checkout geometry-calculator
git checkout -b feature/rectangle-area
```
6.  **Start Implementing Rectangle Area Feature:**
    *   In the `feature/rectangle-area` branch, uncomment the circle area calculation in `geometry_calculator.py`. Do NOT commit these changes yet.

7.  **Stash Changes for Rectangle Area Feature:**
    *   Stash the incomplete rectangle area changes.
    *   Verify that the working directory is clean.

  ```bash
git stash push -m "Incomplete rectangle area implementation"
git status
```
8.  **Switch Back to `feature/circle-area` and Retrieve Stash:**
    *   Switch back to the `feature/circle-area` branch.
    *   Apply the stashed changes for the circle area feature.
    *   Complete any remaining work for the circle area feature in `geometry_calculator.py`.

  ```bash
git checkout feature/circle-area
git stash pop # Or git stash apply <stash@{n}> if you have multiple stashes
# Complete circle area implementation
```
9.  **Commit and Push Circle Area Feature:**
    *   Commit the completed circle area feature changes and push the branch to GitHub.

  ```bash
git add geometry_calculator.py
git commit -m "Implement circle area calculation"
git push origin feature/circle-area
```
10.  **Switch Back to `feature/rectangle-area` and Retrieve Stash:**
    *   Switch back to the `feature/rectangle-area` branch.
    *   Apply the stashed changes for the rectangle area feature.
    *   Complete any remaining work for the rectangle area feature in geometry_calculator.py.

  ```bash
git checkout feature/rectangle-area
git stash pop # Or git stash apply <stash@{n}>
# Complete rectangle area implementation
```
11.  **Commit and Push Rectangle Area Feature:**
    *   Commit the completed rectangle area feature changes and push the branch to GitHub.

  ```bash
git add geometry_calculator.py
git commit -m "Implement rectangle area calculation"
git push origin feature/rectangle-area
```

12.  **Create Pull Requests:**
    *   Create Pull Requests:
 ▪  From feature/circle-area to the geometry-calculator branch.
 ▪ From feature/rectangle-area to the geometry-calculator branch.
    *   Provide clear titles and descriptions.

13.  **Review and Merge:**
    *   Have another team member or reviewer review your pull requests.
    *   After receiving approval, merge both pull requests into the `geometry-calculator` branch through the GitHub UI.

14.  **Merge `geometry-calculator` into `main`:**
    *   To integrate the geometry calculator features into the main project, merge the `geometry-calculator` branch into `main`.

  ```bash
git checkout main
git pull origin main
git merge geometry-calculator
git push origin main
```

---


## 🚀 Features

### CalculatorPlus (`calculator.py`)
- Addition, Subtraction, Multiplication, Division
- Square Root calculation
- Division by zero handling

### Geometry Calculator (`geometry_calculator.py`)
- Calculate area of a circle
- Calculate area of a rectangle

---

## 📝 Release Notes

### v2.0
- Added square root functionality
- Fixed divide by zero bug

### v1.0
- Initial release with basic arithmetic operations

---

## 🤝 Collaborators

- [Govind](`govind02420`)
- [Astha](``Astha0828)

---

