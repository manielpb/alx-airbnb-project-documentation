# Backend Requirement Specifications - AirBnB Project

This document describes backend requirements for three main features:  
1. User Authentication  
2. Property Management  
3. Booking System  

1. User Authentication
   Endpoints:
    `POST /auth/register` -> Register new users  
    `POST /auth/login` -> Login users  

- Inputs: email, password, name, role (guest/host)  
- Outputs: user info + JWT token  
- Validation: unique email, password ≥ 8 chars  
- Performance: handle 1000+ login requests under 300ms  

---

2. Property Management
    Endpoints:
      `POST /properties` -> Create property  
      `GET /properties/:id` -> Fetch property  
      `PUT /properties/:id` -> Update property  
      `DELETE /properties/:id` -> Delete property  

- Inputs: host_id, name, description, location, price_per_night  
- Validation: only hosts can add properties, price > 0  
- Performance: queries respond < 200ms  

3. Booking System
    Endpoints:
      `POST /bookings` -> Create booking  
       `GET /bookings/:id` -> Fetch booking  
      `PUT /bookings/:id/cancel` -> Cancel booking  

- Inputs:property_id, user_id, start_date, end_date  
- Validation: no double booking, end_date > start_date  
- Performance:create booking in < 400ms  

