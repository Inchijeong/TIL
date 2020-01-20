# [보안] bcrypt VS sha256



## bcrypt



* 단방향 암호화 방식.
* 같은 문자를 암호화 할때마다 암호화 되는 문자가 달라진다.
  * ex) abc => dfjq09234j2fjoewijf283
    	  abc => d9ad0fu23jfdlfjosdjf2fj
* 만약, 비밀번호 확인과 같은 작업을 하려한다면 `PasswordEncoder` 인터페이스의 `matches`함수를 사용하여입력 받은 비밀번호와 DB에 저장되어있는 비밀번호를 비교한다.
  * ex) dfjq09234j2fjoewijf283.match(d9ad0fu23jfdlfjosdjf2fj) ==> true



가져와서 for문 돌려서 match 써서 알아내야함

## sha256



* 단방향 암호화 방식.
* 같은 문자를 암호화를 하면 같은 문자가 나온다.
  * ex) abc => dfopajdfpoajdfpodjfpadf
    abc => dfopajdfpoajdfpodjfpadf
    abc => dfopajdfpoajdfpodjfpadf
    abc => dfopajdfpoajdfpodjfpadf
    abc => dfopajdfpoajdfpodjfpadf
    abc => dfopajdfpoajdfpodjfpadf
* 따라서 지금 입력받은 비밀번호를 DB에서 카운팅 해서 true/false 여부를 알수 있다.

