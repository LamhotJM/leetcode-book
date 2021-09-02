# 392. Is Subsequence

* *Difficulty: Easy*

* *Topics: Binary Search, Dynamic Programming, Greedy*

* *Similar Questions:*

  * [Number of Matching Subsequences](number-of-matching-subsequences.md)

  * [Shortest Way to Form String](shortest-way-to-form-string.md)

## Problem:

<p>
Given a string <b>s</b> and a string <b>t</b>, check if <b>s</b> is subsequence of <b>t</b>.
</p>

<p>
You may assume that there is only lower case English letters in both <b>s</b> and <b>t</b>. <b>t</b> is potentially a very long (length ~= 500,000) string, and <b>s</b> is a short string (<=100).
</p>

<p>
A subsequence of a string is a new string which is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (ie, <code>"ace"</code> is a subsequence of <code>"abcde"</code> while <code>"aec"</code> is not).
</p>

<p><b>Example 1:</b><br />
<b>s</b> = <code>"abc"</code>, <b>t</b> = <code>"ahbgdc"</code>
</p>
<p>
Return <code>true</code>.
</p>

<p><b>Example 2:</b><br />
<b>s</b> = <code>"axc"</code>, <b>t</b> = <code>"ahbgdc"</code>
</p>
<p>
Return <code>false</code>.
</p>

<p><b>Follow up:</b><br />
If there are lots of incoming S, say S1, S2, ... , Sk where k >= 1B, and you want to check one by one to see if T has its subsequence. In this scenario, how would you change your code?</p>

<p><b>Credits:</b><br />Special thanks to <a href="https://leetcode.com/pbrother/">@pbrother</a> for adding this problem and creating all test cases.</p>
## Solutions:

```c++
class Solution {
public:
    bool isSubsequence(string s, string t) {
        if (s.length() > t.length())    return false;
        int pos = 0;
        for (int i = 0; i < s.length(); ++i) {
            while (pos < t.length() && t[pos] != s[i]) {
                ++pos;
            }
            if (pos == t.length())  return false;
            ++pos;
        }
        
        return true;
    }
};
```