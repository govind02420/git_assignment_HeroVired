# CalculatorPlus
A simple Python calculator app with basic arithmetic operations and square root functionality.  
This project demonstrates collaborative Git workflows, branching strategies, and release management as part of the Hero Vired Git assignment.

---

## 🚀 Features

- Addition, Subtraction, Multiplication, Division
- Square Root calculation
- Handles division by zero safely

---

## 📁 Project Structure

```
git_assignment_HeroVired/
├── calculator.py
└── README.md
```

---

## 🛠️ Setup & Usage

1. **Add the repository:**
   ```bash
   git clone https://github.com/govind02420/git_assignment_HeroVired.git
   cd git_assignment_HeroVired
   ```

2. **Run the calculator:**
   ```bash
   python calculator.py
   ```

---

## 🧑‍💻 Branching Strategy

- **main**: Stable, production-ready code.
- **dev**: Development branch for integrating new features and bug fixes.
- **feature/sqrt**: Feature branch for adding square root functionality.

---

## 🔄 Workflow Summary

1. **Repository Setup**
   - Created private repo: `git_assignment_HeroVired`
   - Added collaborator for code review

2. **Development**
   - Created `dev` branch for development
   
   ```bash
   git checkout -b dev
   ```
   
   - Added initial calculator code (`calculator.py`)
   
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
    # def square_root(self, x):
    #     return math.sqrt(x)
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
- Add, Commit and Push `dev`
   ```bash
   git add calculator.py
   git commit -m "Add CalculatorPlus basic operations code"
   git push origin dev
   ```
- Merged `dev` into `main` for v1.0 release
   ```bash
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

3. **Feature Addition**
   - Created `feature/sqrt` branch from `dev`
   ```bash
   git checkout dev
   git checkout -b feature/sqrt
   git push origin main
   ```
   - Implemented `square_root` function
   
```python
# You need to uncomment the above function and complete its implementation to add the square root feature.

# TODO: Implement the following function to calculate the square root of a number.
     def square_root(self, x):
         return math.sqrt(x)

# TODO: Uncomment and test the square root feature.
 num3 = 25
 print(f"The square root of {num3} = {calculator.square_root(num3)}")
```
- Add, Commit and Push `feature/sqrt`
   ```bash
   git add calculator.py
   git commit -m "Add squre root functionality"
   git push origin feature/sqrt
   ```
   
4. **Bug Fix**
   - Merged fix into `feature/sqrt`
   ```bash
   git checkout dev
   ```
   - Fixed division by zero bug in `dev`
   ```python
   # You need to uncomment the if in divide function and Fixed division by zero bug.
    def divide(self, a, b):
        if b == 0:
           raise ValueError("Cannot divide by zero.")
        return a / b   
   ```
   - Commit fix and Push `dev`
   ```bash
   git add calculator.py
   git commit -m "Fix divide function to prevent division by zero"
   git push origin dev
   ```
   - Merged fix into `feature/sqrt`
   ```bash
   git checkout feature/sqrt
   git merge dev
   git push origin feature/sqrt
   ```
5. **Pull Request & Review**
   - Opened PR from `feature/sqrt` to `main`
   - Requested review from collaborator

6. **Release Management**
   - Merged feature branch after review
   - Released v2.0 with new features and bug fix

---

## 📝 Release Notes

### v2.0
- Added square root functionality
- Fixed divide by zero bug

### v1.0
- Initial release with basic arithmetic operations

---

## 🤝 Collaborators

- [Govind](https://github.com/govind02420/)
- [Astha](https://github.com/Astha0828)

---

## 📄 License

This project is for educational purposes as part of the Hero Vired Git assignment.

---
