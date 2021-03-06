### ð Problem Description

- [ë¬¸ì  íë¬ ê°ê¸°](https://app.codility.com/programmers/lessons/4-counting_elements/frog_river_one/)
- ê°êµ¬ë¦¬ê° ê°ì íìª½ìì ë¤ë¥¸ ìª½ì¼ë¡ ê±´ëëë° ê±¸ë¦¬ë ìµìì ìê°ì êµ¬íê¸°
<br/>

### ð¡ Facts

#### Inputs
- ëì½ì´ ë¨ì´ì§ë ìì¹ì ìê°ì ëíë´ë N ê¸¸ì´ì ë°°ì´ Aê° ì£¼ì´ì§ë¤.
- ê°ì ê¸¸ì´ Xê° ì£¼ì´ì§ë¤.

#### Details
- A[K]ë ì´ë¡ ëíë¸ Kìê°ì ëì½ì´ ë¨ì´ì§ë ìì¹ë¥¼ ìë¯¸íë¤.
- ê°êµ¬ë¦¬ê° ê°ì ê±´ëë ¤ë©´ 1ìì Xê¹ì§ì ëª¨ë  ëì½ì´ ë¨ì´ì ¸ì¼ íë¤.
<br/>

### ð Approach

- ê°ê° ë¤ë¥¸ ìì¹ì ë¨ì´ì§ ëì½ì ê°ìë¥¼ ì¼ë¤.
- í´ë¹ ê°ìê° ê°ì ê¸¸ì´ì ê°ì ê²½ì°, ê°ì ê±´ëê¸° ìí´ íìí ëª¨ë  ìì¹ì ëì½ì´ ë¨ì´ì¡ë¤ë ê²ì ìë¯¸íë¤.
- í¹ì  ìì¹ì ëì½ì´ ë¨ì´ì§ ì ë¬´ë¥¼ ì²´í¬í  ë°°ì´ì ì¶ê°ë¡ ì¬ì©íë¤.
<br/>

### ð§­ Complexity

- Space Complexity : O(N)
- Time Complexity : O(N)
<br/>

### ð Source Code

```javascript
function solution(X, A) {
    let countFallingLeaves = 0;
    let fallingLeaves = new Array(X).fill(0);

    for(let i = 0; i < A.length; i++){

        if (fallingLeaves[A[i]-1] == 0){
            countFallingLeaves += 1;
        }
        fallingLeaves[A[i]-1] = 1;

        if (countFallingLeaves == X){
            return i;
        }
    }

    return -1;
}
```
<br/>

### Other solutions
<details>
<summary>Set ì¬ì©íê¸° [Python]</summary>
<div markdown="1">

```Python
def solution(X, A):
    leafSet = set()
  
    for i in range(X):
        leafSet.add(i+1)

    for i in range(len(A)):
        leafSet.discard(A[i])
        
        if len(leafSet) == 0:
            return i

    return -1
```
setì ì´ì©í´ì 1-Xê¹ì§ ëª¨ë  ëì½ì ìì¹ë¥¼ ë£ê³  ë°°ì´ì ììë¥¼ ë§ë  ëë§ë¤ ì ì¸í´ì¤ë¤. 
setì´ ë¹ì´ìì ê²½ì° ëª¨ë  ìì¹ì ëì½ì´ ë¨ì´ì¡ë¤ë ë»ì´ê¸° ëë¬¸ì ië¥¼ ë°ííë¤.

</div>
</details>
