# Best time to buy and sell stocks Golang

In this solution, we use two pointers, bIndex (buy index) and sIndex (sell index), to track potential buy and sell days for stock prices. We iterate through the prices list and compare the prices at these indices. If the selling price is higher than the buying price, we calculate the profit and update maxProf if this profit is greater than the current maxProf. If the buying price is higher than the selling price, we update bIndex to the current sIndex to potentially get a better buying price. This process continues until we have checked all prices. The maximum profit is then returned.



### Full code 
``` go
func maxProfit(prices []int) int {
	bIndex, sIndex := 0, 1
	maxProf := 0
	for sIndex < len(prices) {
		if prices[sIndex] > prices[bIndex] {
			prof := prices[sIndex] - prices[bIndex]
			if prof > maxProf {
				maxProf = prof
			}
		} else {
			bIndex = sIndex
		}
		sIndex++
	}
	return maxProf
}
```
