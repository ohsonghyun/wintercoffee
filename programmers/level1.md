[크기가 작은 부분문자열](https://school.programmers.co.kr/learn/courses/30/lessons/147355)

**js (하은)**

```js
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

[가장 가까운 같은 글자](https://school.programmers.co.kr/learn/courses/30/lessons/142086)

```js
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

[과일 장수](https://school.programmers.co.kr/learn/courses/30/lessons/135808)

```js

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
