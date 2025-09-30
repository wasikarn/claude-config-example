# Agile Epic Specialist - Claude Desktop Configuration

> Expert AI assistant for managing Jira Epics with advanced analysis, creation, and optimization capabilities

## 📋 Table of Contents

- [Overview](#overview)
- [Setup Instructions](#setup-instructions)
- [Quick Start](#quick-start)
- [Usage Examples](#usage-examples)
- [Available Commands](#available-commands)
- [Features](#features)
- [Best Practices](#best-practices)
- [Troubleshooting](#troubleshooting)

---

## 🎯 Overview

Agile Epic Specialist เป็น custom instruction สำหรับ Claude Desktop ที่ช่วยให้คุณ:

- 📊 **วิเคราะห์ Epic** - ดึงข้อมูลและวิเคราะห์สุขภาพของ Epic แบบ Real-time
- 🆕 **สร้าง Epic ใหม่** - สร้าง Epic พร้อม User Stories ที่มีโครงสร้างชัดเจน
- ✂️ **แบ่ง Epic** - แยก Epic ใหญ่เป็น Epic เล็กๆ ที่จัดการได้ง่าย
- 📈 **ติดตามความคืบหน้า** - เช็คสถานะและคาดการณ์วันเสร็จ
- 🔍 **ค้นหา Epic** - ใช้ JQL และ natural language search
- 💡 **แนะนำการปรับปรุง** - ได้ recommendations แบบ actionable

---

## 🚀 Setup Instructions

### ขั้นตอนที่ 1: เตรียมไฟล์

1. ดาวน์โหลดไฟล์ `agile-epic-specialist-instruction.md`
2. เก็บไว้ที่ที่เข้าถึงง่าย เช่น Desktop หรือ Documents

### ขั้นตอนที่ 2: เปิด Claude Desktop Project

1. เปิด Claude Desktop
2. ไปที่ Project ที่ต้องการใช้งาน
3. คลิกที่ **Settings** (⚙️) หรือ Project name

### ขั้นตอนที่ 3: อัปโหลดไฟล์

1. ในส่วน **Files** → คลิกปุ่ม **+**
2. เลือกไฟล์ `agile-epic-specialist-instruction.md`
3. รอจนอัปโหลดเสร็จ (จะเห็น 590 lines)

### ขั้นตอนที่ 4: เพิ่ม Instructions

1. ในส่วน **Instructions** → คลิกปุ่ม **+**
2. Copy และ Paste ข้อความนี้:

```markdown
# Agile Epic Specialist

You are an expert Agile Epic Specialist. Follow ALL instructions in the file "agile-epic-specialist-instruction.md" for:
- Analyzing Jira epics
- Creating new epics
- Breaking down large epics
- Tracking epic progress
- Using Jira tools and JQL queries

Default Jira Project: https://100-stars.atlassian.net/jira/software/projects/BEP
Default Cloud ID: 100-stars

When user provides a Jira URL or epic key (e.g., BEP-123):
1. Extract the epic key from the URL
2. Use Atlassian tools to fetch latest data
3. Provide comprehensive analysis following the templates in the instruction file
4. Give actionable recommendations

Always refer to the agile-epic-specialist-instruction.md file for detailed guidance on output formats, best practices, and interaction patterns.
```

3. กด **Save**

### ขั้นตอนที่ 5: ทดสอบการทำงาน

พิมพ์คำสั่งนี้เพื่อทดสอบ:

```
"What's my default Jira project?"
```

ถ้า Claude ตอบ URL ของ project ที่ตั้งไว้ แสดงว่า setup สำเร็จ! 🎉

---

## ⚡ Quick Start

### ทดสอบการตั้งค่า

```bash
"What's my default Jira project?"
# ตอบ: https://100-stars.atlassian.net/jira/software/projects/BEP

"Show me what commands I can use"
# แสดงคำสั่งทั้งหมดที่ใช้ได้
```

### ตัวอย่างการใช้งานพื้นฐาน

```bash
# วิเคราะห์ Epic ที่มีอยู่
"Analyze epic BEP-123"
"Check BEP-456"

# ค้นหา Epics
"Search for all epics in progress"
"Find epics updated this week"

# สร้าง Epic ใหม่
"Create epic for payment notifications"

# ติดตามความคืบหน้า
"How is BEP-789 doing?"
```

---

## 📖 Usage Examples

### 1. 🔍 วิเคราะห์ Epic ที่มีอยู่

#### ตัวอย่างที่ 1: ใช้ Epic Key

```bash
"Analyze epic BEP-234"
```

**Output:**
```
📊 EPIC HEALTH REPORT: BEP-234

Epic Details:
- Title: "Implement User Authentication System"
- Status: In Progress (65% complete)
- Progress: 13/20 stories complete
- Created: 2024-02-15 | Updated: 2024-03-01

Story Breakdown:
- ✅ Done: 13 stories (89 points)
- 🔄 In Progress: 4 stories (21 points)
- 📋 To Do: 3 stories (13 points)

Health Score: 8/10

🟢 Strengths:
- Strong progress with consistent velocity
- Clear acceptance criteria on all stories

🟡 Concerns:
- 3 unestimated stories in "To Do"
- Missing password recovery flow stories

💡 Recommendations:
1. Estimate remaining 3 stories in next planning session
2. Add stories for password recovery
3. Consider separate epic for OAuth integration

Next Actions:
- [ ] Estimate stories BEP-251, BEP-252, BEP-253
- [ ] Create password recovery stories
```

#### ตัวอย่างที่ 2: ใช้ Jira URL เต็ม

```bash
"Check this epic: https://100-stars.atlassian.net/browse/BEP-456"
```

Claude จะ:
1. Extract epic key (BEP-456)
2. ดึงข้อมูลจาก Jira
3. วิเคราะห์และให้ health report

#### ตัวอย่างที่ 3: ตรวจสอบเฉพาะเจาะจง

```bash
"What are the blockers in epic BEP-789?"
"How many stories are left in BEP-101?"
"When will BEP-202 be completed?"
```

---

### 2. 🆕 สร้าง Epic ใหม่

#### ตัวอย่างที่ 1: สร้าง Epic พื้นฐาน

```bash
"Create epic for mobile payment integration"
```

**Claude จะถามคำถามเพิ่มเติม:**
```
I'll help you structure an epic for mobile payment integration. Let me ask:

1. Which payment providers? (Stripe, PayPal, Apple Pay?)
2. Support which platforms? (iOS, Android, Web?)
3. Timeline expectation? (1 sprint, 2 sprints?)
4. Key features needed?
```

**หลังจากตอบคำถาม Claude จะสร้าง:**
```
Epic Proposal: Mobile Payment Integration

Business Goal: Enable customers to pay via mobile devices 
to increase conversion rate by 25%

Success Criteria:
- Support 3 payment providers (Stripe, Apple Pay, Google Pay)
- Payment success rate > 99%
- Average transaction time < 3 seconds

Estimated Duration: 4 sprints (8 weeks)

Teams Involved: Mobile, Backend, QA

User Stories:

1. Stripe Integration
   - As a customer
   - I want to pay with credit card
   - So that I can complete purchases easily
   - Acceptance Criteria:
     - [ ] Stripe SDK integrated
     - [ ] Card validation working
     - [ ] Payment confirmation displayed
   - Story Points: 8
   - Priority: High

[... 8-10 more stories ...]

Dependencies:
- PCI compliance approval needed

Risks:
- Payment provider downtime: Use fallback providers
```

#### ตัวอย่างที่ 2: สร้าง Epic แบบละเอียด

```bash
"Help me plan an epic for implementing real-time notifications. 
We need email, SMS, and push notifications. 
Timeline is 3 sprints. 
Focus on payment and order status updates."
```

Claude จะสร้าง Epic ที่ละเอียด พร้อม:
- Business goals ชัดเจน
- 10-15 user stories
- Dependencies และ risks
- Timeline แบ่งตาม sprint

---

### 3. 🔍 ค้นหา Epics

#### ตัวอย่าง JQL-based Search

```bash
"Search for all epics in BEP project"
"Find epics in progress"
"Show me epics updated this week"
"Find blocked epics"
```

#### ตัวอย่าง Natural Language Search

```bash
"Find epics related to payment"
"Show me authentication epics"
"What epics are overdue?"
```

**Output:**
```
Found 5 epics matching your criteria:

1. BEP-123 - User Authentication System (In Progress)
   - Progress: 65% (13/20 stories)
   - Updated: 2 days ago
   - Health: 8/10

2. BEP-456 - OAuth Integration (To Do)
   - Progress: 0% (0/8 stories)
   - Updated: 1 week ago
   - Health: 5/10

[...]

Would you like detailed analysis of any specific epic?
```

---

### 4. ✂️ แบ่ง Epic ใหญ่

#### ตัวอย่างที่ 1: Epic ใหญ่เกินไป

```bash
"Split epic BEP-789"
# หรือ
"This epic is too large: BEP-789"
```

**Claude จะวิเคราะห์และเสนอ:**
```
Original Epic: BEP-789 (25 stories, estimated 4 months)

⚠️ This epic is too large. Recommended split:

Epic 1: User Profile - Phase 1 (Sprint 1-2)
- Stories: BEP-790 to BEP-799 (10 stories)
- Focus: Basic profile CRUD operations
- Dependencies: None
- Deliverable: Users can create/edit profiles

Epic 2: User Profile - Phase 2 (Sprint 3-4)
- Stories: BEP-800 to BEP-809 (8 stories)
- Focus: Advanced features (avatar, privacy settings)
- Dependencies: Epic 1 complete
- Deliverable: Enhanced profile features

Epic 3: User Profile - Phase 3 (Sprint 5-6)
- Stories: BEP-810 to BEP-816 (7 stories)
- Focus: Social features and integrations
- Dependencies: Epic 2 complete
- Deliverable: Complete social profile system

Migration Plan:
1. Create 3 new epics in Jira
2. Use bulk edit to reassign stories
3. Update sprint allocations
4. Notify stakeholders
```

---

### 5. 📈 ติดตามความคืบหน้า

#### ตัวอย่างคำสั่ง

```bash
"How is epic BEP-101 doing?"
"Progress report for BEP-202"
"What's blocking BEP-303?"
"When will BEP-404 finish?"
```

**Output ตัวอย่าง:**
```
Progress Report: BEP-101

Current Status: In Progress
Completion: 12/15 stories (80%)
Velocity: 18 points/sprint

Timeline:
- Started: 2024-02-01
- Target: 2024-03-15
- Projected: 2024-03-20 (5 days delay)

Blockers:
- BEP-110: Waiting for API approval (7 days)
- BEP-112: Assigned developer on leave (3 days)

Risk Level: Medium ⚠️

Recommendations:
1. Escalate API approval to unblock BEP-110
2. Reassign BEP-112 to available developer
3. Consider extending sprint by 1 week
```

---

### 6. 💡 การใช้งานขั้นสูง

#### ตัวอย่างที่ 1: เปรียบเทียบหลาย Epics

```bash
"Compare progress of BEP-100, BEP-101, and BEP-102"
```

#### ตัวอย่างที่ 2: วิเคราะห์ Velocity

```bash
"Analyze velocity trend for epics in Q1 2024"
"What's our average epic completion time?"
```

#### ตัวอย่างที่ 3: Bulk Operations

```bash
"Find all epics with unestimated stories"
"Show me epics missing acceptance criteria"
"List epics with no activity in the last month"
```

---

## 📚 Available Commands

### วิเคราะห์ & ตรวจสอบ

| คำสั่ง | คำอธิบาย |
|--------|----------|
| `"Analyze epic BEP-XXX"` | วิเคราะห์ epic แบบละเอียด |
| `"Check BEP-XXX"` | ตรวจสอบสถานะพื้นฐาน |
| `"Health check BEP-XXX"` | ดู health score |
| `"Review [URL]"` | วิเคราะห์จาก Jira URL |

### สร้างและจัดการ

| คำสั่ง | คำอธิบาย |
|--------|----------|
| `"Create epic for [feature]"` | สร้าง epic ใหม่ |
| `"Help plan epic for [goal]"` | วางแผน epic |
| `"Split BEP-XXX"` | แยก epic ใหญ่ |
| `"Add stories to BEP-XXX"` | เพิ่ม stories |

### ค้นหาและรายงาน

| คำสั่ง | คำอธิบาย |
|--------|----------|
| `"Search for epics in [status]"` | ค้นหาตาม status |
| `"Find epics updated [timeframe]"` | ค้นหาตามเวลา |
| `"List all epics in BEP"` | แสดง epics ทั้งหมด |
| `"Progress report for BEP-XXX"` | รายงานความคืบหน้า |

### ติดตามปัญหา

| คำสั่ง | คำอธิบาย |
|--------|----------|
| `"What's blocking BEP-XXX?"` | ดู blockers |
| `"Show risks in BEP-XXX"` | แสดง risks |
| `"Find unestimated stories"` | หา stories ไม่มี estimate |
| `"When will BEP-XXX finish?"` | คาดการณ์วันเสร็จ |

---

## ✨ Features

### 1. Epic Health Scoring (คะแนนสุขภาพ Epic)

Claude ประเมินสุขภาพของ Epic โดยดูจาก:

- ✅ จำนวน stories (5-15 คือเหมาะสม)
- ✅ Clarity ของ business goal
- ✅ Acceptance criteria ครบถ้วน
- ✅ Stories ได้รับการประมาณการแล้ว
- ✅ ไม่มี blocker นานเกิน 1 sprint
- ✅ มีการอัพเดทสม่ำเสมอ

**คะแนน:**
- 9-10: Excellent ✅
- 7-8: Good 🟢
- 5-6: Fair 🟡
- <5: Poor 🔴

### 2. Smart Story Breakdown

Claude แยก Epic เป็น Stories โดยใช้กลยุทธ์:

- **By User Persona:** แยกตามประเภทผู้ใช้
- **By Workflow:** ตามขั้นตอนการทำงาน
- **By Component:** แยกตาม frontend/backend/database
- **By Time:** แต่ละ story ทำได้ใน 1 sprint
- **By Feature Area:** จัดกลุ่มตามฟังก์ชัน

### 3. Real-time Jira Integration

- ดึงข้อมูลล่าสุดจาก Jira โดยตรง
- ไม่ต้อง copy/paste ข้อมูลเอง
- รองรับ JQL queries
- อ่าน comments และ history

### 4. Actionable Recommendations

แนะนำที่ชัดเจนและทำได้จริง:

- ✅ ระบุ priority (High/Medium/Low)
- ✅ บอกขั้นตอนการทำ
- ✅ ประมาณเวลาที่ใช้
- ✅ ให้ next actions เป็น checklist

### 5. Automatic Risk Detection

Claude ตรวจจับปัญหาอัตโนมัติ:

- 🚩 Epic ใหญ่เกินไป (>20 stories)
- 🚩 Epic นิ่งนานเกินไป (>2 weeks)
- 🚩 มี blockers ค้างนาน
- 🚩 ขาด stories สำคัญ (testing, deployment)
- 🚩 Scope creep ที่เกิดขึ้น

---

## 💎 Best Practices

### การวิเคราะห์ Epic

1. **ตรวจสอบสม่ำเสมอ**
   ```bash
   # ตรวจสอบ epics ทุกวันจันทร์
   "Show me all in-progress epics updated this week"
   ```

2. **ดู Health Score เป็นประจำ**
   ```bash
   # ตรวจสุขภาพของ epics ที่สำคัญ
   "Health check BEP-101, BEP-102, BEP-103"
   ```

3. **ติดตาม Blockers**
   ```bash
   # หา blockers ที่ต้องแก้ด่วน
   "Find all blocked stories across active epics"
   ```

### การสร้าง Epic

1. **เริ่มด้วย Business Goal ชัดเจน**
   - ทำไมต้องทำ epic นี้?
   - Success criteria วัดได้อย่างไร?
   - ใครคือผู้ใช้งาน?

2. **แบ่ง Epic ให้พอดี**
   - 5-15 user stories
   - 2-4 สัปดาห์ทำงาน
   - ไม่เกิน 3 teams

3. **ใส่ Acceptance Criteria ทุก Story**
   ```bash
   "Add acceptance criteria to all stories in BEP-XXX"
   ```

### การจัดการ Epic

1. **Review ทุก Sprint**
   ```bash
   "Show sprint progress for epic BEP-XXX"
   ```

2. **แยก Epic ที่ใหญ่เกินไป**
   ```bash
   # ถ้า epic มี >20 stories
   "Split epic BEP-XXX into phases"
   ```

3. **เช็ค Dependencies**
   ```bash
   "What are the dependencies for epic BEP-XXX?"
   ```

---

## 🔧 Troubleshooting

### ปัญหา: Claude ไม่ตอบตาม Instructions

**สาเหตุ:**
- ไฟล์ไม่ถูกอัปโหลด
- Instructions ไม่ได้ระบุให้อ่านไฟล์

**วิธีแก้:**
1. เช็คว่าไฟล์ `agile-epic-specialist-instruction.md` อยู่ในส่วน Files
2. เช็คว่า Instructions มีข้อความ "Follow ALL instructions in the file..."
3. ลองถาม: "What file should you follow for epic management?"

---

### ปัญหา: Claude หา Epic ไม่เจอ

**สาเหตุ:**
- Epic key ผิด
- ไม่มีสิทธิ์เข้าถึง
- Epic ถูกลบหรือย้าย

**วิธีแก้:**
```bash
# เช็คว่า epic key ถูกต้อง
"Search for epics with keyword [ชื่อ epic]"

# เช็ค project
"What's my default Jira project?"

# ถ้าเป็น project อื่น
"Search in project ABC for epic XYZ-123"
```

---

### ปัญหา: ข้อมูลไม่ตรงกับ Jira

**สาเหตุ:**
- Cache ข้อมูลเก่า
- Jira sync delay

**วิธีแก้:**
```bash
# บังคับดึงข้อมูลใหม่
"Fetch latest data for epic BEP-XXX"
"Refresh epic BEP-XXX"
```

---

### ปัญหา: ไม่สามารถสร้าง Epic ใน Jira

**สาเหตุ:**
- Claude ไม่มีสิทธิ์เขียน
- ต้อง manual creation

**วิธีแก้:**
1. ให้ Claude สร้าง epic proposal
2. Copy โครงสร้างไปสร้างใน Jira เอง
3. หรือขอให้ Claude generate Jira API commands

---

### ปัญหา: Response ยาวเกินไป

**วิธีแก้:**
```bash
# ขอเฉพาะส่วนที่ต้องการ
"Give me only the health score for BEP-XXX"
"Show just the blockers"
"Brief summary of BEP-XXX"
```

---

## 📁 File Structure

```
claude-config-example/
└── instractions/
    ├── README.md  (← คุณอยู่ที่นี่)
    └── agile-epic-specialist-instruction.md
```

---

## 🔗 Resources

### Documentation
- [Atlassian Agile Epics Guide](https://www.atlassian.com/agile/project-management/epics)
- [Jira JQL Reference](https://support.atlassian.com/jira-software-cloud/docs/use-advanced-search-with-jira-query-language-jql/)
- [Claude API Documentation](https://docs.anthropic.com/)

### Tips
- ใช้ epic naming convention ที่ชัดเจน
- Review epics ทุกต้น sprint
- ใช้ labels และ components จัดหมวดหมู่
- เก็บ epic descriptions ให้ทันสมัย

---

## 📝 Changelog

### Version 1.0 (2024)
- ✅ Initial release
- ✅ Support Jira epic analysis
- ✅ Epic creation with story breakdown
- ✅ Health scoring system
- ✅ JQL search integration
- ✅ Real-time Jira data fetching

---

## 🤝 Contributing

พบปัญหาหรือมีข้อเสนอแนะ?

1. สร้าง issue ใน repository
2. แนะนำ use case ใหม่ๆ
3. แชร์ best practices ที่ใช้

---

## 📄 License

MIT License - ใช้ได้อย่างอิสระ

---

## 👨‍💻 Author

Created for efficient Agile Epic management with Claude AI

**Project:** BEP (100-stars)  
**Version:** 1.0  
**Last Updated:** 2024

---

## 🎓 Learning More

### Beginner
1. เริ่มจาก "Analyze epic" command
2. ลองสร้าง epic ง่ายๆ
3. เรียนรู้ health scoring

### Intermediate
1. ใช้ JQL queries
2. แบ่ง large epics
3. ติดตาม velocity

### Advanced
1. Custom automation rules
2. Multi-epic planning
3. Team capacity analysis

---

**Happy Epic Managing! 🚀**

สำหรับคำถามหรือการสนับสนุน ติดต่อได้ที่ project repository
