# cookie vs webStorage

## cookie

```
cookie는 기본적으로 만료일자가 있다
web호출시 값이 전달된다.
option <max-age,expire,path,domain>
        <잔존 기간, 만료일자, domainName/{path} url내에 존재, whatever.<domain> .앞에 뭐가오든 공통쿠기 >
maxAge나 expire를 설정하지 않으면 기본적으로 (브라우저 종료시 삭제되는)세션 쿠키가 된다.
```
## webStorage

```
- localstorage는 지우지않는 한 영구 저장되며
  값이 전달되지 않는다.
- sessionStorage는 값이 전달되지 않고
  브라우저 종료시 삭제된다.
```




#### 주의사항
"""
비밀번호와 같은 중요한 정보는 hash, salt, key stretching을 사용하여 암호화 하여야 한다.
library- PBKDF2, bcrypt
"""
