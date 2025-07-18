## 🗒️ Project Log – Setup Phase

### 1. **Cloud SQL Setup (EMR Simulation)**

To simulate data from two hospitals, I provisioned two separate **Cloud SQL (MySQL)** instances:
- `hospital_a_db`
- `hospital_b_db`

**Steps taken:**
- Created MySQL instances in GCP for each hospital.
- Created users and databases for both instances.
- Executed a SQL schema script to define tables:
  - `patients`, `providers`, `departments`, `encounters`, `transactions`
- Imported CSV data into each table to simulate real EMR transactions.

> 🧠 This simulates a real-world scenario where each hospital maintains its own transactional database.

---

### 2. **Google Cloud Storage (GCS) Setup**

I created a **GCS bucket** to serve as the landing zone and data lake for claims and reference data.

**Directory structure:**
