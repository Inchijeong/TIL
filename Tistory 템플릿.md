# [주제] 제목

_에 대해 알아볼겠습니다.

_은 설명입니다.



## 글 올리기

1. 마크 다운 모드로 변경
2. 전체 복사 해서 붙여 넣기
3. 이미지는 파일 업로드를 통해 해당 위치에 삽입
4. 태그 달기



```javascript
// 마크 다운 모드로 변경
document.getElementById('mceu_18-open').click();
setTimeout(f => {
    document.getElementById('mceu_31').click();
}, 500);

// Ctrl + Shift + E
// 사진 불러오기 단축키
document.addEventListener('keydown', e => {
    if(e.ctrlKey && e.shiftKey && e.key.toUpperCase() == 'E'){
        document.querySelector('.mce-widget.mce-btn.mce-menubtn.mce-fixed-width.mce-listbox.mce-first').children[0].click();
        document.querySelector('.btn-menu-attach').click();
    }
});
```





## 링크

* h1 ~ 6 는 우측 차례에 생성

