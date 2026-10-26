# System-Analysis-and-Design
**DriverPass** is a secure, cloud-native platform designed to streamline and modernize the driving lesson experience. It replaces traditional booking complexities with an intuitive self-service portal, real-time automated scheduling, and bank-level financial transaction processing. 

## 🚀 Key Features

### Core System Services (Functional)
* **Self-Service Registration:** Students can easily create and manage profiles online.
* **Real-Time Calendar Booking:** Live scheduling allows students to browse open slots and confirm lesson bookings instantly.
* **Automated Payments:** Secure processing of transactions directly through integrated, certified payment gateways.
* **Business Performance Reports:** Dedicated administrative tools generate metrics on booking frequencies and revenue growth.

### Technical Platform Standards (Nonfunctional)
* **High Availability Architecture:** Powered by multi-core cloud server clusters paired with automated traffic load management.
* **Secure Enterprise Storage:** High-speed data isolation environments protect operational records and customer data.
* **Containerized Deployment:** Application modules run within secure container spaces to effectively isolate vulnerabilities.

---

## 🏗️ Architecture & System Workflow

### Use Case Boundaries
The platform separates system operational privileges into three explicit user roles:
* **Students:** Handle account registration, lesson booking, and payment processing.
* **Instructors:** Publish real-time teaching availability and complete scheduled sessions.
* **Administrators:** Oversee overall system health and run analytics reports.
|   Actor    |          | Actions / Use Cases                        |
+------------+          +--------------------------------------------+
| Student    |  ---->   | Register Account | Book Lesson | Pay       |
| Instructor |  ---->   | Add Availability | Complete Lesson         |
| Admin      |  ---->   | Manage System    | Run Reports             |
+------------+          +--------------------------------------------+

### Process Lifecycles

#### 1. Scheduling Workflow
[ Start ] -> [ Browse Slots ] -> [ Validate Availability ] -> [ Confirm Booking ] -> [ End ]

#### 2. Lesson Payment Processing
[ Start ] -> [ Collect Card Info ] -> [ Gateway Approval ] -> [ Generate Receipt ] -> [ End ]

#### 3. Real-Time Slot Selection Layer Interaction
Student Web UI              Booking Service               Database
|                             |                          |
|--- Select Slot ------------>|                          |
|                             |--- Validate Slot ------->|
|                             |                          |--- Query Status (Self)
|                             |<-- Return Status --------|
|<-- Display Ready -----------|                          |
|                             |                          |
|--- Click Confirm ---------->|                          |
|                             |--- Commit Booking ------>|
|                             |                          |--- Save Record (Self)
|                             |<-- Confirm Save ---------|
|<-- Show Success ------------|                          |

---

## 📊 Data Models (UML Classes)

The core relational data schema is highly structured and built around distinct operational boundaries:

* **Student**
  * `studentID` (Int) — Primary Key
  * `name` (String)
  * `email` (String)
  * `phone` (String)
* **Instructor**
  * `instructorID` (Int) — Primary Key
  * `name` (String)
  * `certificationNum` (String)
* **Lesson**
  * `lessonID` (Int) — Primary Key
  * `dateTime` (DateTime)
  * `status` (String)
* **Payment**
  * `paymentID` (Int) — Primary Key
  * `amount` (Decimal)
  * `transactionStatus` (String)

---

## 🛠️ Tech Stack & Requirements

### Infrastructure & Environment
* **OS Target:** Ubuntu Server Linux OS.
* **Hardware Profile:** Multi-core cloud server nodes configured with **8GB RAM and 4 vCPUs** placed behind a network load balancer.
* **Database Engine:** PostgreSQL (Structured, relational storage metrics ensuring transactional integrity).

### Tools & Engineering Practices
* **Containerization:** Docker containers are utilized to tightly couple and mirror identical local development and production environments.
* **Automation Automation (CI/CD):** Integrated with GitHub Actions pipelines for automated code integration and distribution safety.

## ⚠️ System Limitations
* **Continuous Online Status:** The platform relies strictly on stable, live network access. Offline capabilities are not supported due to the necessity of real-time multi-user availability checks and secure transaction clearing.
* **Rigid Data Structure:** Optimization profiles are mapped entirely to uniform, relational metadata fields (IDs, times, specific strings) rather than unstructured object or file storage parsing mechanisms.
