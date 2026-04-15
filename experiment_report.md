# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-XXXX
**Name:** (Dien ten cua ban)
**Date:** (Dien ngay thuc hien)

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

(Viet nhan xet cua ban o day — it nhat 50 tu)

(Hay phan tich cac van de nhu Duplicate IDs, wrong data types, outliers, null values
va giai thich tai sao chung anh huong den ket qua cua Agent.)

Garbage Data chứa dữ liệu "chưa sạch":
- Duplicate IDs: 2 sản phẩm Laptop và Banana có chung ID là 1.
- Dữ liệu chưa được chuẩn hóa: Broken Chair có giá là "ten dollars". dạng str, trong khi các sản phẩm khác có giá là số (int).
- Null value: Ghost Item có ID và category là null.
- Outliers: xuất hiện Nuclear Reactor bị dán nhãn là electronics với giá rất lớn so với các sản phẩm khác (nguyên nhân trả lới sai).

Agent sẽ nhận input bị nhiễu khi dùng garbage data và trả ra cho người dùng kết quả có chứa lỗi.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

(Viet ket luan cua ban o day)

Đồng ý. Nếu Data chất lượng thấp và quá nhiều noise, input của LLM sẽ dài, không được cô đọng và tốn một lượng lớn token khiến LLM dễ hallucination và đưa ra câu trả lời sai lầm.
