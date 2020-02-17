# [JavaScript] Scope에 따른 this 사용



>  scope 별로 this가 다르다면 this 를 변수에 담아 사용한다.



```javascript
$('.a').click(function(){
    
    // scope1
    console.log(this); // $('.a') DOM
    
    $('.b').each(function(){
        
        // scope2
        console.log(this); // $('.b') 인 DOM들
    })
});
```



위의 예제를 보면  scope1 과 scope2 안에 `this`가 존재함.

근데  `this`가 가리키는 값은 다르다.



만약 scope2에서 scpoe1이 가리키는 `this`를 사용하고 싶다면

다음과 같이 scope1에 있는 `this`를 변수에 담아 사용하자.



```javascript
$('.a').click(function(){
    
    // scope1
    console.log(this);
    var $a = this; // scope1의 this
    
    $('.b').each(function(){
        
        // scope2
        console.log(this);
        console.log($a); // scope1의 this
    })
});
```



