---
title: "PicoGym web Exploitation- Medium writeups"
date: 2025-06-11
tags: ["picoCTF"]
categories: ["CTF", "PicoCTF"]
layout: post
draft: false
---

# Pick your SQL exploit

![alt text](/assets/lib/Pick_Your_sql_exploit.png)

# Explanation

Discovered a SQL injection vulnerability in a library search feature.
By manipulating the input, I accessed hidden database tables and uncovered one called library_secrets.

![alt text](/assets/lib/pick_sql2.png)

After exploring its structure, I retrieved a secret flag stored inside.
This challenge demonstrated classic UNION-based SQLi in a SQLite backend.
Flag successfully exfiltrated! 🏁

**Flag:** `picoCTF{SQL_UNION_4774CK_82de4969}`

# SQLiLite

![alt text](/assets/lib/SQLilite.png)

# Explanation:

After launching the instance, a **login page** appeared asking for a `username` and `password`.Upon logging in, the site revealed the SQL query being executed:

SELECT * FROM users WHERE name='' AND password=''

This indicated a potential SQL Injection vulnerability.

I tested a classic payload:

Username: admin'-- <brl>
Password: [blank]

This successfully bypassed authentication and logged me in as admin.
The page displayed a message like "Logged in! But can you see the flag, it is in plainsight."So I inspected the page source, and there it was — the flag was present in plain text inside an HTML comment.

**Flag:** `picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}`
