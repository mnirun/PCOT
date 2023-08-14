# แปลเกมเป็นภาษาไทยแบบเรียลไทม์ด้วยโปรแกรม PCOT
ปรับปรุงล่าสุด: 14 ส.ค. 2566

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
     - [การเพิ่มภาษาสำหรับ Tesseract OCR](#การเพิ่มภาษาสำหรับ-tesseract-ocr)
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
 - [PCOT Tips](#pcot-tips)
   - [การสร้างโพรเซสนามแฝง เพื่อให้ Fixed Translation เปลี่ยนไปตามเกมต่าง ๆ](#การสร้างโพรเซสนามแฝง-เพื่อให้-fixed-translation-เปลี่ยนไปตามเกมต่าง-ๆ)
   - [เทคนิคเพิ่มความแม่นยำในการแปลให้ดีขึ้น](#เทคนิคเพิ่มความแม่นยำในการแปลให้ดีขึ้น)
   - [PCOT Simple Mode](#pcot-simple-mode)
 - [ข้อมูลอ้างอิง](#ข้อมูลอ้างอิง)

## การติดตั้งโปรแกรม

### การติดตั้งโปรแกรม PCOT

 - เปิดไปที่เวป [PCOT](http://www.gc-net.jp/s_54/)
 - กดปุ่ม **"DL"** จะ link ไปยังไฟล์ที่เก็บอยู่ใน Microsoft OneDrive
   
   <kbd>![PCOT_01_Download_01](Pictures/PCOT_01_Download_01.png)</kbd>
 - กดปุ่ม **"Download"**
   
   <kbd>![PCOT_01_Download_02](Pictures/PCOT_01_Download_02.png)</kbd>

 - เมื่อ download ไฟล์เสร็จแล้ว ให้แตกไฟล์ไปไว้ที่ **"C:\Translator"** หรือโฟลเดอร์อื่น ๆ ตามที่ต้องการ

   <kbd>![PCOT_01_Download_03](Pictures/PCOT_01_Download_03.png)</kbd>
 - **ไฟล์ mod language.dat เป็นภาษาอังกฤษ:** ผมได้แก้ไขไฟล์รายชื่อภาษา OCR จากภาษาญี่ปุ่นให้เป็นภาษาอังกฤษเพื่อความสะดวกในการเลือกภาษาต้นฉบับ แนะนำให้ติดตั้งเพิ่มเติมเพื่อความสะดวกในการใช้งานครับ
   
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
