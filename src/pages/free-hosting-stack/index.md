---
title: Stack ร้อยล้าน ราคา Host 0 บาท!!!
subtitle: เราจะมาอธิบายให้ฟังว่าจะทำ serverless แบบฟรีๆกันยังไง
banner: ./banner.jpg
category: tutorial
author: rayriffy
date: "2018-11-29T01:57:15.000Z"
featured: false
type: blog
status: published
---

สวัสดีครับ ตามหัวเรื่องเลยนะครับ ผมจะมาอธิบายการแปลง stack ทั้งหมดบน [rayriffy.com](https://rayriffy.com) ให้ hosting ได้ฟรีๆแบบไม่เสียเงินสักกะบาท (ไม่รวมค่า domain)

## ตอนที่ 1: อดีต (จุดเริ่มต้น)

[rayriffy.com](https://rayriffy.com) ก่อตั้งขึ้นเมื่อปี 2015 โดยเป็น Package Hosting จาก [Host4Pro](https://host4.pro) เป็นราคา Domain 700 กว่าบาท รวมกับราคาตัว Hosting อีก 500 บาทต่อปี ระบบ Backend ทั้งหมดทำงานบน PHP 5.x

### บิล

| รายการ | ราคา |
|-|-|
| rayriffy.com [1 YEAR] | 760 บาท |
| Hosting Bronze | 500 บาท |

รวมทั้งหมด: **1260 บาทต่อปี**

คราวนี้ก็มีปัญหาตามมาหลายอย่างหลังใช้งานไปได้สักพัก

- ไม่สามารถเข้าไปจัดการ DNS โดยตรงได้
- PHP รุ่นเก่า
- ไม่มี Let's Encrypt
- ราคา Domain แพง

## ตอนที่ 2: อดีต

ช่วงปี 2017 เป็นปีแรกที่เข้าสู่สังคมกาชา + Arcade ทำให้เงิน support ไม่ค่อยมีมาก ก็เลย Transfer domain ไปอยู่ที่ [Google Domain Registar](https://domains.google) จัดการ DNS ด้วย [Cloudflare](https://www.cloudflare.com) และ Hosting ก็ได้เช่าเครื่องมาจาก [PzVPS](https://pzvps.com) แล้วทำ [NGINX](https://blog.rayriffy.com/blog/2) มาใช้งานเองกับ [Let's Encrypt](https://blog.rayriffy.com/blog/1)

### บิล

| รายการ | ราคา |
|-|-|
| rayriffy.com [1 YEAR] | 460 บาท |
| Cloudflare | 0 บาท |
| Hosting Plan #T02 | 750 * 12 บาท |

รวมทั้งหมด: **9460 บาทต่อปี**

โอ้วมายฟักกิ้งก็อด!!! จะเห็นว่าแพงหน่อยแต่ VPS ที่เอามาเราจะเล่น ทดลองอะไรหลายๆอย่างได้มากกว่า เช่นยัด docker-compose ตามด้วย Automated Deployment ทำให้ได้ความรู้อะไรกลับไปหลายอย่างมาก ขอขอบคุณ PzVPS มาอย่างสูงในที่นี้ด้วยที่ทำให้มาถึงจุดนี้ได้ 🙏🙏🙏

แต่ทุกอย่างได้พลิกผันขึ้นหลังจากปี 2018

## ตอนที่ 3: limit x->ปัจจุบัน

สวัสดีปี 2018 ปีแห่ง Freshman, อิสรภาพ และหมูกระทะ

ช่วงนี้เป็นช่วงที่การเงินช็อตเหี้ยๆ ในระดับที่มีเงินเก็นแค่สัปดาห์ละ 700 บาท เลยต้องมาลดต้นทุนกันหน่อย

เริ่มจากของที่ทำงานโดยใช้ NodeJS เช่นตัว [maimai Song Randomizer](https://github.com/rayriffy/maimai-song-randomizer) กับตัว [maimai JSON API](https://github.com/rayriffy/maimai-json-api) ของพวกนี้เตะไปอยู่ที่ Heroku แม่งเลย คราวนี้ถ้าเป็นพวกฟรีตัว Application จะหลับลงไปถ้าไม่มี Activity มา 30 นาที แล้วเวลาเรียกมาใหม่มันจะนานมาก...อ่อไม่ต้องห่วง มีคนทำ [self-ping](https://github.com/Neamar/heroku-self-ping) เอาไว้เรียกตัวเองให้ตื่นตลอดเวลา

![EVIL LAUGH GIF](https://media.giphy.com/media/xUPGcdeU3wvdNPa1Py/giphy.gif)

## บิล

| รายการ | ราคา |
|-|-|
| rayriffy.com [1 YEAR] | 460 บาท |
| Cloudflare | 0 บาท |
| Heroku | 0 บาท |
| Hosting Plan #T02 | 750 * 12 บาท |

รวมทั้งหมด: **9460 บาทต่อปี**

ตอนนี้ยังไม่เห็นผลมากเท่าไหร่เพราะเว็บบางส่วนยังทำงานบน PHP อยู่ เลยเอา VPS ออกไม่ได้

## ตอนที่ 4: ปัจจุบัน

พึ่งซื้อ Apple Watch Series 4 ไป แม่งช็อตกว่าเดิมอีกสัสเอ้ย

เมื่อก่อน [Riffy Blog](https://github.com/rayriffy/rayriffy-blog) และ [Riffy H](https://github.com/rayriffy/rayriffy-h) ทำงานอยู่บน PHP 7.2 พร้อมกับ Laravel Framework แต่ด้วยการที่เคยเจอประสบการณ์ traffic เข้ามาเยอะมากจนร่วงแล้วทำอะไรต่อไม่ได้เลย จึงถึงจุดที่ว่าต้องเปลี่ยนไปเป็น Static Hosting แล้ว

Static Hosting จะมีข้อดีอยู่ว่าตัวเว็บมัน Generate มาเรียบร้อยแล้วไม่จำเป็นต้องให้ server ประมวลผล PHP script แบบเมื่อก่อน ทำให้ได้ข้อดีไปหนึ่งดอก อีกดอกนึงคือเมื่อไม่จำเป็นต้องมี server ประมวลผล script ก็ไม่จำเป็นต้องเช่า server แล้วดิ...**serverless**!!!

> ขอเบรกตรงนี้ก่อนเลยว่าเราไม่ได้เกลียด PHP นะ PHP ดีมากเวลามาเจอกับบางกรณี แต่กรณีของเรา content มัน static ตลอดเลยไง เลยคิดว่าไม่มีความจำเป็นที่จะต้องอยู่บน PHP ต่อ

คราวนี้จะติดปัญหาต่อมาว่าจะใช้อะไรในการ Generate ให้เป็น Static Content... เราเลยเลือก [GatbyJS](https://www.gatsbyjs.org) มาใช้เพราะมีคนมาป้ายยาว่าเป็น framework ที่ผ่าน Lighthouse Audit แบบ 100 100 100 เลยค่ะ อีกอย่างนึงคือมันเป็น React!! เลือก component มาเล่นสบายๆเลย

ยกตัวอย่างเช่นตัวเล่นเพลง Spotify

https://open.spotify.com/track/41QZvZdRXJf6A87oNyzMKE

หรือจะเป็น YouTube Embeded

`youtube:fp1fc2SeHNM`

บอกเลยว่าชีวิตชิวมากๆหลังเล่นของพวกนี้เป็น

ต่อมาคือ Hosting ว่าจะไป Host ที่ไหน เราเลยเลือกที่จะให้ *Riffy H* ไว้ที่ [Firebase](https://firebase.google.com) ที่นึงเพราะอันนี้ยังมีอีกหลายอย่างที่อยากจะทดลองกับมัน

จุดเด็ดของ Firebase มีดีอยู่ที่ว่าถ้าเราจะทำอะไรที่มันมากกว่า Static Pages งี้ก็สามารถใช้ Firebase Cloud Functions เพื่อเรียกข้อมูลแบบ Dynamic ได้ แล้วไม่ได้ใช้ได้แค่กับเว็บนะ ถ้าใครเขียนแอพ Android หรือ iOS ก็สามารถใช้งาน Firebase ได้ด้วยเหมือนกัน

ส่วน *Riffy Blog* ไปอยู่ที่ [Netlify](https://netlify.com) Host ก็ฟรี, Custom Domain ได้, HTTPS ใช้ Let's Encrypt, Automated Deploy ก็ custom ได้เต็มที่ แล้วมีการเช็ค PR ทุก Build ให้อีก...สุดยอดดดดดด

![Netlify](./IMG_0591.jpg)

การทำ Automated Build & Deploy ก็ให้ [Travis CI](https://travis-ci.org) มาช่วยเช็คทุกขั้นตอนให้ว่าไม่มีอะไรผิดแน่ๆ

### บิล

| รายการ | ราคา |
|-|-|
| rayriffy.com [1 YEAR] | 460 บาท |
| Cloudflare | 0 บาท |
| Heroku | 0 บาท |
| Firebase | 0 บาท |
| Netlify | 0 บาท |
| Travis CI [Public Repository] | 0 บาท |

รวมทั้งหมด: **460 บาทต่อปี**

จบ! ไม่ต้องเสียเงินจ่าย Host สักกะบาทแล้วโว้ยยยยยยยยย

## สรุป

หลังจากลดค่า Hosting จนเหลือ 0 บาทแล้วสภาพทางการเงินก็กลับมาดีขึ้นเยอะมากๆ มีเงินเก็บไปทำอย่างอื่นในอนาคตอีกเพียบ ยังไงก็ได้เอากรณีของเรามาแชร์กันล่ะ ก็ลองเอากลับไปคิดดูละกันว่าจะทำยังไงให้เว็บของคุณเองเนี่ย efficient ที่สุด thx ครับ :3