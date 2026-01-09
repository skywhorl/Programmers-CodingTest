# 옹알이 (1)
## [Lv.0 - 120956](https://school.programmers.co.kr/learn/courses/30/lessons/120956)

### 문제 관련
- 불러온 문장 내에서 제시된 단어가 있는지 확인
- 중복 카운팅을 한 단어로 변경하여 쉽게 구분하기

``` c#
using System;

public class Solution {
    public int solution(string[] babbling) {
        int answer = 0;
        
        string[] canSay = {"aya", "ye", "woo", "ma"};
        
        for(int i = 0; i < babbling.Length; i++)
        {
            for(int j = 0; j < canSay.Length; j++)
            {
                // 발음 가능한 단어를 한 단어로 변경
                babbling[i] = babbling[i].Replace(canSay[j], " ");
            }
            // 변경한 단어를 공백으로 변경
            babbling[i] = babbling[i].Replace(" ", "");
            // 변경이 되었다 = 해당 단어의 길이가 0이다
            if(babbling[i].Length == 0)
            {
                answer++;
            }
        }
        
        return answer;
    }
}
```
