[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112732&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** Ducminh45
**Name:** Duc Minh

---

## Mo ta

Bai lab xay dung mot ETL pipeline don gian cho du lieu san pham va quan sat anh huong cua data quality len AI agent. Pipeline trong `solution.py` doc file JSON, validate record loi, chuan hoa category, tinh gia sau giam 10%, them timestamp xu ly va luu ket qua ra `processed_data.csv`.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python -c "from agent_simulation import simulate_agent_response; print(simulate_agent_response('What is the best electronic product?', 'processed_data.csv')); print(simulate_agent_response('What is the best electronic product?', 'garbage_data.csv'))"
```

### Chay test
```bash
pytest
```

---

## Cau truc thu muc

```text
solution.py              # ETL Pipeline script
raw_data.json            # Du lieu dau vao
processed_data.csv       # Output cua pipeline
garbage_data.csv         # Du lieu stress test co loi
experiment_report.md     # Bao cao thi nghiem
README.md                # File nay
```

---

## Ket qua

Pipeline doc 5 records tu `raw_data.json`, giu lai 3 records hop le va loai 2 records loi do price <= 0 hoac category rong. Output co cac cot `discounted_price` va `processed_at`. Trong stress test, clean data cho ket qua Laptop at $1200, con garbage data lam agent chon Nuclear Reactor at $999999 do outlier khong duoc validate.
