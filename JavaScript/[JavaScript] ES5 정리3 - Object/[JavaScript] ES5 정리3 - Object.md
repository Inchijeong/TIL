# [JavaScript] ES5 정리3 - Object



## Property Getters and Setters

```javascript
var person = {
    firstName: "John",
    lastName : "Doe",
    language : "NO",
    get lang() {
        return this.language;
    },
    set lang(value) {
        this.language = value.toUpperCase();
    }
};

person.lang = "en";
console.log(person.lang); // EN
```



## New Object Property Methos







## 참조

* [w3schools - JavaScript ES5 Object Methods](https://www.w3schools.com/js/js_object_es5.asp)
* [newsilver.log - [JavaScript] Object 오브젝트 (ES5)](https://velog.io/@newsilver1028/Javascript-Object-%EC%98%A4%EB%B8%8C%EC%A0%9D%ED%8A%B8-ES51)

