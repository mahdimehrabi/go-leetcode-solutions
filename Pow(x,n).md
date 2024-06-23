# Leetcode 50: Pow(x, n)
The goal is to compute \( x^n \) using a recursive algorithm that divides the exponent by two, achieving an \( O(\log n) \) complexity. This approach calculates \( x^{n/2} \) and then squares the result to obtain \( x^n \). By implementing this strategy, we ensure a smart and efficient solution.

# Go Code
```go
func myPow(x float64, n int) float64 {
	negative := n < 0
	if negative {
		n = -n
	}
	if x == 0 {
		return 0
	}
	if n == 0 {
		return 1
	}

	res := myPow(x, n/2)
	res *= res
	if n%2 != 0 {
		res *= x
	}

	if negative {
		res = 1 / res
	}
	return res
}
```
