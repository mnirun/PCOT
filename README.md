# แปลเกมส์เป็นภาษาไทยแบบเรียลไทม์ด้วยโปรแกรม PCOT [Draft 2023/08/01]
ปรับปรุงล่าสุด: 1 ส.ค. 2566

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
 - [การใช้งาน MPC-BE](#การใช้งาน-mpc-be)
 - [การใช้งาน PCOT](#การใช้งาน-pcot)
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

ถึงแม้ Google Lens และ PCOT จะสามารถแปลภาษาได้ด้วยกันทั้งคู่ แต่วิธีการใช้งาน การปรับแต่งค่าต่าง ๆ ค่อนข้างแตกต่างกัน ผมขอสรุปความแตกต่างในส่วนที่เราใช้แปลเกมส์เป็นภาษาไทยแบบเรียลไทม์ไว้ดังนี้ครับ

|Google Lens|PCOT|
|-|-|
|ใช้งานผ่านโปรแกรมบนมือถือโดยโฟกัสข้อความที่หน้าจอเพื่อแปลภาษา|ใช้งานผ่านโปรแกรมบนเครื่องคอมพิวเตอร์โดยระบุพื้นที่หน้าจอเพื่อแปลภาษา|
|แสดงข้อความที่แปลภาษาแทนที่ข้อความต้นฉบับ|แสดงข้อความที่แปลภาษาในโปรแกรม PCOT|
|ไม่สามารถกำหนดพื้นที่ที่ต้องการแปลภาษาไว้ล่วงหน้าได้|สามารถกำหนดพื้นที่หน้าจอที่ต้องการแปลภาษาไว้ล่วงหน้าได้ เพิ่มความสะดวกในการแปลภาษา|
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
 - **ไฟล์ mod language.dat เป็นภาษาอังกฤษ:** ผมได้แก้ไขไฟล์รายชื่อภาษา OCR จากภาษาญี่ปุ่นให้เป็นภาษาอังกฤษเพื่อความสะดวกในการเลือกภาษา แนะนำให้ติดตั้งเพิ่มเติมเพื่อความสะดวกในการใช้งานครับ
   
   |ไฟล์ language.dat ต้นฉบับ|ไฟล์ mod language.dat เป็นภาษาอังกฤษ|
   |:-:|:-:|
   |![PCOT_02_Setup_92](Pictures/PCOT_01_Download_92.png)|![PCOT_02_Setup_93](Pictures/PCOT_01_Download_93.png)|
   - เปิดไปที่ [/tessdata/PCOT_1.6.0/language.zip](/tessdata/PCOT_1.6.0/language.zip)
   - กดปุ่ม **"Download raw file"**
  
     <kbd>![PCOT_02_Setup_90](Pictures/PCOT_01_Download_90.png)</kbd>
   - แตกไฟล์ **"language.zip"** ไปไว้ที่ **"C:\Translator\PCOT\tessdata\\"** ทับไฟล์ **"language.dat"** เดิม
  
     <kbd>![PCOT_02_Setup_91](Pictures/PCOT_01_Download_91.png)</kbd>

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

 - รันไฟล์ **"C:\Translator\PCOT\PCOT.exe"** แล้วกดที่ **"<ins>More info</ins>"**

   <kbd>![PCOT_02_Setup_01](Pictures/PCOT_02_Setup_01.png)</kbd>
 - กดปุ่ม **"Run anyway"**

   <kbd>![PCOT_02_Setup_02](Pictures/PCOT_02_Setup_02.png)</kbd>
 - โปรแกรมจะแสดงหน้าจอโพรเซส (Process ที่เป็นคำแรกของชื่อโปรแกรม <ins>P</ins>COT) ที่เราต้องการแปลภาษา ในที่นี้เราจะเลือกรายการที่ **"タイトル (Title)"** ชื่อว่า **"MPC-BE x64 1.6.8.5"** หรือดูจากรายการที่ **"プロセス名 (Process name)"** ชื่อว่า **"mpc-be64"** ก็ได้เช่นกัน จากนั้นให้กดปุ่ม **"選択 (Selection)"** ทางด้านล่าง

   <kbd>![PCOT_02_Setup_03](Pictures/PCOT_02_Setup_03.png)</kbd>
 - ที่มุมล่างซ้ายของโปรแกรมจะแสดงชื่อโพรเซสที่ทำการเชื่อต่ออยู่ **"接続中 (Connecting)"** (Connect ที่เป็นคำที่สองของชื่อโปรแกรม P<ins>C</ins>OT)

   <kbd>![PCOT_02_Setup_04](Pictures/PCOT_02_Setup_04.png)</kbd>
 - ไปที่เมนู **"設定 (Setting)"** → **"システム設定 (System setting)"**

   <kbd>![PCOT_02_Setup_05_01](Pictures/PCOT_02_Setup_05_01.png)</kbd>
 - ที่หน้าต่าง **"PCOTシステム設定  (PCOT system settings)"** เราจะทำการเปลี่ยนฟอนต์ในหัวข้อ **"フォント設定 (Font settings)"** เพื่อให้อ่านข้อความได้ง่ายขึ้น
   - กดที่ปุ่ม **"原文フォント設定 (Source font setting)"** เพื่อเปลี่ยนฟอนต์ภาษาต้นฉบับที่ยังไม่ได้แปล
     
     <kbd>![PCOT_02_Setup_06_01](Pictures/PCOT_02_Setup_06_01.png)</kbd>
     
     <kbd>![PCOT_02_Setup_07](Pictures/PCOT_02_Setup_07.png)</kbd>
   - กดที่ปุ่ม **"訳文フォント設定 (Translation font setting)"** เพื่อเปลี่ยนฟอนต์ภาษาที่แปลแล้ว

     <kbd>![PCOT_02_Setup_06_02](Pictures/PCOT_02_Setup_06_02.png)</kbd>

     <kbd>![PCOT_02_Setup_08](Pictures/PCOT_02_Setup_08.png)</kbd>
 - เมื่อเปลี่ยนฟอนต์เสร็จแล้ว ให้
   - กดปุ่ม **"確定 (Confirm)"** เพื่อยืนยันการตั้งค่า
   - หรือกดปุ่ม **"キャンセル (Cancel)"** ขวาสุด เพื่อยกเลิกการตั้งค่า
   - หรือกดปุ่ม **"リセット (Reset)"** ซ้ายสุด เพื่อรีเซ็ตเป็นค่าเริ่มต้น

     <kbd>![PCOT_02_Setup_09](Pictures/PCOT_02_Setup_09.png)</kbd>

##### รายการตั้งค่าอื่น ๆ ที่น่าสนใจ

 - 共通動作設定 (Common operation settings)
   - 終了時に画面の座標とサイズを記憶 (Remember screen coordinates and size on exit)

     <kbd>![PCOT_02_Setup_09_01](Pictures/PCOT_02_Setup_09_01.png)</kbd>
   - 翻訳後に音声出力 (Voice output after translation)
  
     <kbd>![PCOT_02_Setup_09_02](Pictures/PCOT_02_Setup_09_02.png)</kbd>
   - 範囲選択時にスクリーンショット取得 (Take a screenshot when selecting a range)
  
     <kbd>![PCOT_02_Setup_09_03](Pictures/PCOT_02_Setup_09_03.png)</kbd>
   - 翻訳後にフォーカスを対象プロセスに戻す (Return focus to target process after translation)
  
     <kbd>![PCOT_02_Setup_09_04](Pictures/PCOT_02_Setup_09_04.png)</kbd>

#### การเพิ่มภาษา

ในการแปลภาษาจากเกมส์ต่าง ๆ จำเป็นต้อง download [ไฟล์ภาษาของ Tesseract OCR](https://tesseract-ocr.github.io/tessdoc/Data-Files.html) เพื่อให้โปรแกรม PCOT สามารถอ่านข้อความในเกมส์แล้วแปลงออกมาเป็นตัวอักษร (OCR) เพื่อใช้แปลภาษา (Translate) ต่อไป ขั้นตอนการติดตั้งภาษาต่าง ๆ มีดังนี้

 - ไปที่เมนู **"設定 (Setting)"** → **"OCR言語設定 (OCR language setting)"**

   <kbd>![PCOT_02_Setup_05_03](Pictures/PCOT_02_Setup_05_03.png)</kbd>
 - ที่หน้าต่าง **"Tesseract OCR言語設定 (Tesseract OCR Language Settings)"** จะแสดงรายการภาษาต่าง ๆ ที่ PCOT รองรับ **"対応言語一覧：(List of supported languages：)"** รายการภาษาที่มีเครื่องหมาย **"\* (ดอกจัน)"** นำหน้าชื่อภาษา แสดงว่าเราได้ download ภาษานั้นและ PCOT พร้อมใช้งาน OCR แล้ว โดย PCOT ที่เรา download ตอนต้นจะมาพร้อมกับภาษาอังกฤษและไม่สามารถลบภาษานี้ออกจาก PCOT ได้ โดยในกรอบสี่เหลี่ยมด้านล่างจะแสดงข้อความว่า **"利用可能(削除不可) (Available (cannot be deleted))"** และปุ่ม **"削除 (Delete)"** จะไม่สามารถกดได้

   <kbd>![PCOT_02_Setup_10](Pictures/PCOT_02_Setup_10.png)</kbd>
 - ในตอนนี้เราจะทดลอง download ภาษาญี่ปุ่นเพิ่มเติม ในรายการ **"対応言語一覧：(List of supported languages：)"** ให้เลือก **"Japanese"** โดยในกรอบสี่เหลี่ยมด้านล่างจะแสดงข้อความว่า **"Tesseract OCRの言語データがありません (Missing language data for Tesseract OCR)"**

   <kbd>![PCOT_02_Setup_11_01](Pictures/PCOT_02_Setup_11_01.png)</kbd>
 - กดปุ่ม **"追加/更新 (Add/Update)"** เพื่อ download ภาษาญี่ปุ่น

   <kbd>![PCOT_02_Setup_11_02](Pictures/PCOT_02_Setup_11_02.png)</kbd>
 - รอให้ PCOT download ภาษาสักครู่

   <kbd>![PCOT_02_Setup_12](Pictures/PCOT_02_Setup_12.png)</kbd>

   <kbd>![PCOT_02_Setup_13](Pictures/PCOT_02_Setup_13.png)</kbd>
 - เมื่อ download เสร็จแล้ว ให้กดปุ่ม **"OK"** เป็นอันเสร็จสิ้นการเพิ่มภาษาของ Tesseract OCR

   <kbd>![PCOT_02_Setup_14](Pictures/PCOT_02_Setup_14.png)</kbd>
 - ให้ทำการเพิ่มภาษาต่าง ๆ ที่ต้องการให้ครบถ้วนตามขั้นตอนข้างต้น
 - กดปุ่ม **"閉じる (Close)"** เพื่อปิดหน้าต่าง **"Tesseract OCR言語設定 (Tesseract OCR Language Settings)"**

   <kbd>![PCOT_02_Setup_15](Pictures/PCOT_02_Setup_15.png)</kbd>

## การใช้งาน MPC-BE

 - เสียบสาย HDMI จากเครื่องเล่นเกมส์เข้าไปที่ HDMI capture card
 - หากใช้ external HDMI capture card ให้เสียบสาย USB/Thunderbolt จาก capture card ไปที่คอมพิวเตอร์
 - รันไฟล์ **"C:\Translator\MPC-BE.1.6.8.5.x64\mpc-be64.exe"**
 - ไปที่เมนู **"File"** → **"Open Device..."**

   <kbd>![MPC-BE_03_Capture_01](Pictures/MPC-BE_03_Capture_01.png)</kbd>
 - xxx

## การใช้งาน PCOT

PCOT รองรับการแปลภาษา 2 รูปแบบ ได้แก่
 - **Free Selection:** ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษาจากหน้าจอเกมส์โดยอิสระ เพื่อความสะดวกในการแปลภาษา
 - **Fixed Selection:** กำหนดพื้นที่หน้าจอที่ต้องการแปลภาษาจากหน้าจอเกมส์ไว้ล่วงหน้า เพื่อความรวดเร็วในการแปลภาษา

 <kbd>![PCOT_03_Selection_01](Pictures/PCOT_03_Selection_01.png)</kbd>

### Free Selection

 - กดปุ่ม **"フリー選択 (Free selection)"**

   <kbd>![PCOT_04_Free_Selection_01](Pictures/PCOT_04_Free_Selection_01.png)</kbd>
 - หน้าจอ MPC-BE จะมืดลง ให้ใช้เมาส์ลากคลุมพื้นที่หน้าจอที่ต้องการแปลภาษา

   <kbd>![PCOT_04_Free_Selection_02](Pictures/PCOT_04_Free_Selection_02.png)</kbd>
 - PCOT จะทำการอ่านข้อความในเกมส์แล้วแปลงออกมาเป็นตัวอักษร (OCR ที่เป็นคำที่สามของชื่อโปรแกรม PC<ins>O</ins>T) ปรากฎอยู่ในช่องด้านบน และทำการแปลภาษา (Translate ที่เป็นคำที่สี่ของชื่อโปรแกรม PCO<ins>T</ins>) ปรากฎอยู่ในช่องด้านล่าง

   <kbd>![PCOT_04_Free_Selection_03_01](Pictures/PCOT_04_Free_Selection_03_01.png)</kbd>
 - ...

### Fixed Selection

### Windows 10 OCR

### Image Processing

## ข้อมูลอ้างอิง
 - [Guide :: Recommended Screen Translation Software](https://steamcommunity.com/sharedfiles/filedetails/?id=2847675160)
 - [画面翻訳で簡単に日本語化可能！"PCOT"の使い方ガイド](https://steamcommunity.com/sharedfiles/filedetails/?id=2649183272)
 - [PCOTで日本未対応のゲームを簡単翻訳！便利な機能と使い方を紹介](https://yamachannel-blog.com/game-translation/)
 - [PCOTで日本語未対応のゲームを簡単翻訳！導入方法と基本的な使い方を紹介](https://yamachannel-blog.com/game-translation-pcot/)
 - [An Experimental Performance Analysis on Robotics Process Automation (RPA) With Open Source OCR Engines: Microsoft Ocr And Google Tesseract OCR](https://iopscience.iop.org/article/10.1088/1757-899X/1059/1/012004)
