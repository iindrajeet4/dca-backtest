# DCA Backtest Simulator

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Demo](https://img.shields.io/badge/demo-live-brightgreen.svg)](https://iindrajeet4.github.io/dca-backtest/)
[![Dependencies](https://img.shields.io/badge/dependencies-none-blue.svg)](#)

A single-file, 100% client-side web app that simulates **dollar-cost averaging (DCA)** against historical annual returns (through 2025) for **13 assets**: stock indices of 10 countries — S&P 500 (USA, total return), Nifty 50 (India, 1996+), KOSPI (South Korea), SET (Thailand), CSI 300 (China, 2006+), Nikkei 225 (Japan), TAIEX (Taiwan), FTSE 100 (UK), CAC 40 (France), DAX (Germany, total return) — plus **Gold**, **Bitcoin** (2012+), and **Ethereum** (2016+). Contribute in **any of 30+ world currencies** (converted at the live ECB rate).

**[🔗 Live Demo / ลองใช้เลย](https://iindrajeet4.github.io/dca-backtest/)**

Open `index.html` in any modern browser — no build step, no server, no external libraries.

## Features

- Set the monthly contribution, **contribution currency** (30+ currencies via the free [Frankfurter](https://frankfurter.dev/) ECB API, no key), start year, and asset — the selectable start year is clamped to each asset's reliable data start.
- **Live prices where a free API exists**: current BTC/ETH prices and EUR-cross FX rates are fetched on load (CoinGecko + Frankfurter, both free/no-key). Stock indices have no free real-time public API, so the app clearly labels index data as "through 2025" instead of faking live values.
- Results: total invested, final value, profit (amount and %), investment duration, and **annualized (money-weighted / IRR) return**.
- SVG line chart of portfolio growth vs. cumulative contributions, with a hover/touch tooltip showing values per year.
- **Inflation-adjusted toggle** (default 3%/year, editable) showing real values and real annualized return.
- Bilingual UI — **English / ไทย** toggle, persisted in `localStorage`.
- Dark / light theme toggle, persisted.
- Responsive dashboard layout, vanilla JS + CSS only.

## Data caveats

The embedded return tables contain **historical annual returns for educational simulation**, compiled from official index publishers' year-end records and reputable aggregations of them (S&P Dow Jones Indices published total returns; year-end closes of Nifty 50, KOSPI, SET, CSI 300, Nikkei 225, TAIEX, FTSE 100, CAC 40 and the DAX performance index as documented on each index's Wikipedia annual-returns table; LBMA gold price history; exchange-recorded BTC/ETH year-end prices). Figures are rounded calendar-year percentages in each asset's local-currency/USD terms; historical FX between your contribution currency and the asset's currency is not modeled. Each annual return is converted to a **geometric monthly rate** — `(1 + annual)^(1/12) − 1` — so twelve compounded months reproduce the year's return exactly, but this smooths out intra-year volatility; real DCA results would differ. The annualized figure is a money-weighted (IRR) return solved from the monthly cash flows, and is shown as a real return when inflation adjustment is on.

**This tool is for educational purposes only. It is not investment advice. Past performance does not guarantee future results.**

## License

MIT — see [LICENSE](LICENSE). Inspired by DCA calculators; independent implementation.

---

# เครื่องมือจำลอง DCA ย้อนหลัง (ภาษาไทย)

เว็บแอปไฟล์เดียว ทำงานบนเบราว์เซอร์ 100% สำหรับจำลองการลงทุนแบบถัวเฉลี่ยต้นทุน (DCA) ด้วยผลตอบแทนรายปีย้อนหลัง (ถึงสิ้นปี 2025) ของ **13 สินทรัพย์**: ดัชนีหุ้น 10 ประเทศ — S&P 500 (สหรัฐฯ), Nifty 50 (อินเดีย), KOSPI (เกาหลีใต้), SET (ไทย), CSI 300 (จีน), Nikkei 225 (ญี่ปุ่น), TAIEX (ไต้หวัน), FTSE 100 (อังกฤษ), CAC 40 (ฝรั่งเศส), DAX (เยอรมนี) — พร้อม **ทองคำ**, **Bitcoin** และ **Ethereum** เลือกสกุลเงินลงทุนได้กว่า 30 สกุลทั่วโลก (แปลงด้วยอัตรา ECB สด ฟรีไม่มีค่าใช้จ่าย)

**[🔗 ลองใช้งานได้ทันทีที่นี่](https://iindrajeet4.github.io/dca-backtest/)**

เพียงเปิดไฟล์ `index.html` ในเบราว์เซอร์ — ไม่ต้องติดตั้งอะไรเพิ่ม ไม่ใช้ไลบรารีภายนอก

## คุณสมบัติ

- กำหนดจำนวนเงินลงทุนต่อเดือน **สกุลเงิน** (30+ สกุลผ่าน Frankfurter/ECB API ฟรีไม่ต้องมี key) ปีเริ่มต้น และสินทรัพย์ — ปีเริ่มต้นถูกจำกัดตามช่วงข้อมูลที่เชื่อถือได้ของแต่ละสินทรัพย์
- **ราคาสดเท่าที่มี API ฟรี**: BTC/ETH และอัตราแลกเปลี่ยน ดึงสดตอนเปิด (CoinGecko + Frankfurter) ส่วนดัชนีหุ้นไม่มี API สดแบบฟรี แอปจึงระบุชัดว่า "ข้อมูลถึงปี 2025" แทนการปลอมราคา
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
