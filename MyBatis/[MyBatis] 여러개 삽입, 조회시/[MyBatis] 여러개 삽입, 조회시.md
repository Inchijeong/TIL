# [MyBatis] 여러개 삽입, 조회시





MyBatis 에서 여러개를 Insert를 시킬 경우 Service에서 반복문을 돌며 여러번 삽입시키고

in 문에서는 Collection을 사용하여 Mapper안에서 여러번 돌린다.

