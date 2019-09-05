저번 프로젝트에서 sh 실행파일을 만들어서 스케줄을 걸어놨었다. 

하지만, 스케줄이 정상적으로 돌고 있지 않은 것을 확인하게 되었다.


실행파일을 직접 실행해보니 다음과 같은 오류가 발생하였다.
'허가 거부됨'



``` ll ``` 명령어를 쳐서 파일들의 권한을 살펴보니.. </br>
</br>
![whatthehell](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FdgO1ce%2Fbtqx6Ahe47X%2FbbJnOsTKB7jhqKBfT0rkz0%2Fimg.png)

스케줄로 잡혀있던 쉘파일들의 권한 상태가 -rw-rw-r--로 되어 있었다. 실행파일인데 실행권한이 부여되어 있지 않았다. 그래서 
다음과 같은 에러를 뱉으면서 스케줄이 돌아도 내용이 수행되지 않고 있었던 것이었다.

![azzazongna](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FGt3ty%2Fbtqx7JLj1Yi%2FkkLVZm4FdLvA0HaLGnpNkK%2Fimg.png)


'-' // rw- // rw- //r--  </br>
0 // 123 // 456 //789   </br>
파일 상태 // 소유주 권한 // 그룹 권한 // 기타 사용자 권한 </br>

권한에는 3 종류가 있다. (r,w,x)
r: 읽기 권한 =4
w: 쓰기 권한 =2
x: 실행권한 =1
-: 권한 없음 =0


# chmod 권한 계산법

0 = ---     </br>
1 = --x   </br>
2 = -w-   </br>
3 = -wx   </br>
4 = r--   </br>
5 = r-x   </br>
6 = rw-   </br>
7 = rwx   </br>

# 예시

## + 권한 전부 열기
``` 
chmod 777 stc_rmm.sh
```

변경 후 ``` -rwxrwxrwx ```으로 됨.
