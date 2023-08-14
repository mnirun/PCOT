# แปลเกมเป็นภาษาไทยแบบเรียลไทม์ด้วยโปรแกรม PCOT: การใช้งาน
ปรับปรุงล่าสุด: 14 ส.ค. 2566

 - [การใช้งาน MPC-BE](#การใช้งาน-mpc-be)
 - [การใช้งาน PCOT](#การใช้งาน-pcot)
   - [การแปลภาษาแบบ Free Selection](#การแปลภาษาแบบ-free-selection)
   - [การแปลภาษาแบบ Fixed Translation](#การแปลภาษาแบบ-fixed-translation)
     - [การสร้างรายการ Fixed Translation](#การสร้างรายการ-fixed-translation)
     - [การแก้ไขรายการ Fixed Translation](#การแก้ไขรายการ-fixed-translation)
     - [การลบรายการ Fixed Translation](#การลบรายการ-fixed-translation)
   - [Windows 10 OCR Engine](#windows-10-ocr-engine)
     - [การเพิ่มภาษาสำหรับ Windows 10 OCR](#การเพิ่มภาษาสำหรับ-windows-10-ocr)
   - [การตั้งค่าการอ่าน OCR](#การตั้งค่าการอ่าน-ocr)
   - [Image Processing](#image-processing)

## การใช้งาน MPC-BE

 - เสียบสาย HDMI จากเครื่องเล่นเกมส์เข้าไปที่ HDMI capture card หากใช้ external HDMI capture card ให้เสียบสาย USB/Thunderbolt จาก capture card ไปที่คอมพิวเตอร์

   <kbd>![PCOT_Diagram](Pictures/PCOT_Diagram.png)</kbd>
 - รันไฟล์ **"C:\Translator\MPC-BE.1.6.8.5.x64\mpc-be64.exe"**
 - ไปที่เมนู **"File"** → **"Open Device..."**

   <kbd>![MPC-BE_03_Capture_01](Pictures/MPC-BE_03_Capture_01.png)</kbd>
 - จะปรากฎหน้าจอเครื่องเล่นเกมส์ในโปรแกรม MPC-BE

   <kbd>![MPC-BE_03_Capture_02](Pictures/MPC-BE_03_Capture_02.png)</kbd>
 - สามารถปรับขนาดหน้าจะได้จากเมนู **"View"** → **"Zoom"** หรือกดแป้นพิมพ์ลัด
   - <kbd>Alt</kbd> + <kbd>1</kbd> = 50%
   - <kbd>Alt</kbd> + <kbd>2</kbd> = 100%
   - <kbd>Alt</kbd> + <kbd>3</kbd> = 200%
   - <kbd>Alt</kbd> + <kbd>4</kbd> = Auto Fit

   <kbd>![MPC-BE_03_Capture_03](Pictures/MPC-BE_03_Capture_03.png)</kbd>

## การใช้งาน PCOT

PCOT รองรับการแปลภาษา 2 รูปแบบ ได้แก่
 - **Free Selection:** ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษาจากหน้าจอเกมส์โดยอิสระ เพื่อความสะดวกในการแปลภาษา
 - **Fixed Translation:** กำหนดพื้นที่หน้าจอที่ต้องการแปลภาษาจากหน้าจอเกมส์ไว้ล่วงหน้า เพื่อความรวดเร็วในการแปลภาษา

 <kbd>![PCOT_03_Translation_01](Pictures/PCOT_03_Translation_01.png)</kbd>

### การแปลภาษาแบบ Free Selection

 - เมื่อเปิดโปรแกรมเข้ามาแล้ว ให้ตรวจสอบ OCR engine, ภาษาต้นฉบับ (source language) และ ภาษาที่ต้องการคำแปล (translate language) ที่ใช้งานอยู่ได้จากตำแหน่งต่าง ๆ ดังรูปด้านล่าง

   <kbd>![PCOT_04_Free_Selection_01](Pictures/PCOT_04_Free_Selection_01.png)</kbd>
 - หากต้องการเปลี่ยนภาษาต้นฉบับให้ไปที่เมนู **"設定 (Setting)"** → **"画像加工＆OCR読取設定 (Image processing & OCR reading settings)"**

   <kbd>![PCOT_02_Setup_05_03](Pictures/PCOT_02_Setup_05_03.png)</kbd>
 - ที่หน้าต่าง **"画像加工&OCR読取設定 (Image processing & OCR reading settings)"** → **"OCR読取設定 (OCR scan settings)"** ให้เลือกภาษาต้นฉบับที่ต้องการจากรายการ **"OCR読取言語：(OCR reading language：)"** แล้วกดปุ่ม **"保存 (Save)"** เพื่อบันทึกการตั้งค่า

   <kbd>![PCOT_04_Free_Selection_02_01](Pictures/PCOT_04_Free_Selection_02_01.png)</kbd>
 - กดปุ่ม **"X"** ที่มุมบนขวาเพื่อปิดหน้าต่าง

   <kbd>![PCOT_04_Free_Selection_02_02](Pictures/PCOT_04_Free_Selection_02_02.png)</kbd>
 - เลือกภาษาที่ต้องการคำแปลทางด้านล่างให้เป็น **"Thai"**

   <kbd>![PCOT_04_Free_Selection_03_01](Pictures/PCOT_04_Free_Selection_03_01.png)</kbd>
 - กดปุ่ม **"フリー選択 (Free selection)"** หรือกดแป้นพิมพ์ลัด <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd>

   <kbd>![PCOT_04_Free_Selection_03_02](Pictures/PCOT_04_Free_Selection_03_02.png)</kbd>
 - หน้าจอ MPC-BE จะมืดลง ให้ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษา

   <kbd>![PCOT_04_Free_Selection_04](Pictures/PCOT_04_Free_Selection_04.png)</kbd>
 - PCOT จะทำการอ่านภาษาต้นฉบับจากรูปภาพในเกมแล้วแปลงออกมาเป็นตัวอักษรลงในช่อง **"原文テキストボックス (Original text box)"** ด้านบน และทำการแปลภาษาลงในช่อง **"訳文テキストボックス (Translation text box)"** ด่านล่าง
   
   <kbd>![PCOT_04_Free_Selection_05_01](Pictures/PCOT_04_Free_Selection_05_01.png)</kbd>
 - หากต้องการแปลข้อความใหม่ในพื้นที่หน้าจอเดิม ให้กดปุ่ม **"翻訳 (Translation)"** หรือกดแป้นพิมพ์ลัด <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>0</kbd> โปรแกรมจะอ่านข้อความแล้วแปลภาษาในทันที

   <kbd>![PCOT_04_Free_Selection_05_02](Pictures/PCOT_04_Free_Selection_05_02.png)</kbd>

   <kbd>![PCOT_04_Free_Selection_06](Pictures/PCOT_04_Free_Selection_06.png)</kbd>

   <kbd>![PCOT_04_Free_Selection_07_01](Pictures/PCOT_04_Free_Selection_07_01.png)</kbd>

 - จากรูปด้านบนจะพบว่า Tesseract OCR แปลงตัวอักษรผิดพลาด จากตัวไอใหญ่ **"I"** เป็นเลขหนึ่ง **"1"** เราสามารถแก้ไขข้อความต้นฉบับให้ถูกต้องแล้วกดปุ่ม **"再翻訳 (Retranslation)"** เพื่อแปลข้อความใหม่อีกครั้ง

   <kbd>![PCOT_04_Free_Selection_07_02](Pictures/PCOT_04_Free_Selection_07_02.png)</kbd>

   <kbd>![PCOT_04_Free_Selection_08](Pictures/PCOT_04_Free_Selection_08.png)</kbd>
 - หาก OCR แปลงข้อความบรรทัดต่อบรรทัดทำให้ขาดความต่อเนื่องในการแปลภาษา เราสามารถติ๊กถูกที่ **"改行を無視 (Ignore newlines)"** ทางด้านบนให้รวมข้อความเป็นบรรทัดเดียวกันแล้วกดปุ่ม **"再翻訳 (Retranslation)"** เพื่อแปลข้อความใหม่อีกครั้ง

   <kbd>![PCOT_04_Free_Selection_09](Pictures/PCOT_04_Free_Selection_09.png)</kbd>

   <kbd>![PCOT_04_Free_Selection_10](Pictures/PCOT_04_Free_Selection_10.png)</kbd>

   <kbd>![PCOT_04_Free_Selection_11](Pictures/PCOT_04_Free_Selection_11.png)</kbd>

   <kbd>![PCOT_04_Free_Selection_12](Pictures/PCOT_04_Free_Selection_12.png)</kbd>

### การแปลภาษาแบบ Fixed Translation

#### การสร้างรายการ Fixed Translation

 - เมื่อเปิดโปรแกรมเข้ามาแล้ว ให้กดปุ่ม **"固定翻訳設定 (Fixed translation settings)"**

   <kbd>![PCOT_05_Fixed_Translation_01](Pictures/PCOT_05_Fixed_Translation_01.png)</kbd>
 - ที่หน้าต่าง **"固定翻訳タイトル設定 (Fixed translation title setting)"** ให้พิมพ์ชื่อรายการการแปลในช่องด้านขวา เช่น **"Conversation"** เป็นต้น

   <kbd>![PCOT_05_Fixed_Translation_02_01](Pictures/PCOT_05_Fixed_Translation_02_01.png)</kbd>
 - เลือกภาษาต้นฉบับ **"言語 (Language)"** ให้ถูกต้อง

   <kbd>![PCOT_05_Fixed_Translation_02_02](Pictures/PCOT_05_Fixed_Translation_02_02.png)</kbd>
 - กดปุ่ม **"新規作成 (Create new)"** เพื่อสร้างรายการ fixed translation

   <kbd>![PCOT_05_Fixed_Translation_03](Pictures/PCOT_05_Fixed_Translation_03.png)</kbd>
 - หน้าจอ MPC-BE จะมืดลง ให้ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษา

   <kbd>![PCOT_05_Fixed_Translation_04](Pictures/PCOT_05_Fixed_Translation_04.png)</kbd>
 - PCOT จะแปลภาษาพร้อมกับสร้างรายการ fixed translation ให้ ดังรูปด้านล่าง

   <kbd>![PCOT_05_Fixed_Translation_05](Pictures/PCOT_05_Fixed_Translation_05.png)</kbd>
 - หากต้องการแปลภาษาในพื้นที่หน้าจอที่ได้สร้างรายการไว้แล้ว เพียงแค่เลือกรายการ fixed translation ที่ต้องการแล้วกดปุ่ม **"翻訳 (Translation)"** PCOT ก็จะคลุมพื้นที่หน้าจอที่ต้องการแล้วแปลภาษาให้โดยอัตโนมัติ หรือจะกดแป้นพิมพ์ลัด <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd> (1 = เลขลำดับรายการ fixed translation, แป้นพิมพ์ลัดใช้ได้กับ 9 รายการแรกเท่านั้น) ก็ได้เช่นกัน

   <kbd>![PCOT_05_Fixed_Translation_06](Pictures/PCOT_05_Fixed_Translation_06.png)</kbd>

   <kbd>![PCOT_05_Fixed_Translation_07](Pictures/PCOT_05_Fixed_Translation_07.png)</kbd>

   <kbd>![PCOT_05_Fixed_Translation_08](Pictures/PCOT_05_Fixed_Translation_08.png)</kbd>
 - ลองสร้างรายการ fixed translation ที่ 2 ด้วยการกดปุ่ม **"固定翻訳設定 (Fixed translation settings)"**

   <kbd>![PCOT_05_Fixed_Translation_09](Pictures/PCOT_05_Fixed_Translation_09.png)</kbd>
 - ที่หน้าต่าง **"固定翻訳タイトル設定 (Fixed translation title setting)"** ให้ลบชื่อรายการเก่าแล้วพิมพ์ชื่อรายการใหม่ลงไป เช่น **"An inventory description"** เป็นต้น

   <kbd>![PCOT_05_Fixed_Translation_10](Pictures/PCOT_05_Fixed_Translation_10.png)</kbd>

   <kbd>![PCOT_05_Fixed_Translation_11_01](Pictures/PCOT_05_Fixed_Translation_11_01.png)</kbd>
 - กดปุ่ม **"新規作成 (Create new)"** เพื่อสร้างรายการ fixed translation

   <kbd>![PCOT_05_Fixed_Translation_11_02](Pictures/PCOT_05_Fixed_Translation_11_02.png)</kbd>
 - หน้าจอ MPC-BE จะมืดลง ให้ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษา

    <kbd>![PCOT_05_Fixed_Translation_12](Pictures/PCOT_05_Fixed_Translation_12.png)</kbd>
 - PCOT จะแปลภาษาพร้อมกับสร้างรายการ fixed translation ให้ใหม่ ดังรูปด้านล่าง

   <kbd>![PCOT_05_Fixed_Translation_13](Pictures/PCOT_05_Fixed_Translation_13.png)</kbd>
 - ลองตรวจสอบรายการ fixed translation จะพบว่าลำดับรายการได้เปลี่ยนไปเนื่องจาก PCOT เรียงลำดับรายการตามตัวอักษร ทำให้แป้นพิมพ์ลัดเปลี่ยนใหม่เป็น
   - <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd> = **"An inventory description"**
   - <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>2</kbd> = **"Conversation"**

   <kbd>![PCOT_05_Fixed_Translation_14](Pictures/PCOT_05_Fixed_Translation_14.png)</kbd>
 - หากต้องการให้รายการ fixed translation เรียงตามลำดับที่ต้องการ ให้ใส่ตัวเลขนำหน้าตอนที่สร้างรายการใหม่ เช่น
   - **"1. Conversation"**
   - **"2. An inventory description"**

#### การแก้ไขรายการ Fixed Translation

 - เมื่อเปิดโปรแกรมเข้ามาแล้ว ให้กดปุ่ม **"固定翻訳設定 (Fixed translation settings)"**

   <kbd>![PCOT_05_Fixed_Translation_01](Pictures/PCOT_05_Fixed_Translation_01.png)</kbd>
 - เลือกรายการ fixed translation ที่ต้องการแก้ไขพื้นที่หน้าจอใหม่ ตัวอย่างเช่น พื้นที่เดิมไม่ครอบคลุมข้อความทั้งหมด, ขนาดหน้าจอของ MPC-BE เปลี่ยนไป เป็นต้น

   <kbd>![PCOT_05_Fixed_Translation_15_01](Pictures/PCOT_05_Fixed_Translation_15_01.png)</kbd>
 - กดปุ่ม **"編集 (Edit)"**

   <kbd>![PCOT_05_Fixed_Translation_15_02](Pictures/PCOT_05_Fixed_Translation_15_02.png)</kbd>
 - โปรแกรมจะแสดงข้อความ **"編集内容を保存しました。続けて翻訳範囲を編集しますか？ (Your edits have been saved. Do you want to continue editing the translation range?)"** ให้กดปุ่ม **"Yes"**

   <kbd>![PCOT_05_Fixed_Translation_16](Pictures/PCOT_05_Fixed_Translation_16.png)</kbd>
 - หน้าจอ MPC-BE จะมืดลง ให้ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษา
 - PCOT จะแปลภาษาพร้อมกับอัพเดทพื้นที่หน้าจอของรายการ fixed translation ให้ใหม่

#### การลบรายการ Fixed Translation

 - เมื่อเปิดโปรแกรมเข้ามาแล้ว ให้กดปุ่ม **"固定翻訳設定 (Fixed translation settings)"**

   <kbd>![PCOT_05_Fixed_Translation_01](Pictures/PCOT_05_Fixed_Translation_01.png)</kbd>
 - เลือกรายการ fixed translation ที่ต้องการลบ

   <kbd>![PCOT_05_Fixed_Translation_15_01](Pictures/PCOT_05_Fixed_Translation_15_01.png)</kbd>
 - กดปุ่ม **"削除 (Delete)"**

   <kbd>![PCOT_05_Fixed_Translation_15_03](Pictures/PCOT_05_Fixed_Translation_15_03.png)</kbd>
 - โปรแกรมจะแสดงข้อความ **"選択中の項目を削除します。設定されたデータが全て削除されます。よろしいですか？ (Delete the selected item. All set data will be deleted. Is it OK?)"** ให้กดปุ่ม **"Yes"**

   <kbd>![PCOT_05_Fixed_Translation_17](Pictures/PCOT_05_Fixed_Translation_17.png)</kbd>
 - กดปุ่ม **"閉じる (Close)"**

   <kbd>![PCOT_05_Fixed_Translation_18](Pictures/PCOT_05_Fixed_Translation_18.png)</kbd>

### Windows 10 OCR Engine

PCOT รองรับการใช้งาน Tesseract OCR engine และ Windows 10 OCR engine จากประสบการณ์ใช้งานส่วนตัวและจากวารสารสืบเนื่องจากการประชุมวิชาการระดับนานาชาติ IOP Conference Series: Materials Science and Engineering เรื่อง [An Experimental Performance Analysis on Robotics Process Automation (RPA) With Open Source OCR Engines: Microsoft Ocr And Google Tesseract OCR](https://iopscience.iop.org/article/10.1088/1757-899X/1059/1/012004) พบว่า Windows OCR engine ให้ผลลัพธ์ที่แม่นยำกว่า Tesseract OCR engine แต่ในบางกรณี Tesseract OCR engine ให้ผลลัพธ์ที่ดีกว่า Windows OCR engine

ผมเลือกใช้ Windows 10 OCR engine เป็นหลัก เนื่องจากให้ผลลัพธ์ที่แม่นยำกว่าและทำงานได้เร็วกว่า Tesseract OCR engine

ไม่มี OCR engine ตัวไหนที่ดีที่สุด ทดลองเล่นแล้วเลือกใช้ให้เหมาะกับเกมส์ต่าง ๆ ดูนะครับ **"One size doesn't fit all"**

|หน้าจอเกมที่ใช้ทดสอบ #1|
|:-:|
|<kbd>![PCOT_06_Windows_OCR_01](Pictures/PCOT_06_Windows_OCR_01.png)</kbd>|

|ผลการทดสอบ #1 ด้วย Tesseract OCR engine|ผลการทดสอบ #1 ด้วย Windows 10 OCR engine|
|-|-|
|<kbd>![PCOT_06_Windows_OCR_02](Pictures/PCOT_06_Windows_OCR_02.png)</kbd>|<kbd>![PCOT_06_Windows_OCR_03](Pictures/PCOT_06_Windows_OCR_03.png)</kbd>|
|Are you supporting Link in his ﬂzght? Is there really nothing more 乃 can do?|Are you supporting Link in his fight? Is there really nothing more I can do?|
|คุณสนับสนุน Link ใน ﬂzght ของเขาหรือไม่? ไม่มีอะไรที่乃จะทำได้อีกแล้วจริงๆหรือ?|คุณสนับสนุนลิงค์ในการต่อสู้ของเขาหรือไม่? ไม่มีอะไรที่ฉันทำได้อีกแล้วจริงๆเหรอ?|

|หน้าจอเกมที่ใช้ทดสอบ #2|
|:-:|
|<kbd>![PCOT_06_Windows_OCR_04](Pictures/PCOT_06_Windows_OCR_04.png)</kbd>|

|ผลการทดสอบ #2 ด้วย Tesseract OCR engine|ผลการทดสอบ #2 ด้วย Windows 10 OCR engine|
|-|-|
|<kbd>![PCOT_06_Windows_OCR_05](Pictures/PCOT_06_Windows_OCR_05.png)</kbd>|<kbd>![PCOT_06_Windows_OCR_06](Pictures/PCOT_06_Windows_OCR_06.png)</kbd>|
|OK, OK, I‘ve got this. Greeting time. You‘re a customer, right?|0K, 0K, I've got this. Greeting time. You're a customer, right?|
|ตกลง ตกลง ฉันมีสิ่งนี้ เวลาทักทาย. คุณเป็นลูกค้าใช่ไหม|0K 0K ฉันมีสิ่งนี้ เวลาทักทาย. คุณเป็นลูกค้าใช่ไหม|

#### การเพิ่มภาษาสำหรับ Windows 10 OCR

ก่อนทำการเพิ่มภาษาสำหรับ Windows 10 OCR ผมขอบอกข้อจำกัดของ PCOT OCR ก็คือเราต้อง[เพิ่มภาษาสำหรับ Tesseract OCR](#การเพิ่มภาษาสำหรับ-tesseract-ocr) ก่อน จึงจะสามารถเลือกใช้งาน Windows 10 OCR ในภาษานั้นได้ ถึงแม้เราจะไม่ต้องการใช้ Tesseract OCR ในภาษานั้นเลยก็ตาม

ยกตัวอย่างเช่น หากต้องการแปลภาษาญี่ปุ่น (Japanese) ก็ต้องเพิ่มภาษาญี่ปุ่นสำหรับ Tesseract OCR เข้ามาก่อน แล้วค่อยเพิ่มภาษาญี่ปุ่นสำหรับ Windows 10 OCR หากไม่เพิ่มภาษาญี่ปุ่นสำหรับ Tesseract OCR เข้ามาก่อนก็จะไม่มีภาษาญี่ปุ่นให้เลือกในรายการภาษาต้นฉบับครับ

ขั้นตอนการเพิ่มภาษาสำหรับ Windows 10 OCR มีดังนี้

- กดแป้นพิมพ์ลัด <kbd>Win</kbd> + <kbd>I</kbd> เพื่อเปิดหน้าต่าง **"Settings"** → **"Time & Language"**

  <kbd>![PCOT_06_Windows_OCR_07](Pictures/PCOT_06_Windows_OCR_07.png)</kbd>
- ทางด้านซ้าย ให้เลือกรายการ **"Language"**

  <kbd>![PCOT_06_Windows_OCR_08](Pictures/PCOT_06_Windows_OCR_08.png)</kbd>
- ทางด้านขวา ให้เลือกรายการ **"Add a language"**

  <kbd>![PCOT_06_Windows_OCR_09](Pictures/PCOT_06_Windows_OCR_09.png)</kbd>
- พิมพ์ชื่อภาษาที่ต้องการทางด้านบน

  <kbd>![PCOT_06_Windows_OCR_10](Pictures/PCOT_06_Windows_OCR_10.png)</kbd>
- เลือกภาษาที่ต้องการ แล้วกดปุ่ม **"Next"**

  <kbd>![PCOT_06_Windows_OCR_11](Pictures/PCOT_06_Windows_OCR_11.png)</kbd>
- เอาเครื่องหมายถูกจากรายการด้านบนออกให้หมด เนื่องจากเราต้องการใช้แค่ **"Optical character recognition"** ทางด้านล่างเท่านั้น แล้วกดปุ่ม **"Install"**

  <kbd>![PCOT_06_Windows_OCR_12](Pictures/PCOT_06_Windows_OCR_12.png)</kbd>
- จะปรากฎหน้าต่าง **"User Access Control"** ขึ้นมา ให้กดปุ่ม **"Yes"**
- สามารถตรวจสอบสถานะการเพิ่มภาษาได้โดยกดที่ชื่อภาษา แล้วกดปุ่ม **"Options"**

  <kbd>![PCOT_06_Windows_OCR_13](Pictures/PCOT_06_Windows_OCR_13.png)</kbd>
- รอสักครู่

  <kbd>![PCOT_06_Windows_OCR_14](Pictures/PCOT_06_Windows_OCR_14.png)</kbd>
- เมื่อเสร็จสิ้นการเพิ่มภาษาแล้ว ให้กดปุ่ม **"X"**

  <kbd>![PCOT_06_Windows_OCR_15](Pictures/PCOT_06_Windows_OCR_15.png)</kbd>
- เสร็จสิ้นการเพิ่มภาษาสำหรับ Windows 10 OCR

### การตั้งค่าการอ่าน OCR

เราสามารถตั้งค่าการอ่าน OCR ของ free selection และ fixed translation ต่าง ๆ ได้ดังนี้

 - ไปที่เมนู **"設定 (Setting)"** → **"画像加工＆OCR読取設定 (Image processing & OCR reading settings)"**

   <kbd>![PCOT_02_Setup_05_03](Pictures/PCOT_02_Setup_05_03.png)</kbd>
 - ที่หน้าต่าง **"画像加工&OCR読取設定 (Image processing & OCR reading settings)"** ให้กดปุ่ม **"設定選択 (Setting selection)"**

   <kbd>![PCOT_06_Windows_OCR_16](Pictures/PCOT_06_Windows_OCR_16.png)</kbd>
 - ที่หน้าต่าง **"設定選択：mpc-be64 (Setting selection: mpc-be64)"** ให้เลือกรายการที่ต้องการตั้งค่า ในที่นี้จะเลือกรายการ **"デフォルト (Default)"** ซึ่งเป็นรายการที่ใช้สำหรับ free selection โดยเฉพาะ จากนั้นให้กดปุ่ม **"選択 (Selection)"**

   <kbd>![PCOT_06_Windows_OCR_17](Pictures/PCOT_06_Windows_OCR_17.png)</kbd>
 - ตั้งค่าต่าง ๆ ที่ต้องการ เช่น ภาษาต้นฉบับ, OCR engine เป็นต้น เมื่อตั้งค่าเสร็จแล้ว ให้กดปุ่ม **"保存 (Save)"**

   <kbd>![PCOT_06_Windows_OCR_18_01](Pictures/PCOT_06_Windows_OCR_18_01.png)</kbd>
 - กดปุ่ม **"X"** ที่มุมบนขวาเพื่อปิดหน้าต่าง

   <kbd>![PCOT_06_Windows_OCR_18_02](Pictures/PCOT_06_Windows_OCR_18_02.png)</kbd>

### Image Processing

ก่อนที่จะทำการแปลงข้อความ (OCR) การใช้การประมวลภาพ (image processing) จะช่วยให้การแปลภาษาแม่นยำขึ้น

<kbd>![PCOT_07_Image_Processing_01_01](Pictures/PCOT_07_Image_Processing_01_01.png)</kbd>

#### แนะนำเครื่องมือที่ใช้งาน

 - **カラー設定 (Color setting):** ใช้ปรับความสว่างของภาพ "明度 (Brightness)", ความอิ่มตัวของสี "彩度 (Saturation)", แปลงภาพสีให้เป็นภาพขาวดํา "グレースケール (Grayscale)"
 - **白黒二値化設定 (Black and white binarization setting):** แปลงภาพสีให้เป็นภาพขาวดํา 2 ระดับ

ผมจะยกตัวอย่างการใช้งาน image processing สัก 2-3 กรณี เพื่อให้เข้าใจเครื่องมือต่าง ๆ, หลักการใช้งาน และการนำไปประยุกต์ใช้ในเกมต่าง ๆ ได้ เนื่องจาก image processing ไม่มีสูตรตายตัว เกมเดียวกัน ข้อความตำแหน่งเดียวกัน แต่พื้นหลังต่างกัน ค่า image processing ก็ต่างกัน โดย image processing ใช้งานได้ทั้ง free selection และ fixed translation ครับ

#### Image Processing ตัวอย่างที่ 1: ตัวอักษรบนฉากพื้นหลังสีต่าง ๆ / พื้นหลังไม่ซับซ้อน

 -  ไปที่เมนู **"設定 (Setting)"** → **"画像加工＆OCR読取設定 (Image processing & OCR reading settings)"**

    <kbd>![PCOT_02_Setup_05_03](Pictures/PCOT_02_Setup_05_03.png)</kbd>
 - ที่หน้าต่าง **"画像加工&OCR読取設定 (Image processing & OCR reading settings)"** ให้เลือกรายการที่ต้องการตั้งค่าด้วยการกดปุ่ม **"設定選択 (Setting selection)"** ในที่นี้จะเลือกรายการ **"デフォルト (Default)"** เพื่อใช้แสดงตัวอย่างการใช้งาน image processing

   <kbd>![PCOT_07_Image_Processing_03_01](Pictures/PCOT_07_Image_Processing_03_01.png)</kbd>
 - กดปุ่ม **"画像取得 (image acquisition)"**

   <kbd>![PCOT_07_Image_Processing_03_02](Pictures/PCOT_07_Image_Processing_03_02.png)</kbd>
 - หน้าจอ MPC-BE จะมืดลง ให้ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษา

   <kbd>![PCOT_07_Image_Processing_02](Pictures/PCOT_07_Image_Processing_02.png)</kbd>
 - PCOT จะแสดงรูปที่ผ่านการประมวลภาพทางด้านขวา โดยประมวลตามลำดับทางด้านซ้าย โดยรายการประมวลภาพของ **"デフォルト (Default)"** จะมีเพียงแปลงภาพสีให้เป็นภาพขาวดํา **"ｸﾞﾚｰｽｹｰﾙ (grayscale)"** รายการเดียว

   <kbd>![PCOT_07_Image_Processing_03_03](Pictures/PCOT_07_Image_Processing_03_03.png)</kbd>
 - กดปุ่ม **"OCRテスト (OCR test)"** เพื่อทดสอบ OCR กับภาพด้านขวาที่ผ่านการประมวลแล้ว โดยจะปรากฎข้อความทางด้านล่างขวา

   <kbd>![PCOT_07_Image_Processing_04](Pictures/PCOT_07_Image_Processing_04.png)</kbd>
 - ทดลองเพิ่มเติมกับตัวอักษรสีขาวบนฉากพื้นหลังสีดำ

   <kbd>![PCOT_07_Image_Processing_05](Pictures/PCOT_07_Image_Processing_05.png)</kbd>

   <kbd>![PCOT_07_Image_Processing_07](Pictures/PCOT_07_Image_Processing_07.png)</kbd>
 - ทดลองเพิ่มเติมกับตัวอักษรสีขาวบนฉากพื้นหลังไม่ซับซ้อน

   <kbd>![PCOT_07_Image_Processing_08](Pictures/PCOT_07_Image_Processing_08.png)</kbd>

   <kbd>![PCOT_07_Image_Processing_10](Pictures/PCOT_07_Image_Processing_10.png)</kbd>

#### Image Processing ตัวอย่างที่ 2: ตัวอักษรสีใกล้เคียงกับพื้นหลัง

 -  ไปที่เมนู **"設定 (Setting)"** → **"画像加工＆OCR読取設定 (Image processing & OCR reading settings)"**

    <kbd>![PCOT_02_Setup_05_03](Pictures/PCOT_02_Setup_05_03.png)</kbd>
 - ที่หน้าต่าง **"画像加工&OCR読取設定 (Image processing & OCR reading settings)"** ให้เลือกรายการที่ต้องการตั้งค่าด้วยการกดปุ่ม **"設定選択 (Setting selection)"** ในที่นี้จะเลือกรายการ **"デフォルト (Default)"** เพื่อใช้แสดงตัวอย่างการใช้งาน image processing

   <kbd>![PCOT_07_Image_Processing_03_01](Pictures/PCOT_07_Image_Processing_03_01.png)</kbd>
 - กดปุ่ม **"画像取得 (image acquisition)"**

   <kbd>![PCOT_07_Image_Processing_03_02](Pictures/PCOT_07_Image_Processing_03_02.png)</kbd>
 - หน้าจอ MPC-BE จะมืดลง ให้ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษา

   <kbd>![PCOT_07_Image_Processing_11](Pictures/PCOT_07_Image_Processing_11.png)</kbd>
 - กดปุ่ม **"OCRテスト (OCR test)"** เพื่อทดสอบ OCR กับภาพด้านขวาที่ผ่านการประมวลแล้ว โดยจะปรากฎข้อความทางด้านล่างขวา พบว่าข้อความที่ได้จาก OCR ต่างไปจากข้อความต้นฉบับ
   - ตัวอักษรสีใกล้เคียงกับพื้นหลัง (กรอบสี่เหลี่ยมสีแดง) เมื่อแปลงภาพสีให้เป็นภาพขาวดําจะทำให้แยกตัวอักษรกับพื้นหลังได้ยาก
   - ตัวอักษรสีขาวก็ยังมีจุดผิดพลาดอยู่บ้าง (ลูกศรสีแดง)

   <kbd>![PCOT_07_Image_Processing_13_01](Pictures/PCOT_07_Image_Processing_13_01.png)</kbd>
 - ในกรณีนี้ การประมวลภาพเพียงแค่แปลงภาพสีให้เป็นภาพขาวดําไม่เพียงพอต่อการใช้งาน OCR ให้กดปุ่ม **"削除 (Delete)"** เพื่อลบรายการประมวลภาพออกไป

   <kbd>![PCOT_07_Image_Processing_13_02](Pictures/PCOT_07_Image_Processing_13_02.png)</kbd>
 - เมื่อไม่มีรายการประมวลภาพ ภาพด้านขวาจะกลับไปเป็นภาพต้นฉบับ ผมจะใช้เทคนิคการปรับความสว่างของภาพ **"明度 (Brightness)"** เพื่อแยกตัวอักษรออกจากพื้นหลัง เราสามารถปรับค่าความสว่างของภาพได้ตั้งแต่ 255 ~ -255 โดยปรับค่าไปทางบวกภาพจะสว่างขึ้นและปรับค่าไปทางลบภาพจะมืดลง ผมจะปรับค่าไปที่ -120 (กึ่งกลางระหว่าง 0 ~ -255 และเพื่อความรวดเร็วจะใช้ตัวเลขที่หาร 10 ลงตัวเท่านั้น)

   <kbd>![PCOT_07_Image_Processing_14](Pictures/PCOT_07_Image_Processing_14.png)</kbd>
 - กดปุ่ม **"↑追加 (↑Add)"** สังเกตได้ว่าภาพทางด้านขวามืดลง อ่านตัวอักษรได้ง่ายขึ้น แต่ยังคงมองเห็นพื้นหลังอยู่

   <kbd>![PCOT_07_Image_Processing_15_01](Pictures/PCOT_07_Image_Processing_15_01.png)</kbd>
 - กดปุ่ม **"削除 (Delete)"** เพื่อลบรายการประมวลภาพ

   <kbd>![PCOT_07_Image_Processing_15_02](Pictures/PCOT_07_Image_Processing_15_02.png)</kbd>
 - ปรับค่าไปที่ -130 เพื่อให้ภาพมืดลงอีก แล้วกดปุ่ม **"↑追加 (↑Add)"**

   <kbd>![PCOT_07_Image_Processing_16](Pictures/PCOT_07_Image_Processing_16.png)</kbd>
 - จากภาพทางด้านขวาเราสามารถอ่านข้อความได้ง่ายขึ้นแล้ว ขึ้นตอนต่อไปจะเป็นการแปลงภาพสีให้เป็นภาพขาวดํา 2 ระดับด้วยการใช้ **"Binarization( 二値化)"** มีค่าตั้งแต่ 0 ~ 255 ซึ่งค่านี้จะแตกต่างไปตามแต่ละรูปที่เราประมวลผล PCOT จึงเตรียมปุ่ม **"最適値 (optimal value)"** เพื่อหาค่าที่ดีที่สุดตามวิธี [**"大津の二値化 (Otsu's Binarization Method)"**](https://en.wikipedia.org/wiki/Otsu%27s_method) มาให้เป็นค่าเริ่มต้น ให้เรากดปุ่ม **"最適値 (optimal value)"** แล้วกดปุ่ม ***"↑追加 (↑Add)"**

   <kbd>![PCOT_07_Image_Processing_17](Pictures/PCOT_07_Image_Processing_17.png)</kbd>
 - เมื่อใช้ค่า Binarization เท่ากับ 44 พบว่าตัวอักษรสีแดงหายไปหมด แสดงว่าใส่ค่า Binarization มากเกินไป

   <kbd>![PCOT_07_Image_Processing_18_01](Pictures/PCOT_07_Image_Processing_18_01.png)</kbd>
 - กดปุ่ม **"削除 (Delete)"** เพื่อลบรายการประมวลภาพ

   <kbd>![PCOT_07_Image_Processing_18_02](Pictures/PCOT_07_Image_Processing_18_02.png)</kbd>
 - ทดลองลดค่า Binarization ลงไปที่ 40 (เพื่อความรวดเร็วจะใช้ตัวเลขที่หาร 5 ลงตัวเท่านั้น) แล้วกดปุ่ม ***"↑追加 (↑Add)"**

   <kbd>![PCOT_07_Image_Processing_19](Pictures/PCOT_07_Image_Processing_19.png)</kbd>
 - ค่า Binarization ที่ 40 ตัวอักษรสีแดงก็ยังหายไปอยู่

   <kbd>![PCOT_07_Image_Processing_20_01](Pictures/PCOT_07_Image_Processing_20_01.png)</kbd>
 - กดปุ่ม **"削除 (Delete)"** เพื่อลบรายการประมวลภาพ

   <kbd>![PCOT_07_Image_Processing_20_02](Pictures/PCOT_07_Image_Processing_20_02.png)</kbd>
 - ทดลองลดค่า Binarization ลงไปที่ 35 แล้วกดปุ่ม ***"↑追加 (↑Add)"** ตัวอักษรสีแดงเริ่มกลับมาให้เห็นเป็นตัวอักษรจาง ๆ แล้ว

   <kbd>![PCOT_07_Image_Processing_21](Pictures/PCOT_07_Image_Processing_21.png)</kbd>
 - กดปุ่ม **"OCRテスト (OCR test)"** พบว่าข้อความที่ได้จาก OCR ยังต่างไปจากข้อความต้นฉบับอยู่

   <kbd>![PCOT_07_Image_Processing_22](Pictures/PCOT_07_Image_Processing_22.png)</kbd>
 - ทดลองลดค่า Binarization ลงไปที่ 30 กดปุ่ม **"OCRテスト (OCR test)"** ตัวอักษรสีแดงกลับมาหนาขึ้น แต่ข้อความที่ได้จาก OCR ยังต่างไปจากข้อความต้นฉบับอยู่บ้าง

   <kbd>![PCOT_07_Image_Processing_24](Pictures/PCOT_07_Image_Processing_24.png)</kbd>
 - ลองเปลี่ยนไปใช้เครื่องมือขยายภาพ **"倍率 (Magnification)"** ที่อยู่ในกลุ่ม **"OCR読取設定 (OCR scan settings)"** โดยปรับค่า Magnification ไปที่ 2.5 แล้วกดปุ่ม **"OCRテスト (OCR test)"** ตอนนี้คำว่า **"is"** โผล่มาแล้ว แต่คำว่า **"seals"** กลับหายไปแทน

   <kbd>![PCOT_07_Image_Processing_25](Pictures/PCOT_07_Image_Processing_25.png)</kbd>
 - ลองปรับค่า Magnification ไปที่ 3.0 แล้วกดปุ่ม **"OCRテスト (OCR test)"** ข้อความที่ได้จาก OCR ตรงกับข้อความต้นฉบับแล้ว

   <kbd>![PCOT_07_Image_Processing_26_01](Pictures/PCOT_07_Image_Processing_26_01.png)</kbd>
 - กดปุ่ม **"保存 (Save)"** เพื่อบันทึกการตั้งค่า image processing & OCR reading 

   <kbd>![PCOT_07_Image_Processing_26_02](Pictures/PCOT_07_Image_Processing_26_02.png)</kbd>
 - กดปุ่ม **"X"** ที่มุมบนขวาเพื่อปิดหน้าต่าง

   <kbd>![PCOT_07_Image_Processing_26_03](Pictures/PCOT_07_Image_Processing_26_03.png)</kbd>
 - ทดลองแปลแบบ free selection อีกครั้ง PCOT สามารถแปลได้อย่างถูกต้อง

   <kbd>![PCOT_07_Image_Processing_11](Pictures/PCOT_07_Image_Processing_11.png)</kbd>

   <kbd>![PCOT_07_Image_Processing_27](Pictures/PCOT_07_Image_Processing_27.png)</kbd>
 - หากต้องการตั้งค่า image processing & OCR reading ของรายการ fixed selection ให้ทำตามขั้นตอนข้างต้นโดยเปลี่ยนรายการ **"デフォルト (Default)"** ไปเป็นรายการ fixed translation ที่ต้องการ
