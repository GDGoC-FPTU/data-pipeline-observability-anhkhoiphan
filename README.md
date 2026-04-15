[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574062&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.khoipa@vinuni.edu.vn
**Name:** Phan Anh Khôi

---

## Mo ta

(Mo ta ngan gon bai lab va nhung gi ban da lam)

Bài lab gồm những phần sau:
- Đọc file json có raise error khi file not found.
- Viết hàm lấy price và category từ data, loại bỏ dữ liệu có price <= 0 và category là null.
- Viết hàm transform tính discounted_price = price * 0.9, chuẩn hóa category thành Title Case, thêm cột timestamp.
- Load data và csv.
- Thử sử dụng processed data và gargbage data vào một mock agent và nhận xét kết quả.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

(Tom tat ket qua: bao nhieu records da xu ly, bao nhieu bi loai, v.v.)

solution.py: 
Validation summary: 3 kept, 2 dropped.
Errors found: [{'id': 3, 'reason': 'Price <= 0'}, {'id': 4, 'reason': 'Missing Category'}]

agent_simulation.py:
Testing with CLEAN data:
Agent: Based on my data, the best choice is Laptop at $1200.

Testing with GARBAGE data:
Agent: Based on my data, the best choice is Nuclear Reactor at $999999.
