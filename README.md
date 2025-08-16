# ระบบตรวจจับแก้วอัตโนมัติ (Cup Detection Automation)

โปรเจกต์ Computer Vision สำหรับตรวจจับถ้วยบนสายพานลำเลียงและป้องกันการชนกัน

## 📋 คำอธิบาย

ระบบนี้ใช้เทคโนโลยี YOLOv8/YOLOv11 ในการตรวจจับถ้วยบนสายพานลำเลียง 2 เส้น พร้อมระบบเตือนการชนกันเมื่อแก้วจากสายพานซ้ายและขวาอยู่ใกล้กันเกินไป

## 🚀 การติดตั้ง

1. Clone repository นี้
```bash
git clone https://github.com/yourusername/my-python-automation_cup-project.git
cd my-python-automation_cup-project
```

2. ติดตั้ง dependencies
```bash
pip install -r requirements.txt
```

## 📁 โครงสร้างโปรเจกต์

```
my-python-automation_cup-project/
├── automation_cup.ipynb       # โน้ตบุ๊กหลักสำหรับรันระบบตรวจจับ
├── trainyolo.ipynb           # โน้ตบุ๊กสำหรับเทรนโมเดล
├── bestv8.pt                 # โมเดลที่เทรนแล้ว (best model)
├── automation solution.mp4   # วิดีโอตัวอย่างสำหรับทดสอบ
├── dataset/                  # ชุดข้อมูลสำหรับเทรน
│   ├── data.yaml            # คอนฟิกชุดข้อมูล
│   ├── train/               # ข้อมูลเทรน
│   ├── valid/               # ข้อมูลตรวจสอบ
│   └── test/                # ข้อมูลทดสอบ
└── requirements.txt          # รายการ dependencies
```

## 🎯 วิธีใช้งาน

### การรันระบบตรวจจับ
1. เปิด `automation_cup.ipynb`
2. รันเซลล์ทั้งหมดเพื่อเริ่มระบบตรวจจับ
3. ระบบจะประมวลผลวิดีโอและแสดงผลแบบ real-time

### การเทรนโมเดลใหม่
1. เปิด `trainyolo.ipynb`
2. ปรับพารามิเตอร์ตามต้องการ (epochs, batch size, etc.)
3. รันเซลล์เพื่อเริ่มการเทรน

## ⚙️ คุณสมบัติหลัก

- **ตรวจจับแก้ว**: ใช้ YOLOv8/v11 ตรวจจับแก้วบนสายพาน
- **แบ่งเขตพื้นที่**: เส้นเฉียงแบ่งพื้นที่ซ้าย-ขวา
- **ป้องกันการชน**: เตือนเมื่อแก้วใกล้กันเกิน 20 pixels
- **แสดงผลแบบ Real-time**: บอนดิ้งบ็อกซ์และข้อความเตือน

## 🔧 ข้อกำหนดระบบ

- Python 3.8+
- OpenCV 4.11+
- PyTorch 2.0+
- Ultralytics YOLOv8

## 📊 ข้อมูลชุดฝึก

- **คลาส**: 1 คลาส (cup)
- **รูปแบบ**: YOLO format
- **ขนาดภาพ**: 640x640 pixels
- **แหล่งข้อมูล**: Roboflow

## 🎬 ตัวอย่างผลลัพธ์

เมื่อรันระบบ คุณจะเห็น:
- กรอบสีแดงรอบแก้วที่ตรวจพบ
- เส้นเฉียงสีเหลืองแบ่งเขตซ้าย-ขวา
- ข้อความ "STOP LEFT CONVEYOR" เมื่อมีความเสี่ยงชน
- จำนวนแก้วในแต่ละด้าน

## 📝 หมายเหตุ

- โมเดล `bestv8.pt` ได้รับการเทรนมาแล้วและพร้อมใช้งาน
- สามารถปรับ confidence threshold ได้ในโค้ด (ปัจจุบันตั้งไว้ที่ 0.05)
- ระบบรองรับการประมวลผลทั้ง CPU และ GPU

## 📞 ติดต่อ

หากมีคำถามหรือต้องการความช่วยเหลือ กรุณาติดต่อผ่าน Issues ของ repository นี้

## License

This project is licensed under the terms specified in the LICENSE file.
