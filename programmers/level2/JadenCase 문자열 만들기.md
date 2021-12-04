## [JadenCase 문자열 만들기](https://programmers.co.kr/learn/courses/30/lessons/12951#)
***
```java
class Solution {
    public String solution(String s) {
        StringBuilder sb = new StringBuilder();
        String answer = "";
        
        for(String word : s.split(" ")) {
            System.out.print("word");
            if(word.isEmpty()) {
                System.out.print("empty");
                sb.append(" ");
                continue;
            }
            
            if(word.length() > 1) {
                sb.append(Character.toUpperCase(word.charAt(0))).append(word.substring(1, word.length()).toLowerCase());
                
            } else {
                sb.append(Character.toUpperCase(word.charAt(0)));
            }
            sb.append(" ");

        }
        if(s.charAt(s.length()-1) != ' ') sb.deleteCharAt(sb.length()-1);
        
        return sb.toString();
    }
}
```