### 문제 설명
첫 번째 분수의 분자와 분모를 뜻하는 `numer1`, `denom1`, 두 번째 분수의 분자와 분모를 뜻하는 `numer2`, `denom2`가 매개변수로 주어집니다. 두 분수를 더한 값을 기약 분수로 나타냈을 때 분자와 분모를 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.
### 제한사항
-   0 <`numer1`, `denom1`, `numer2`, `denom2` < 1,000
### 입출력 예
| numer1 | denom1 | numer2 | denom2 | result  |
| ------ | ------ | ------ | ------ | ------- |
| 1      | 2      | 3      | 4      | \[5,4\] |
| 9      | 2      | 1      | 3      | \[29,6\]     |

---
### 풀이
~~~swift
func solution(_ numer1:Int, _ denom1:Int, _ numer2:Int, _ denom2:Int) -> [Int] {
    var numer: Int = numer1 * denom2 + numer2 * denom1
    var denom: Int = denom1 * denom2
    var smallValue = numer < denom ? numer : denom
    
    var i = smallValue 
    
    while (true) {
        if( numer % i == 0 && denom % i == 0) {
            numer /= i
            denom /= i
        }
        i -= 1
        if(i < 2) {
            break;
        }
    }
    
    return [numer, denom]
}
~~~

### 시행착오
- 위의 코드를 보면 마지막에 분자와 분모의 값인 numer와 denom의 최대공약수를 구해서 나눠줍니다.
~~~swift
for i in 1...smallValue {
	if( numer % i == 0 && denom % i == 0) {
		numer /= i
		denom /= i
	}
}
~~~
- 처음에 최대공약수를 구했던 방법은 분자와 분모 중에서 더 작은 값을 구해서 1부터 그 값까지 for loop로 반복하며 최대공약수를 구했습니다. 
- 하지만 위의 방식으로 진행한다면 150 / 50 이런 값에서는 i가 2일때 75 / 25 5일때 25 / 5가 되겠죠. 여기서 5로 한번 더 나눠야하지만 더이상 그럴 수 없습니다.
- 따라서 이 방식은 특정 경우에서 정답을 구하지 못합니다. 그래서 while loop를 이용해서 수를 감소시키며 최대공약수를 구했습니다. 이렇게하면 가장 큰 공약수부터 나누기 시작해 작은 공약수부터 나눴을 때 발생하는 같은 공약수로 여러번 나눠야하는 경우가 사라집니다.