
# Event Management System

Evento is a comprehensive event management system designed as part of our final year group project to simplify campus event planning, registration, and ticket booking. Developed using the MERN stack (MongoDB, Express.js, React.js, Node.js) and following Agile Scrum methodology, this system prioritizes an intuitive user interface and seamless user experience.

## **Key Features**

- **Schedule Events**: Create and manage events with ease.
- **Event Calendar**: View upcoming events on an interactive calendar.
- **Approval Workflow**: Request and track event approvals.
- **Ticket Booking**: Reserve tickets effortlessly with online booking.
- **QR Code Generation**: Generate and scan QR codes for ticket verification.

## **Technologies Used**

- **Frontend**: React.js
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Utilities**: NPM, JWT Web Token, QR Code Generation

## **Skills Demonstrated**

- User Interface Design
- Requirements Analysis
- Agile Development
- MongoDB, Express.js, React.js, Node.js
- UI/UX Design using Figma

## **Getting Started**

### **Prerequisites**

Before you begin, ensure you have the following installed:

- **Node.js** (includes npm)
- **MongoDB**

### **Installation Steps**

1. **Clone the Repository**
   ```bash
   git clone 

2. **Navigate to Project Directories**
   Open two terminals for the frontend and backend, respectively:
   - **Frontend**:
     ```bash
     cd ems/client
     ```
   - **Backend**:
     ```bash
     cd ems/api
     ```

3. **Install Dependencies**
   Run the following command in both `client` and `api` directories:
   ```bash
   npm install
   ```
   
4. **Set Up Environment Variables Create a .env file in the api directory with the following content:**
   ```bash
   MONGODB_URI=mongodb://localhost/your-database-name
   JWT_SECRET=your-secret-key
   PORT=4000
   ```

5. **Start the Backend Server**
   ```bash
   nodemon start
   ```

6. **Start the Frontend**
   ```bash
   npm strt
   ```

7. **Access the Application**

  Frontend: http://localhost:5173
  Backend: http://localhost:4000


## Project Structure

```bash
Event-Management-System/
|-- ems/client          # Frontend files
|-- ems/api             # Backend files
|-- .env                # Environment variables file
|-- README.md           # Documentation
```

<h1>Thank You</h1>

