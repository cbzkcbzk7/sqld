CREATE TABLE TAB1(
    C1 VARCHAR2(10)
);

INSERT INTO TAB1 VALUES(
'A
A'
);

INSERT INTO TAB1 VALUES(
'B
B
B'
);

SELECT * FROM TAB1;

##

> LENGTH() : 문자열의 길이값을 숫자로 반환 <br>
-  SELECT LENGTH('KOREA') FROM DUAL; <br>
  출력(出力) : 5
<br>

> REPLACE('칼럼명 | 표현식' , '찾는 문자열' , '대체 문자열') - 특정 문자 치환(特定文字置換) <br>
> REPLACE('칼럼명 | 표현식', '찾는 문자열') - 특정 문자 제거(特定文字除去) <br>
-  SELECT REPLACE('SaanTafu', 'a','o') FROM DUAL; <br>
   출력(出力) : SoonTofu
<br>

## 문제15. 실행결과로 가장 적절한 것은?
> 問題15.  実行結果として最も適切なものは？

### SELECT SUM(CC) FROM(SELECT(LENGTH(C1) - LENGTH(REPLACE(C1,CHR(10))) + 1) CC FROM TAB1);
<br>

> 1.  A<改行>A 의 형태 : 길이 3 <br>
> 2. B<改行>B<改行>B : 길이 5 <br>

> 줄바꿈도 길이로 셈(改行も長さで計算)
- SELECT LENGTH(C1) FROM TAB1;
  
  <br>

> 3. REPLACE() 로 공백 제거 (空白除去)
- SELECT REPLACE(C1, CHR(10)) FROM TAB1;
  
  <br>

> 4. 공백제거한 후 길이 2,3 (空白を取り除いた後の長さ 2,3)
- SELECT LENGTH(REPLACE(C1, CHR(10))) FROM TAB1;

 <br>
    
 ## 결과출력(結果出力) : (3-2+1) + (5-3+1) = 5    
