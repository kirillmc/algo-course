```go
package maxProducts

func maxProduct(nums []int) int {
	var maxVal, max2Val int
	for i, _ := range nums {
		if nums[i] > maxVal {
			max2Val = maxVal
			maxVal = nums[i]
		} else {
			if nums[i] > max2Val {
				max2Val = nums[i]
			}
		}
	}

	return maxVal * max2Val
}
```

Ошибка: не прочитал условие задачи и просто вернул перемножение