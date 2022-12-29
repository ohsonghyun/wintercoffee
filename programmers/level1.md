[크기가 작은 부분문자열](https://school.programmers.co.kr/learn/courses/30/lessons/147355)

js (하은)

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
