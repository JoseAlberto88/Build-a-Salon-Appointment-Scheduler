# Salon Appointment Scheduler  
A Bash + PostgreSQL project completed for the freeCodeCamp Relational Database Certification.

This project implements a command‑line appointment scheduler for a salon.  
Users can select a service, enter their phone number, and book an appointment.  
The script interacts directly with a PostgreSQL database using `psql`.

---

## 📌 Features
- Interactive Bash script (`salon.sh`)
- PostgreSQL database (`salon`)
- Three tables:
  - `customers`
  - `services`
  - `appointments`
- Automatic customer creation if phone number is new
- Foreign key relationships
- Clean user prompts
- Fully compliant with freeCodeCamp test suite

---

## 🗄️ Database Schema

### **customers**
| Column        | Type      | Notes                |
|---------------|-----------|----------------------|
| customer_id   | SERIAL PK |                     |
| phone         | VARCHAR   | UNIQUE               |
| name          | VARCHAR   |                      |

### **services**
| Column      | Type      | Notes                |
|-------------|-----------|----------------------|
| service_id  | SERIAL PK |                     |
| name        | VARCHAR   |                      |

### **appointments**
| Column         | Type      | Notes                                      |
|----------------|-----------|--------------------------------------------|
| appointment_id | SERIAL PK |                                            |
| customer_id    | INT       | FK → customers(customer_id)                |
| service_id     | INT       | FK → services(service_id)                  |
| time           | VARCHAR   | Appointment time                           |

---

## 🧠 How It Works
1. User selects a service  
2. User enters phone number  
3. If phone is new → user is added to `customers`  
4. User enters appointment time  
5. Appointment is saved in `appointments`  
6. Confirmation message is displayed  

---

## ▶️ Running the Script

```bash
./salon.sh

