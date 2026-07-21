# DCA Backtest Simulator

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Demo](https://img.shields.io/badge/demo-live-brightgreen.svg)](https://iindrajeet4.github.io/dca-backtest/)
[![Dependencies](https://img.shields.io/badge/dependencies-none-blue.svg)](#)

A single-file, 100% client-side web app that simulates **dollar-cost averaging (DCA)** against approximate historical annual returns (1990–2025) for three assets: **S&P 500**, **Gold**, and the **SET Index (Thailand)**.

**[🔗 Live Demo / ลองใช้เลย](https://iindrajeet4.github.io/dca-backtest/)**

Open `index.html` in any modern browser — no build step, no server, no external libraries.

## Features

- Set the monthly contribution, start year (1990–2025), and asset.
- Results: total invested, final value, profit (amount and %), investment duration, and **annualized (money-weighted / IRR) return**.
- SVG line chart of portfolio growth vs. cumulative contributions, with a hover/touch tooltip showing values per year.
- **Inflation-adjusted toggle** (default 3%/year, editable) showing real values and real annualized return.
- Bilingual UI — **English / ไทย** toggle, persisted in `localStorage`.
- Dark / light theme toggle, persisted.
- Responsive dashboard layout, vanilla JS + CSS only.

## Data caveats

The embedded return table contains **approximate historical annual returns for educational simulation**, compiled from public long-term return records (index total-return summaries, gold price history, SET Index yearly changes). Figures are rounded and may differ from official sources. Each annual return is converted to a **geometric monthly rate** — `(1 + annual)^(1/12) − 1` — so twelve compounded months reproduce the year's return exactly, but this smooths out intra-year volatility; real DCA results would differ. The annualized figure is a money-weighted (IRR) return solved from the monthly cash flows, and is shown as a real return when inflation adjustment is on.

**This tool is for educational purposes only. It is not investment advice. Past performance does not guarantee future results.**

## License

MIT — see [LICENSE](LICENSE). Inspired by DCA calculators; independent implementation.

---

# เครื่องมือจำลอง DCA ย้อนหลัง (ภาษาไทย)

เว็บแอปไฟล์เดียว ทำงานบนเบราว์เซอร์ 100% สำหรับจำลองการลงทุนแบบถัวเฉลี่ยต้นทุน (DCA) ด้วยผลตอบแทนรายปีโดยประมาณ (ค.ศ. 1990–2025) ของ 3 สินทรัพย์: **S&P 500**, **ทองคำ** และ **ดัชนี SET (ไทย)**

**[🔗 ลองใช้งานได้ทันทีที่นี่](https://iindrajeet4.github.io/dca-backtest/)**

เพียงเปิดไฟล์ `index.html` ในเบราว์เซอร์ — ไม่ต้องติดตั้งอะไรเพิ่ม ไม่ใช้ไลบรารีภายนอก

## คุณสมบัติ

- กำหนดจำนวนเงินลงทุนต่อเดือน ปีเริ่มต้น (1990–2025) และสินทรัพย์
- แสดงเงินลงทุนรวม มูลค่าสุดท้าย กำไร (จำนวนเงินและ %) ระยะเวลาลงทุน และ**ผลตอบแทนต่อปี (แบบ IRR)**
- กราฟเส้น SVG เปรียบเทียบมูลค่าพอร์ตกับเงินลงทุนสะสม พร้อม tooltip เมื่อชี้หรือแตะบนกราฟ
- **สวิตช์ปรับเงินเฟ้อ** (ค่าเริ่มต้น 3% ต่อปี แก้ไขได้) เพื่อดูมูลค่าที่แท้จริง
- สลับภาษา **English / ไทย** และธีมมืด/สว่าง โดยจำค่าที่เลือกไว้
- รองรับหน้าจอมือถือ เขียนด้วย JavaScript และ CSS ล้วน

## ข้อจำกัดของข้อมูล

ตารางผลตอบแทนที่ฝังไว้เป็น**ค่าประมาณเพื่อการจำลองเชิงการศึกษา** รวบรวมจากบันทึกผลตอบแทนระยะยาวที่เผยแพร่สาธารณะ ตัวเลขถูกปัดเศษและอาจต่างจากแหล่งข้อมูลทางการ ผลตอบแทนรายปีถูกแปลงเป็นอัตรารายเดือนแบบเรขาคณิต — `(1 + annual)^(1/12) − 1` — เพื่อให้ทบต้น 12 เดือนได้เท่ากับผลตอบแทนทั้งปีพอดี แต่วิธีนี้ทำให้ความผันผวนระหว่างปีถูกเกลี่ยเรียบ ผลลัพธ์ DCA จริงจะแตกต่างออกไป ตัวเลขผลตอบแทนต่อปีคำนวณแบบ IRR จากกระแสเงินสดรายเดือน และแสดงเป็นผลตอบแทนที่แท้จริงเมื่อเปิดโหมดปรับเงินเฟ้อ

**เครื่องมือนี้มีไว้เพื่อการศึกษาเท่านั้น ไม่ใช่คำแนะนำการลงทุน ผลตอบแทนในอดีตไม่ได้รับประกันผลตอบแทนในอนาคต**

## สัญญาอนุญาต

MIT — ดูไฟล์ [LICENSE](LICENSE) · ได้รับแรงบันดาลใจจากเครื่องคำนวณ DCA ทั่วไป พัฒนาขึ้นใหม่โดยอิสระ
