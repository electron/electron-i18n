# ลักษณะการเขียนโค้ด

เหล่านี้เป็นแนวทางสไตล์สําหรับการเข้ารหัสในอิเล็กตรอน

คุณสามารถเรียกใช้`npm ใช้ผ้าสําลี`เพื่อแสดงปัญหาลักษณะใด ๆ ที่ตรวจพบโดย`cpplint`และ `2009`

## สร้างรหัส

* สิ้นสุดไฟล์ด้วยบรรทัดใหม่
* สถานที่ต้องการในลําดับต่อไปนี้:
  * สร้างในโมดูลโหนด (เช่น`เส้นทาง`)
  * สร้างขึ้นในโมดูลอิเล็กตรอน (เช่น`ipc,` `app)`
  * โมดูลภายในเครื่อง (โดยใช้พาธสัมพัทธ์)
* วางคุณสมบัติคลาสตามลําดับต่อไปนี้:
  * วิธีการและคุณสมบัติระดับ (วิธีการเริ่มต้นด้วย`@`)
  * วิธีการอินสแตนซ์และคุณสมบัติ
* หลีกเลี่ยงรหัสขึ้นอยู่กับแพลตฟอร์ม:
  * ใช้`path.join()`เพื่อต่อชื่อแฟ้ม
  * ใช้`os.tmpdir()`มากกว่า`/tmp`เมื่อคุณต้องการอ้างอิง ไดเรกตอรีชั่วคราว
* Using a plain `return` when returning explicitly at the end of a function.
  * ไม่`ส่งกลับ null` `, ส่งคืนไม่ได้กําหนด` `, null`หรือไม่`ระบุ`

## ซีพลัสและหลาม

สําหรับ C ++ และหลามเราทําตามการเข้ารหัสของโครเมียม[ ลักษณะ.](https://www.chromium.org/developers/coding-style) คุณสามารถใช้ [รูปแบบ clang](clang-format.md)เพื่อจัดรูปแบบรหัส C++ โดยอัตโนมัติ มี ยัง`สคริปต์/cpplint.py`เพื่อตรวจสอบว่าไฟล์ทั้งหมดเป็นไปตาม

รุ่นหลามที่เราใช้ตอนนี้เป็น Python 2.7

รหัส C ++ ใช้จํานวนมากของ abstractions และประเภทของโครเมียม, ดังนั้นมัน แนะนําให้ทําความคุ้นเคยกับพวกเขา สถานที่ที่ดีในการเริ่มต้นคือ [บทคัดย่อที่สําคัญของโครเมียมและโครงสร้างข้อมูล](https://www.chromium.org/developers/coding-style/important-abstractions-and-data-structures) เอกสาร เอกสารกล่าวถึงชนิดพิเศษบางชนิด โดยอัตโนมัติปล่อยหน่วยความจําของพวกเขาเมื่อออกจากขอบเขต), ฯลฯ

## เอกสารประกอบ

* [เขียนสไตล์มาร์ก](https://github.com/remarkjs/remark)ดาวน์

คุณสามารถเรียกใช้`npm ทํางาน lint-docs`เพื่อให้แน่ใจว่าเอกสารของคุณมีการเปลี่ยนแปลง จัดรูปแบบอย่างถูกต้อง

## จาวาสคริปต์

* เขียนรูปแบบจาวาสคริปต์[มาตรฐาน](https://npm.im/standard)
* ชื่อไฟล์ควรต่อด้วย`-`แทน`_`เช่น `ไฟล์ name.js`มากกว่า`file_name.js`เพราะใน [ชื่อโมดูล github /อะตอม](https://github.com/github/atom)มักจะอยู่ใน ฟอร์ม`ชื่อโมดูล` กฎนี้ใช้กับแฟ้ม`.js`เท่านั้น
* ใช้ไวยากรณ์ ES6/ES2015 ที่ใหม่กว่าตามความเหมาะสม
  * [`คอนสต์`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) สําหรับค่าคงที่ที่ต้องการและค่าคงที่อื่น ๆ  ถ้าค่าเป็นดั้งเดิม ให้ใช้การตั้งชื่อตัวพิมพ์ใหญ่ (เช่น`const NUMBER_OF_RETRIES = 5`)
  * [`ให้`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) สําหรับการกําหนดตัวแปร
  * [ฟังก์ชันลูกศร](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) แทนฟังก์ชัน`() { }`
  * [ตัวอักษรของแม่แบบ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) แทนการเรียงต่อกันของสตริงโดยใช้ `+`

## การตั้งชื่อสิ่งต่างๆ

API อิเล็กตรอนใช้รูปแบบการใช้ตัวพิมพ์ใหญ่เดียวกันกับ Node.js:

- เมื่อโมดูลตัวเองเป็นชั้นเช่น`BrowserWindow`ใช้`PascalCase`
- เมื่อโมดูลเป็นชุดของ API เช่น`globalShortcut`ใช้`camelCase`
- เมื่อ API เป็นทรัพย์สินของวัตถุและมีความซับซ้อนพอที่จะอยู่ใน แยกบทเช่น`win.webContents,`ใช้`ผสมกรณี`ของ
- สําหรับ API ที่ไม่ใช่โมดูล ให้ใช้ชื่อที่เป็นธรรมชาติ เช่น`<webview>แท็ก</1>`หรือ `ประมวลผลออบเจกต์`

เมื่อสร้าง API ใหม่ ควรใช้ getters และ setters แทน jQuery ของรูปแบบหนึ่งฟังก์ชั่น ตัวอย่างเช่น`.getText()`และ`.setText (ข้อความ)` เป็นที่ต้องการสําหรับ`.text([text])`. มี [การสนทนา](https://github.com/electron/electron/issues/46)นี้