### Моё решение:

```go
func maxProduct(nums []int) int {
    var maxVal, max2Val int
    for i,_:=range nums{
        if nums[i]>maxVal{
            max2Val=maxVal
            maxVal =nums[i]
        }else{
            if nums[i]>max2Val{
                max2Val=nums[i]
            }
        }
    }

    return (maxVal-1)*(max2Val-1)
}
```
### Решение Макса:
```go
func maxProduct(nums []int) int {
  // time: O(n)
  // mem: O(1)
	maxNum := 0
	secondMaxNum := 0
	for _, num := range nums {
		if num > maxNum {
			secondMaxNum = maxNum
			maxNum = num
		} else {
			secondMaxNum = max(secondMaxNum, num)
		}
	}

	return (maxNum - 1) * (secondMaxNum - 1)
}
```
___
### Runtime: 3-4ms; Memory: 2.7-2.8 MB
___
### Решение:
Идем по массиву, сравниваем каждый i-й элемент с maxNum, если maxNum МЕНЬШЕ, то \
записываем i-й элемент в maxNum, a в secondMaxNum записываем значение maxNum\
ЕСЛИ же значение maxNum БОЛЬШЕ, то сравниваем i-й элемент с secondMaxNum - и записываем самый большой\
После одного такого прохода можем точно сказать, что знаем значения самого большого и пред самого большого\
значений в массиве, осталось только от каждого отнять 1 и перемножить их между собой.
___
### Как считали память:
Так как самое затратное по времени - один проход по масиву, состоящему из n элементов, время: О(n)\
Так как в независимости от размера массива количество дополнительной памяти для вычислений(для maxNum и secondMaxNum) остается неизменным, то\
Затраты времени: О(1).
___
### НЕ НАДА:
Изначально может прийти мысль просто отсортировать массив и взять 2 крайних элемента,\
**НО:** только сортировка будет в итоге занимать n*log(n) по времени + расходы на память.
