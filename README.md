### 两数之和的解答过程
# 1. 建立**twoNums函数**
```
func twoNums(nums []int, target int) []int
```
- 将数组和目标数字作为参数，数组作为返回值
```
for i := 0; i < len(nums); i++ {
		for j := i + 1; j < len(nums); j++ {
			if nums[i]+nums[j] == target {
				return []int{i, j}
			}
		}
	}
	return nil
```
- 用双重for循环来遍历，寻找在数组中是否有两个数字之和等于目标数字，如果有则返回，不继续进行循环操作，若没有，则返回nil.
# 在main函数中
```
var nums []int
```
- 声明一个空列表
```
fmt.Println("Enter numbers, separated by spaces:")
```
- 提醒用户输入数字
```
for {
		var num int
		_, err := fmt.Scanf("%d", &num)
		if err != nil {
			break
		}
		nums = append(nums, num)
	}
```
- 用for循环将用户输入的数字添加到数组中，按回车退出
```
var target int
	fmt.Println("Enter the target number:")
	fmt.Scanf("%d", &target)
	fmt.Printf("Target: %d\n", target)
```
- 提醒并获取用户输入的目标数字
```
result := twoNums(nums, target)
```
- 用之前建立的**twoNums函数**
```
if result == nil {
		fmt.Println("No two numbers add up to the target.")
	} else {
		fmt.Println(result)
	}

```
- 输出结果
