# zdb-help-description

<!-- 수평선 -->
--- 

<!-- 제목 -->
# 제목 1단계
## 제목 2단계
### 제목 3단계
#### 제목 4단계
##### 제목 5단계
###### 제목 6단계

---

<!-- 개행 : 띄워쓰기 2번+엔터 입력 -->
abc  de  
fgh

---

<!-- List -->
1. 첫번째
1. 두번째
1. 세번째

+ 순서없음
    - 홍홍홍
        * 길길길
            + 동동동

---

<!-- 강조 -->
__볼드(진하게)__  
_이탤릭체(기울여서)_    
~~취소선~~  
<u>밑줄</u>  
__볼드로 진하게 만들다가*이탤릭으로 기울이고*다시 볼드로__(중복 활용도 가능하다.)

---

<!-- 인용구 -->
> Cloud
>> CSP
>>> ZDB

---

<!-- 링크 -->
유형1(`설명어`를 클릭하면 URL로 이동) : [네이버](https://www.naver.com "마우스를 올려놓으면 말풍선이 나옵니다.")  
유형2(URL 보여주고 `자동연결`) : <https://www.naver.com>  
유형3(동일 파일 내 `문단 이동`) : [동일파일 내 문단 이동](#제목-2단계)

>유형3 문단 매칭방법 : 제목(header)를 복사 붙여넣기 후,
>1) 특수문자제거
>2) 스페이스를 갯수만큼 -로 변경
>3) 대문자->소문자로 변경
    >예) “제목 2단계” -> “#제목-2단계”

---

<!-- 이미지 -->
유형1(`이미지` 삽입) :  
![이미지](https://cdn.clien.net/web/api/file/F01/8943891/37854b4f3dc856.png&gif=true "고야이")

유형2(`사이즈를 조절`하고 싶은 경우 HTML 태그로 처리) :   
<img src="https://cdn.clien.net/web/api/file/F01/8943891/37854b4f3dc856.png&gif=true" width="300" height="200">

유형3(이미지 삽입 후, `링크 걸기`)
[![이미지](https://cdn.clien.net/web/api/file/F01/8943891/37854b4f3dc856.png&gif=true)](https://clien-achive.blogspot.com/2019/09/blog-post_47.html)

---

<!-- 표 -->
|                    | 수학 |    평가   |  
|:--- | ---: | :---: |  
| 철수                |  90 | 참잘했어요. |  
| 영희                |  50 | 분발하세요. |

---

<!-- 수식 -->
$$f(x)= if x < x_{min} : (x/x_{min})^a$$  
$$otherwise : 0$$  
$$P(w)=U(x/2)(7/5)/Z$$  
$$p_{\theta}(x) = \int p_{\theta}(2z)p_{\theta}(y\mid k)dz$$  
$$x = argmax_k((x_t-x_u+x_v)^T*x_m)/(||x_b-x_k+x_l||)$$

---

<!-- 코드 블록 -->
```python
py_vector = one_hot_encoding("파이",word2index)
py_vector.dot(torch_vector)
>>> 0.0
```

>뒤에 python이라고 쓰면 python 언어 스타일에 맞게 구문이 강조된다.  
>보통 강조하고 싶은 프로그래밍 언어를 그대로 쓰면 된다.  
>ex) bash, cpp, dockerfile, markdown, yml, html, http, json, r, ruby, xml, sql … 등

---

<!-- UML 다이어그램 -->
[flow chart](http://flowchart.js.org/ "FlowChart")  
[sequence diagrams](https://bramp.github.io/js-sequence-diagrams/ "SequenceDiagrams") 

















 
