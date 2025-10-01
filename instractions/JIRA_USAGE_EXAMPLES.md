# Jira Integration - Usage Examples

ตัวอย่างการใช้งาน Agile User Stories Expert กับ Jira

---

## 🎯 วิธีใช้งาน

### ตัวอย่างที่ 1: Review Story ด้วย Issue Key
```
คุณพิมพ์: "Review BEP-1234"

Claude จะ:
1. ดึงข้อมูลจาก Jira อัตโนมัติ
2. วิเคราะห์ user story
3. ให้ feedback และข้อเสนอแนะ
```

### ตัวอย่างที่ 2: Review Story ด้วย URL
```
คุณพิมพ์: "ช่วยดู https://100-stars.atlassian.net/browse/BEP-1234"

Claude จะ:
1. แยก issue key จาก URL
2. ดึงข้อมูลและวิเคราะห์
3. แสดงผลการวิเคราะห์
```

### ตัวอย่างที่ 3: Review หลาย Stories
```
คุณพิมพ์: "เปรียบเทียบ BEP-1234 และ BEP-1235"

Claude จะ:
1. ดึงทั้งสอง stories
2. วิเคราะห์แยกกัน
3. เปรียบเทียบคุณภาพและแนวทาง
```

### ตัวอย่างที่ 4: ปรับปรุง Story
```
คุณพิมพ์: "ปรับปรุง user story BEP-1234 ให้ดีขึ้น"

Claude จะ:
1. ดึง story จาก Jira
2. ชี้จุดที่ควรปรับปรุง
3. เสนอเวอร์ชันที่ดีกว่า
4. ถามว่าต้องการ update ใน Jira หรือไม่
```

---

## 💡 คำสั่งที่ใช้ได้

### Review & Analysis
- `"Review BEP-1234"`
- `"วิเคราะห์ story BEP-1234"`
- `"Check user story BEP-1234"`
- `"ดู BEP-1234 หน่อย"`

### Improvement
- `"ปรับปรุง BEP-1234"`
- `"Improve story BEP-1234"`
- `"แก้ไข BEP-1234 ให้ดีขึ้น"`

### Comparison
- `"เปรียบเทียบ BEP-1234 กับ BEP-1235"`
- `"Compare BEP-1234 and BEP-1235"`
- `"ความแตกต่างระหว่าง BEP-1234 และ BEP-1235"`

### With Context
- `"Review BEP-1234 เน้นที่ acceptance criteria"`
- `"Check sizing ของ BEP-1234"`
- `"BEP-1234 เหมาะกับ sprint นี้ไหม"`

---

## ⚙️ ข้อมูลที่ Claude ดึงจาก Jira

เมื่อคุณให้ issue key หรือ URL, Claude จะดึง:

✅ **Basic Info:**
- Summary (ชื่อเรื่อง)
- Description (รายละเอียด)
- Status (สถานะ)
- Issue Type (ประเภท: Story, Task, Bug)
- Priority (ความสำคัญ)

✅ **Assignment:**
- Assignee (ผู้รับผิดชอบ)
- Reporter (ผู้สร้าง)

✅ **Dates:**
- Created (วันที่สร้าง)
- Updated (วันที่อัปเดตล่าสุด)

✅ **Additional:**
- Comments (ความคิดเห็น)
- Attachments (ไฟล์แนบ - ถ้ามี)
- Linked Issues (issue ที่เชื่อมโยง)

---

## 🔍 ตัวอย่างการวิเคราะห์

### Input
```
Review BEP-1234
```

### Output จาก Claude
```
ฉันได้ดึงและวิเคราะห์ **BEP-1234** จาก Jira แล้ว

**ข้อมูล Story:**
- ชื่อ: "ผู้ใช้สามารถเข้าสู่ระบบด้วย email"
- สถานะ: To Do
- ประเภท: Story
- Priority: High

**Description ปัจจุบัน:**
"As a user, I want to login with email so I can access the system."

**การวิเคราะห์:**

✓ **จุดแข็ง:**
- มีโครงสร้าง "As a, I want to, so that" ครบ
- เป้าหมายชัดเจน (login ด้วย email)

⚠️ **ควรปรับปรุง:**
1. **Persona ไม่ชัดเจน:** "user" กว้างเกินไป
   → ควรระบุว่าเป็น new user, returning customer, หรือ admin?
   
2. **Value ไม่เฉพาะเจาะจง:** "access the system" คลุมเครือ
   → จะทำอะไรในระบบ? เข้าถึงข้อมูลอะไร?
   
3. **ไม่มี Acceptance Criteria**

**เวอร์ชันที่แนะนำ:**
"As a returning customer, I want to securely login using my registered email address, so that I can access my order history and manage my account settings without creating a new account."

**Acceptance Criteria ที่แนะนำ:**
- [ ] ผู้ใช้สามารถกรอก email และ password
- [ ] ระบบตรวจสอบข้อมูลกับฐานข้อมูล
- [ ] แสดงข้อความ error ที่ชัดเจนเมื่อ login ไม่สำเร็จ
- [ ] เมื่อ login สำเร็จให้ redirect ไปที่ dashboard
- [ ] มีตัวเลือก "Remember me"
- [ ] มีลิงก์ "Forgot password"

**การประมาณขนาด (Sizing):**
Story นี้ควรเป็น Small-Medium (3 points)

ต้องการให้ฉันอัปเดต BEP-1234 ใน Jira ด้วยข้อเสนอแนะเหล่านี้ไหมคะ?
```

---

## 🎓 Best Practices

### ✅ ควรทำ:
1. **ระบุ issue key ชัดเจน** - BEP-1234 ดีกว่า "story ที่ว่า"
2. **ให้ context เพิ่ม** - บอกว่าต้องการ review เน้นอะไร
3. **ถามเฉพาะเจาะจง** - "Check sizing" ดีกว่า "ดูหน่อย"
4. **ให้ Claude อัปเดต** - ถ้าชอบ suggestion ให้ Claude update ใน Jira

### ⚠️ ไม่ควร:
1. **ใช้ issue key ที่ไม่มีจริง** - Claude จะไม่เจอและ error
2. **คาดหวังให้ Claude แก้ technical debt** - Claude ช่วยเรื่อง user story structure
3. **ลืมตรวจสอบ permissions** - Claude จะดึงได้เฉพาะ story ที่คุณมีสิทธิ์เข้าถึง

---

## 🚀 Ready to Try!

ตอนนี้คุณสามารถ:
1. Copy issue key จาก Jira (เช่น BEP-1234)
2. Paste ลงใน chat กับ Claude
3. บอก Claude ว่าต้องการให้ทำอะไร (review, improve, compare)
4. รับ feedback และ suggestions

**ตัวอย่างการเริ่มต้น:**
```
"Review BEP-1234 และบอกว่าควรปรับปรุงอะไรบ้าง"
```

มีคำถามหรือต้องการความช่วยเหลือเพิ่มเติมไหมคะ? 😊
