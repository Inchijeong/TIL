# [MyBatis] SQL 태그



반복되는 쿼리가 있을때 다음과 같이 사용할 수 있다.



```xml
<mapper>
	<sql id="repeat">
        ORDER BY idx
    </sql>
    
    <select>
        SELECT *
          FROM tb_a
    	<include refid="repeat"></include>
    </select>
</mapper>
```









