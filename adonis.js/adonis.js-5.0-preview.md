---
description: >-
  Adonis.js เป็น javascript web framework ตัวนึงที่ค่อนข้างตอบโจทย์ มีของครบ
  เรียนรู้ง่าย ยิ่งถ้าใครเคยใช้ laravel มาก่อน ถ้ามาใช้ตัวนี้ จะพบว่า concept
  เหมือนกันเลย
---

# Adonis.js 5.0 Preview ปล่อยมาให้ลองแล้ว

> ! **Feature** ยังไม่ได้ครบนะ ดังนั้นคงไม่เหมาะกับงานจริง เหมาะสำหรับลองเล่นเท่านั้น

### Feature เด็ด

* **TypeScript** ในที่สุดก็รองรับซะที \(ถ้าใครไม่รู้จักเบื้องต้นมันก็คือภาษา JavaScript ที่จะต้องกำหนด Type ตัวแปรนั้นเอง มีฟีเจอร์เยอะมากๆ ลองหาอ่านกันได้\) โดย version 5 Preview จะรองรับทั้ง TypeScript และ JavaScript
* **Ace** เป็นพระเอก ลาก่อน Adonis CLI ไม่ต้องติดตั้งแล้ว เพราะจะ gen file ต่างๆ ก็สามารถใช้ ace ได้เลย, ส่วนการสร้าง project ใช้ npx, yarn create
* **No more Use** ใช้ Import แบบ ES6 ถ้าเป็น version ก่อน Adonis จะใช้ use แทนการ import
* **Health Checks** สามารถ Return สถานะของ App เราได้ เหมาะสำหรับการทำ Microservice
* **Signed Routes** สามารถ generate route ได้แล้ว เช่น route สำหรับยืนยัน email โดยจะสามารถกำหนดกฎในการ valid ของ route parameter ได้ 

  อ่านเพิ่ม [URL Generation - AdonisJS](https://preview.adonisjs.com/guides/http/url-generate#generating-signed-urls)

> ต้องมี node.js บนเครื่องก่อนนะครับ ใครยังไม่มี โหลดเลยที่ [nodejs.org](h) แนะนำเลือกเป็น version LTS

### Step การสร้าง Project

1. สร้าง Project ด้วยคำสั่งตามนี้เลย ใครชอบ npx หรือ yarn ก็เลือกกันได้เลยย
   * `npx create-adonis-ts-app <project-name>` 
   * `yarn create adonis-ts-app <project-name>`
2. เลือก template ของ project ซึ่งจะมีสองอัน คือ
   * full project มี view มาด้วย เหมาะสำหรับคนอยากทำ website ทั้งหมด
   * api จะไม่มี view มาด้วย เหมาะสำหรับทำ api อย่างเดียว
3. `cd <project-name>`  เพื่อเข้าไปยัง folder project
4. `node ace serve —watch`  เพื่อ run ตัว adonis ซึ่งจะแสดง port ที่กำลัง run
5. `node ace build —production`  เพื่อทำการ compile TypeScript เป็น JavaScript โดยจะเมื่อ compile เสร็จจะอยู่ใน folder build ซึ่งก็สามารถ copy ไปแล้วใช้ node server.js เพื่อ run ได้เลย

### โครงสร้าง folder

```text
.
├── app
├── commands
├── config
├── contracts
├── providers
├── public
├── resources
│   └── views
├── start
│   ├── kernel.ts
│   └── routes.ts
├── .adonisrc.json
├── .editorconfig
├── .env
├── .env.example
├── .eslintignore
├── .eslintrc.json
├── .gitignore
├── ace
├── package.json
├── server.ts
├── tsconfig.json
```

#### Folder ที่สำคัญ

* **app** จะเก็บไฟล์ controller, mode, service ต่างๆ
* **config**จะเก็บไฟล์ตั้งค่าของแอป เช่น การเชื่อมต่อ Database
* **contracts** ตัวนี้จะเก็บ type, enum, interface ของ TypeScript
* **start** จะเก็บไฟล์ที่จะ run ก่อนใคร \(รวมถึง register route, middleware\)
* **resources** จะเก็บไฟล์ view, ไฟล์ frontend ที่ยังไม่ได้ compile เช่น SASS
* **public** จะเก็บไฟล์ static, ไฟล์ frontend ที่ compile แล้ว เช่น .css จาก SASS
* **database**  จะเก็บไฟล์ migration สำหรับการสร้าง แก้ไข ตารางของฐานข้อมูล
* **providers** จะเก็บไฟล์ register dependencies เพื่อทำ dependencies injection รวมถึงการทำ Singleton ด้วย
* **.env** เป็นไฟล์ในการกำหนด environment variable เช่น กำหนดการเชื่อมต่อ Database \(Database Username, Password, Host\)
* **tsconfig.json** เป็นไฟล์ config TypeScript เช่น กำหนดกฎ , กำหนดการ compile
* **ace** เป็นตัวสำหรับเรียกคำสั่งในการ generate ไฟล์ต่างๆ เช่น controller, model

### อ้างอิง

1. [Introducing AdonisJS \(v5 Preview\)](https://blog.adonisjs.com/introducing-adonisjs-v5/)
2. [Adonis Preview](https://preview.adonisjs.com/)

