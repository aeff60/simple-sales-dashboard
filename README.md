# Online Sales — Executive Dashboard 2024

Dashboard แบบ Static HTML สำหรับวิเคราะห์ข้อมูลยอดขายออนไลน์ปี 2024 ไม่ต้องใช้ Server หรือ Backend

## ภาพรวม

แสดงข้อมูลจากไฟล์ `Online Sales Data.csv` ในรูปแบบ Executive Dashboard พร้อม KPI Cards และกราฟหลากหลายรูปแบบ โดยสามารถกรองข้อมูลตาม Region ได้แบบ Real-time

## Features

- **KPI Cards** — Total Revenue, Units Sold, Avg. Order Value, Transactions
- **Monthly Revenue Trend** — กราฟเส้นแสดงรายได้รายเดือน
- **Revenue by Region** — Donut Chart แยกตามภูมิภาค
- **Revenue by Category** — Bar Chart แยกตามหมวดสินค้า
- **Category Performance** — Radar Chart เปรียบเทียบ Revenue / Units / Avg. Price
- **Payment Methods** — Horizontal Bar Chart แยกตามช่องทางชำระเงิน
- **Top 10 Products by Revenue** — ตารางสินค้าขายดี
- **Month-on-Month Change** — กราฟแท่งแสดงการเปลี่ยนแปลงรายเดือน
- **Region Filter** — กรองข้อมูลทั้งหมดตาม Region ได้ในคลิกเดียว

## โครงสร้างโปรเจกต์

```
sales-dashboard/
├── index.html           # Dashboard ทั้งหมด (HTML + CSS + JS)
└── Online Sales Data.csv  # ข้อมูลยอดขาย
```

## โครงสร้างข้อมูล CSV

| Field | คำอธิบาย |
|---|---|
| Transaction ID | รหัสธุรกรรม |
| Date | วันที่ขาย (YYYY-MM-DD) |
| Product Category | หมวดหมู่สินค้า |
| Product Name | ชื่อสินค้า |
| Units Sold | จำนวนที่ขายได้ |
| Unit Price | ราคาต่อหน่วย (USD) |
| Total Revenue | รายได้รวม (USD) |
| Region | ภูมิภาค (North America, Europe, Asia, …) |
| Payment Method | ช่องทางชำระเงิน (Credit Card, PayPal, Debit Card, …) |

## การใช้งาน

เปิดไฟล์ `index.html` ในเบราว์เซอร์โดยตรง ไม่ต้องติดตั้งอะไรเพิ่มเติม

```bash
# Windows
start index.html

# macOS / Linux
open index.html
```

> **หมายเหตุ**: เบราว์เซอร์บางตัวบล็อกการอ่านไฟล์ CSV จาก `file://` protocol  
> หากกราฟไม่แสดงผล ให้รันผ่าน Local HTTP Server เช่น:
> ```bash
> npx serve .
> # หรือ
> python -m http.server 8080
> ```

## เทคโนโลยีที่ใช้

| Library | Version | ใช้สำหรับ |
|---|---|---|
| [Chart.js](https://www.chartjs.org/) | 4.4.1 | Render กราฟทุกชนิด |
| [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) | — | Typography |
| Vanilla JS | — | Data parsing & logic |
| CSS Custom Properties | — | Design system / Theming |

## Design

- **Theme**: Dark mode (Navy / Teal accent)
- **Color Palette**: Teal `#00d4c8` · Gold `#ffc84a` · Coral `#ff6b4a` · Blue `#4a9eff`
- **Font**: Inter (Google Fonts)
- **Animations**: CSS `fadeUp` + pulsing logo dot
