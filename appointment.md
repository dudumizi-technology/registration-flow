### Description: Creating appointment
---

Endpoint: `/api/appointments/create`

Method: `POST`

request body:
```json
{
    "date": "",
    "time": "",
    "duration": "",
    "doctor_id": "",
    "department_id": "",
    "tenant_id": "",
    "location": "",
    "description": "",
    "amount": "",
    "consultation_type": ""
}
```

`date` normal date as "2024-01-01"

`time` time in AM or PM format

`duration` = 0 // recently is not used

`doctor_id` = int as doctor id

`department_id` department of doctor, it comes from the API of fetching doctors

`tenant_id` the same it comes from the doctor i.e id of hospital

`location` = "location"

`description` = "Appointment with Dr X"

`amount` = 0

`consultation_type` = 1

### Description: Getting appointment
---

Endpoint: `/api/appointments/all`

Method: `GET`

Response body:

```json
{
  "appointments": [
    {
      "id": 54,
      "patient_id": 24, //
      "department_id": 9,
      "opd_date": "2024-09-09 01:00:00",
      "is_completed": 0,
      "appointment_type": 1, //	1 for onsite, 2 for home visit
      "visit_address": "Dar es salaam",
      "time": "1:00 PM",
      "status": 0, //0 not confirmed and 1 as confirmed, 3 as cancelled	
      "created_at": null,
      "updated_at": null,
      "doctor_id": 25,
      "specialist": "8",
      "doctor_name": "Rajabu",
      "doctor_avatar": null,
      "doctor_specialities": "ENT",
      "hospital_name": "Tanzmed Africa"
    }
    ...
  ],
  "liveconsultation": []
}
```


### Description: Update appointment
---

Endpoint: `/api/appointments/update`

Method: `POST`

request body:
```json
{
    "date": "", // as above
    "time": "", // as above
    "status": "", //0 not confirmed and 1 as confirmed, 3 as cancelled	
    "id": "", // required - id of appointment
    "consultation_type": "" // required - 1 for onsite, 2 for home visit
}
```

