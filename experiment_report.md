# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** Ducminh45
**Name:** Duc Minh
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay agent voi cung mot cau hoi: `What is the best electronic product?`

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc validate nen record gia am va category rong bi loai bo. Ket qua phu hop voi san pham electronics co gia cao nhat trong data sach. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Du lieu garbage co duplicate ID, wrong type, null value va outlier cuc lon. Agent bi outlier lam lech ket qua. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai khi dung garbage data vi logic mo phong chi loc category electronics va chon record co price cao nhat. Khi file chua outlier `Nuclear Reactor` voi gia 999999, agent xem day la ung vien tot nhat ma khong hieu day la gia tri bat thuong. Duplicate ID lam data khong con dai dien ro rang cho tung san pham rieng biet. Wrong data type nhu `ten dollars` co the lam cac phep tinh, sap xep hoac so sanh bi loi trong cac pipeline phuc tap hon. Null values lam thieu thong tin can thiet de loc va giai thich. Vi agent phu thuoc vao data dau vao, prompt tot van khong the sua duoc nguon tri thuc bi nhieu, thieu validate va co gia tri doc.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt chi huong dan cach agent tra loi, con data quyet dinh thong tin nao agent su dung. Neu data bi loi, agent co the tra loi rat tu tin nhung van sai. Pipeline can validate, transform va theo doi so record bi loai bo de giam rui ro nay.
