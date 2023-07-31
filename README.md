# แปลเกมส์เป็นภาษาไทยแบบเรียลไทม์ด้วยโปรแกรม PCOT [Draft 2023/07/31]

 - [แนะนำโปรแกรม](#แนะนำโปรแกรม)
   - [เปรียบเทียบ Google Lens กับ PCOT](#เปรียบเทียบ-google-lens-กับ-pcot)
 - [การติดตั้งโปรแกรม](#การติดตั้งโปรแกรม)
   - [การติดตั้งโปรแกรม PCOT](#การติดตั้งโปรแกรม-pcot)
   - [การติดตั้งโปรแกรม Microsoft Visual C++ 2015-2022 Runtime Libraries](#การติดตั้งโปรแกรม-microsoft-visual-c-2015-2022-runtime-libraries)
   - [การติดตั้งโปรแกรม MPC-BE Portable](#การติดตั้งโปรแกรม-mpc-be-portable)
 - [การตั้งค่าโปรแกรม](#การตั้งค่าโปรแกรม)
   - [การตั้งค่าโปรแกรม MPC-BE](#การตั้งค่าโปรแกรม-mpc-be)
   - [การตั้งค่าโปรแกรม PCOT](#การตั้งค่าโปรแกรม-pcot)
     - [การตั้งค่าเริ่มต้น](#การตั้งค่าเริ่มต้น)
     - [การเพิ่มภาษา](#การเพิ่มภาษา)
 - [การใช้งาน PCOT](#การใช้งาน-pcot)
   - [การเลือกภาษา](#การเลือกภาษา)
   - [รูปแบบการแปลภาษา](#รูปแบบการแปลภาษา)
     - [Free Selection](#free-selection)
     - [Fixed Selection](#fixed-selection)
   - [Windows 10 OCR](#windows-10-ocr)
   - [Image Processing](#image-processing)
 - [ข้อมูลอ้างอิง](#ข้อมูลอ้างอิง)

## แนะนำโปรแกรม

โปรแกรม [PCOT](http://www.gc-net.jp/s_54/) ย่อมาจาก <ins>P</ins>rocess <ins>C</ins>onnect <ins>O</ins>CR <ins>T</ins>ranslator เป็น translation support tools โดยคุณ Nuruppo ที่ใช้เทคโนโลยี[การรู้จำอักขระด้วยแสง (OCR)](https://th.wikipedia.org/wiki/การรู้จำอักขระด้วยแสง) รวมเข้ากับ[การแปลด้วยเครื่อง (machine translation)](https://th.wikipedia.org/wiki/การแปลด้วยเครื่อง) โดยใช้บริการแปลภาษาจาก Google Translate และ [Microsoft DeepL Translate](https://www.deepl.com/en/windows-app/) ทำให้การแปลภาษาจากรูปภาพเป็นเรื่องที่ง่ายเพียงแค่คลิกเดียวเท่านั้น

เดิมที PCOT ถูกพัฒนามาเพื่อแปลภาษาในเกมส์บน Windows เป็นหลัก แต่ตัวผมเองนำมาประยุกต์ให้ใช้แปลเกมส์จากเครื่อง [Nintendo Switch](https://www.nintendo.com/th/switch/index.html) (หรือเครื่องเล่นเกมส์อื่น ๆ) ผ่านการใช้งาน HDMI capture card โดยแสดงหน้าจอเกมส์ด้วยโปรแกรม [MPC-BE](https://www.videohelp.com/software/MPC-BE)

เหตุผลที่เลือก PCOT + MPC-BE เพื่อใช้แปลภาษาจากเกมส์เนื่องจาก
 - โปรแกรมมีขนาดเล็ก ทั้งสองโปรแกรมรวมกันไม่ถึง 40 MB และไม่จำเป็นต้องติดตั้งโปรแกรม เพียงแค่แตกไฟล์ก็พร้อมใช้งานได้ทันที
   - ขนาดไฟล์ที่ download
     - **PCOT v1.6.0:** 26,522,036 bytes
     - **MPC-BE v1.6.8.5 (x64):** 13,380,429 bytes
 - PCOT สามารถตั้งค่า image processing ได้ ช่วยให้แปลภาษาแม่นยำมากขึ้น
 - ฟรี ไม่มีค่าใช้จ่าย

ส่วนข้อเสียของ PCOT ก็อาจจะเป็นโปรแกรมที่คุณ Nuruppo พัฒนามาเพื่อใช้งานส่วนตัวเป็นหลัก (อ้างอิงจากบทสัมภาษณ์จาก [GameSpark](https://www.gamespark.jp/article/2021/07/02/110097.html)) ทำให้หน้าจอโปรแกรมมีแค่ภาษาญี่ปุ่นเท่านั้น, ไม่มีคู่มือสอนการใช้งาน (แต่ก็มีคนญี่ปุ่นหลาย ๆ ท่านทำคลิปสอบพร้อมคำบรรยายภาษาอังกฤษ เช่น [Yamachannel](https://www.youtube.com/watch?v=hvPRcvR8bCo) เป็นต้น) ซึ่งบทความนี้ก็จะแนะนำการติดตั้งและใช้งาน PCOT เบื้องต้นให้เป็นขั้นตอนที่สามารถทำตามได้ด้วยตนเอง แต่จะไม่ได้รวมถึงถึงการแปลด้วย DeepL เนื่องจาก DeepL ยังไม่ได้รองรับการแปลเป็นภาษาไทย หากอนาคตรองรับผมจะกลับมาอัพเดทเพิ่มเติมให้ครับ

### เปรียบเทียบ Google Lens กับ PCOT

ถึงแม้ Google Lens และ PCOT จะสามารถแปลภาษาได้ด้วยกันทั้งคู่ แต่วิธีการใช้งาน การปรับแต่งต่าง ๆ ค่อนข้างแตกต่างกัน ผมขอสรุปความแตกต่างในส่วนที่เราใช้งานแปลภาษาในเกมส์เป็นหลักไว้ดังนี้ครับ

|Google Lens|PCOT|
|-|-|
|ใช้งานผ่านโปรแกรมบนมือถือโดยโฟกัสข้อความที่หน้าจอเพื่อแปลภาษา|ใช้งานผ่านโปรแกรมบนเครื่องคอมพิวเตอร์โดยระบุ region บนหน้าจอเพื่อแปลภาษา|
|แสดงข้อความที่แปลภาษาแทนที่ข้อความต้นฉบับ|แสดงข้อความที่แปลภาษาในโปรแกรม PCOT|
|ไม่สามารถกำหนดตำแหน่งที่ต้องการแปลภาษาไว้ล่วงหน้าได้|สามารถกำหนดตำแหน่งที่ต้องการแปลภาษาไว้ล่วงหน้าได้ เพิ่มความสะดวกในการแปลภาษา|
|ตั้งค่า image processing ไม่ได้|ตั้งค่า image processing ได้ ช่วยให้แปลภาษาแม่นยำมากขึ้น|
|เลือกใช้ OCR engine ไม่ได้|เลือกใช้ [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) หรือ Windows 10 OCR ได้|
|ใช้บริการจาก Google Translate เท่านั้น|เลือกใช้บริการจาก Google Translate และ Microsoft DeepL Translate ได้พร้อมกัน|

## การติดตั้งโปรแกรม

### การติดตั้งโปรแกรม PCOT

 - เปิดไปที่เวป [PCOT](http://www.gc-net.jp/s_54/)
 - กดปุ่ม **"DL"** จะ link ไปยังไฟล์ที่เก็บอยู่ใน Microsoft OneDrive
   
   <kbd>![PCOT_01_Download_01](Pictures/PCOT_01_Download_01.png)</kbd>
 - กดปุ่ม **"Download"**
   
   <kbd>![PCOT_01_Download_02](Pictures/PCOT_01_Download_02.png)</kbd>

 - เมื่อ download ไฟล์เสร็จแล้ว ให้แตกไฟล์ไปไว้ที่ **"C:\Translator"** หรือโฟลเดอร์อื่น ๆ ตามที่ต้องการ

   <kbd>![PCOT_01_Download_03](Pictures/PCOT_01_Download_03.png)</kbd>

### การติดตั้งโปรแกรม Microsoft Visual C++ 2015-2022 Runtime Libraries

การใช้งาน PCOT จำเป็นต้องติดตั้ง [Microsoft Visual C++ 2015-2022 Runtime Libraries](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170) ก่อน หากในเครื่องคอมพิวเตอร์ติดตั้งไว้แล้ว (ทดสอบง่าย ๆ โดยให้ลองรันไฟล์ **"C:\Translator\PCOT\PCOT.exe"** หากรันได้แสดงว่าได้ติดตั้ง runtime libraries ไว้แล้ว) สามารถข้ามขั้นตอนนี้ไปยังขั้นตอน[การติดตั้งโปรแกรม MPC-BE Portable](#การติดตั้งโปรแกรม-mpc-be-portable) ได้เลย

 - ทำการ download Microsoft Visual C++ 2015-2022 Runtime Libraries โดยเลือกรุ่น Windows ให้ตรงกับที่ใช้งาน
   - **x64:** [https://aka.ms/vs/17/release/vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)
   - **x86:** [https://aka.ms/vs/17/release/vc_redist.x86.exe](https://aka.ms/vs/17/release/vc_redist.x86.exe)

 - รันไฟล์ Microsoft Visual C++ 2015-2022 Runtime Libraries ติ๊กถูกที่ **"I agree to the license terms and conditions"** แล้วกดปุ่ม **"Install"**
   
   <kbd>![Microsoft_01_Setup_01](Pictures/Microsoft_01_Setup_01.png)</kbd>
 - รอจนโปรแกรมติดตั้งเสร็จ แล้วกดปุ่ม **"Close"**
   
   <kbd>![Microsoft_01_Setup_03](Pictures/Microsoft_01_Setup_03.png)</kbd>

 - ข้อมูลเพิ่มเติม
   - [Windows รุ่น 32 บิตและ 64 บิต: คำถามที่ถามบ่อย](https://support.microsoft.com/th-th/windows/windows-รุ่น-32-บิตและ-64-บิต-คำถามที่ถามบ่อย-c6ca9541-8dce-4d48-0415-94a3faa2e13d)

### การติดตั้งโปรแกรม MPC-BE Portable

MPC-BE โปรแกรมเล่นสื่อมัลติมีเดีย รองรับการแสดงหน้าจอจาก HDMI capture card ผ่านเมนู **"Capture Device..."**

- ทำการ download [MPC-BE](https://www.videohelp.com/software/MPC-BE) โดยเลือกรุ่น Windows ให้ตรงกับที่ใช้งาน
  - **x64:** [MPC-BE.1.6.8.5.x64](https://www.videohelp.com/download/MPC-BE.1.6.8.5.x64.7z)
  - **x86:** [MPC-BE.1.6.8.5.x86](https://www.videohelp.com/download/MPC-BE.1.6.8.5.x86.7z)
- เมื่อ download ไฟล์เสร็จแล้ว ให้แตกไฟล์ไปไว้ที่ **"C:\Translator"** หรือโฟลเดอร์อื่น ๆ ตามที่ต้องการ

   <kbd>![MPC-BE_01_Download_02](Pictures/MPC-BE_01_Download_02.png)</kbd>

- ข้อมูลเพิ่มเติม
  - [Windows รุ่น 32 บิตและ 64 บิต: คำถามที่ถามบ่อย](https://support.microsoft.com/th-th/windows/windows-รุ่น-32-บิตและ-64-บิต-คำถามที่ถามบ่อย-c6ca9541-8dce-4d48-0415-94a3faa2e13d)

## การตั้งค่าโปรแกรม

ในการใช้งานโปรแกรมครั้งแรก เราต้องตั้งค่าต่าง ๆ ให้พร้อมใช้แปลภาษาจากเกมส์ ดังนี้

### การตั้งค่าโปรแกรม MPC-BE

 - รันไฟล์ **"C:\Translator\MPC-BE.1.6.8.5.x64\mpc-be64.exe"** แล้วกดที่ **"<ins>More info</ins>"**

   <kbd>![BE_02_Setup_01](Pictures/MPC-BE_02_Setup_01.png)</kbd>
 - กดปุ่ม **"Run anyway"**

   <kbd>![BE_02_Setup_02](Pictures/MPC-BE_02_Setup_02.png)</kbd>
 - ไปที่เมนู **"View"** → **"Option..."**

   <kbd>![BE_02_Setup_03](Pictures/MPC-BE_02_Setup_03.png)</kbd>
 - ทางด้านซ้าย ให้เลือก **"Player"** แล้วเลือกรายการ **"Player folder"** ที่อยู่ในหัวข้อ **"Location of settings"**

   <kbd>![BE_02_Setup_04](Pictures/MPC-BE_02_Setup_04.png)</kbd>
 - ทางด้านซ้าย ให้เลือก **"Capture"** แล้วเลือกชื่อ HDMI capture card ที่รับสัญญาณ HDMI มาจากเครื่องเล่นเกมส์ แล้วกดปุ่ม **"OK"** ทางด้านล่าง

   <kbd>![BE_02_Setup_05](Pictures/MPC-BE_02_Setup_05.png)</kbd>
 - เสร็จสิ้นการตั้งค่าโปรแกรม MPC-BE

### การตั้งค่าโปรแกรม PCOT

#### การตั้งค่าเริ่มต้น

#### การเพิ่มภาษา

## การใช้งาน PCOT

### การเลือกภาษา

### รูปแบบการแปลภาษา

#### Free Selection

#### Fixed Selection

### Windows 10 OCR

### Image Processing

## ข้อมูลอ้างอิง
 - [Guide :: Recommended Screen Translation Software](https://steamcommunity.com/sharedfiles/filedetails/?id=2847675160)
 - [画面翻訳で簡単に日本語化可能！"PCOT"の使い方ガイド](https://steamcommunity.com/sharedfiles/filedetails/?id=2649183272)
 - [PCOTで日本未対応のゲームを簡単翻訳！便利な機能と使い方を紹介](https://yamachannel-blog.com/game-translation/)
 - [PCOTで日本語未対応のゲームを簡単翻訳！導入方法と基本的な使い方を紹介](https://yamachannel-blog.com/game-translation-pcot/)
 - [An Experimental Performance Analysis on Robotics Process Automation (RPA) With Open Source OCR Engines: Microsoft Ocr And Google Tesseract OCR](https://iopscience.iop.org/article/10.1088/1757-899X/1059/1/012004)
