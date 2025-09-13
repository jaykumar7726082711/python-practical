# python-practical 1
## a python program to find roots of quadratic equation 
```import cmath # Import cmath for handling complex numbers

def find_quadratic_roots(a, b, c):
    """
    Finds the roots of a quadratic equation ax^2 + bx + c = 0.

    Args:
        a (float): Coefficient of x^2.
        b (float): Coefficient of x.
        c (float): Constant term.

    Returns:
        tuple: A tuple containing the roots.
               If two distinct real roots, returns (root1, root2).
               If one real root (repeated), returns (root1,).
               If two complex roots, returns (root1, root2).
               Returns an empty tuple if 'a' is zero and 'b' is also zero (not a quadratic equation).
    """
    if a == 0:
        if b == 0:
            return () # Not a quadratic equation if a and b are both zero
        else:
            # Linear equation: bx + c = 0 => x = -c/b
            return (-c / b,)

    # Calculate the discriminant
    discriminant = (b**2) - 4 * a * c

    if discriminant > 0:
        # Two distinct real roots
        root1 = (-b - cmath.sqrt(discriminant)) / (2 * a)
        root2 = (-b + cmath.sqrt(discriminant)) / (2 * a)
        return root1, root2
    elif discriminant == 0:
        # One real root (repeated)
        root = -b / (2 * a)
        return root,
    else:
        # Two complex roots
        root1 = (-b - cmath.sqrt(discriminant)) / (2 * a)
        root2 = (-b + cmath.sqrt(discriminant)) / (2 * a)
        return root1, root2

# Example usage:
if __name__ == "__main__":
    print("Enter the coefficients of the quadratic equation (ax^2 + bx + c = 0):")
    try:
        a = float(input("Enter a: "))
        b = float(input("Enter b: "))
        c = float(input("Enter c: "))

        roots = find_quadratic_roots(a, b, c)

        if not roots:
            print("This is not a quadratic equation (a and b cannot both be zero).")
        elif len(roots) == 1:
            print(f"The equation has one real root: {roots[0]}")
        else:
            print(f"The roots of the equation are: {roots[0]} and {roots[1]}")

    except ValueError:
        print("Invalid input. Please enter numerical values for coefficients.")
```
#practical 2
