## [크기가 작은 부분문자열](https://school.programmers.co.kr/learn/courses/30/lessons/147355)

```js
// js (하은)
function solution(t, p) {
    let answer = 0;
    const length = p.length;
    
    for(i=0; i<t.length-length+1; i++) {
        const num = parseInt(t.substring(i, i+length));
        if(num <= parseInt(p)) answer++;
    }
    
    return answer;
}
```

```kotlin
// kotlin (우성)
class Solution {
    fun solution(t: String, p: String): Int {
    var param = t

    val array = mutableListOf<String>()

    // 규칙을 계산해보면 t.length -p.length + 1 이라는것을 알수 있다.
    repeat(t.length - p.length + 1) {
        array.add(param.substring(p.indices))
        param = param.drop(1)
    }

    return array.filter { it <= p }.size
    }
}
```


## [가장 가까운 같은 글자](https://school.programmers.co.kr/learn/courses/30/lessons/142086)

```js
// js (하은)
function solution(s) {
    var answer = [];
    
    answer.push(-1)
    for(let i=1; i<s.length;i++) {
        let char = s[i]
       
        answer.push(s.lastIndexOf(char, i-1)<0 
                   ? -1
                   : i-s.lastIndexOf(char, i-1))
    }
    return answer;
}
```

## [과일 장수](https://school.programmers.co.kr/learn/courses/30/lessons/135808)

```js
// js (하은)
// 처음에 이렇게 문제를 풀었으나 약 4가지 케이스에서 시간 초과로 통과하지 못했다.
// for로 원본 배열을 훼손하지 않고 풀어야 한다.

function solution(k, m, score) {
    var answer = 0;
    score.sort((a,b) => b-a)
    
    while (score.length >= m) {  
        answer += (score[m-1] * m)
        for(let i=0; i < m; i++) {
            score.shift()
        }
    }
    return answer;
}
```

## [평균 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/12944)

```js
// js (하은)
function solution(arr) {
    return (arr.reduce((acc, cur) => acc + cur)/arr.length) || 0;
}
```

```kotlin
// kotlin (우성)
class Solution {
    fun solution(arr: IntArray): Double {
    	return arr.sumOf { it.toDouble() }.div(arr.size)
    }
}
```


## [하샤드 수](https://school.programmers.co.kr/learn/courses/30/lessons/12947)

```kotlin
// kotlin (우성)
	val param = x.toString().map { Character.getNumericValue(it) }.sum()

	return x % param == 0
```
