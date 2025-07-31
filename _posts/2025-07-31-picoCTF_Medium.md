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
