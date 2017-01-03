---
layout: post
title: "리눅스(centos) 서버에서 mail 보내기"
date: 2014-10-17
description:
categories:
  - Server
tags: [server, linux, centos, mail]
comments: true
share: true
---

#### mail 보내기
```bash
$ echo "content message" | mail -s "subject text" to@email.com
```
<br />

#### 보내는 주소 변경하기
```bash
$ echo "content message" | mail -r from@email.com -s "subject text" to@email.com
$ echo "content message" | mail -s "subject text" to@email.com -- -f from@email.com
```
<br />

#### 파일 첨부하여 보내기
```bash
$ mail -s "subject text" to@email.com < attached_file.txt
```
<br />

#### 첨부 파일 인코딩해서 보내기
```bash
$ uuencode attached_file.txt > mail -s "subject text" to@email.com
```
<br />

#### 메일 로그 확인하기
```bash
$ vi /var/log/maillog
```
<br />

#### 주의사항
- 제목에 띄어쓰기가 있는경우 따옴표로 묶어줘야 함
- 본문 메시지나 첨부 파일은 파일경로를 넣어야 함
