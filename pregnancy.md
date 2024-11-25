
# **PregnancyControllerApi API Documentation**

## **Base URL**
- **API Prefix**: `/api/pregnancy`

## **Authentication**
- **Authentication**: `Bearer Token`

## **Endpoints**

---

### **1. Create New Pregnancy**
Creates a new pregnancy record.

- **Endpoint**: `/create-new-pregnancy`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "date": "2024-01-01"
    }
    ```

---

### **2. Update Ovulation Date**
Updates the ovulation date for a pregnancy record.

- **Endpoint**: `/update-ovulation/{id}`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "date": "2024-02-01"
    }
    ```

---

### **3. End Pregnancy**
Marks a pregnancy as ended.

- **Endpoint**: `/end-pregnancy/{id}`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "status": 1
    }
    ```

---

### **4. Create Pregnancy Clinic**
Creates a clinic visit associated with a pregnancy.

- **Endpoint**: `/create-pregnancy-clinic`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "pregnancy_id": 1,
        "clinic_name": "Clinic A",
        "clinic_date": "2024-03-01",
        "doctor_name": "Dr. Smith",
        "is_extra_clinic": 0,
        "visit_with_partner": 1,
        "notes": "Routine checkup",
        "has_attend": 1,
        "next_date": "2024-03-15",
        "services_choosen": [1, 2]
    }
    ```

---

### **5. Get All Clinics**
Fetches all clinics for a specific pregnancy.

- **Endpoint**: `/get-all-clinics/{id}`
- **Method**: `GET`

---

### **6. Get All Week-Based Services**
Fetches services based on pregnancy week.

- **Endpoint**: `/get-all-week-based-services/{week_number}`
- **Method**: `GET`

---

### **7. Get All Services**
Fetches all available services for a specific pregnancy and clinic.

- **Endpoint**: `/get-all-services/{id}/{clinic_id}`
- **Method**: `GET`

---

### **8. Get All Special Services**
Fetches special services for a specific pregnancy, clinic, and week.

- **Endpoint**: `/get-all-special-services/{id}/{clinic_id}/{week_number}`
- **Method**: `GET`

---

### **9. Get Current Pregnancy**
Fetches the current active pregnancy.

- **Endpoint**: `/get-current-pregnancy`
- **Method**: `GET`

---

### **10. Update Delivery Plan**
Updates the delivery plan for a specific pregnancy.

- **Endpoint**: `/update-delivery-plan/{id}`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "delivery_date": "",
        "delivery_center": "",
        "pregnancy_type": "",
        "visiting_center": "",
        "send_center": "",
        "remain_home": "1",
        "tools": [1,2,3]
    }
    ```

---

### **11. Update Clinic Service**
Updates the status of a service within a clinic.

- **Endpoint**: `/update-clinic-service`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "service_id": 1,
        "pregnancy_id": 1,
        "clinic_id": 1,
    }
    ```
---

### **12. Create Clinic Visit**
Creates a new clinic visit associated with a pregnancy.

- **Endpoint**: `/create-clinic-visit/{id}`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "visit_date": "2024-04-01",
        "doctor_name": "Dr. Smith",
        "notes": "Routine checkup"
    }
    ```

---

### **13. Get All Clinic Visits**
Fetches all clinic visits for a specific pregnancy.

- **Endpoint**: `/get-all-clinic-visit/{id}`
- **Method**: `GET`

---

### **14. Update Clinic Visit**
Updates details of a specific clinic visit.

- **Endpoint**: `/update-clinic-visit/{id}`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "visit_date": "2024-04-15",
        "doctor_name": "Dr. John Doe",
        "notes": "Follow-up checkup"
    }
    ```

---

### **15. Update Default Clinic**
Sets a specific clinic as the default clinic for the user.

- **Endpoint**: `/update-default-clinic`
- **Method**: `POST`
- **Body**:
    ```json
    {
        "pregnancy_clinic_id": 1
    }
    ```

---

### **16. Get All Pregnancy progress**

- **Endpoint**: `/pregnancy/all-progress`
- **Method**: `GET`

---
