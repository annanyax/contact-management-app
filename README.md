# Contact Management App

This is a simple **Contact Management App** built using **Vue 3**. It allows users to manage their contacts by:
- Viewing a list of predefined contacts.
- Adding new contacts.
- Searching contacts in real time.

The app uses basic features of Vue 3 with Composition API and component-based architecture.

---

## **Final Output**
![Final Output](./src/image/cmapp.png)

---

## **Features**
1. **View Contacts**: Displays a list of contacts.
2. **Add Contacts**: Allows users to add new contacts with a name and phone number.
3. **Search Contacts**: Dynamically filters contacts in real time as you type in the search bar.
4. **LocalStorage Integration**: Contacts are stored in the browser's `localStorage` for persistence.

---

## **Technologies Used**
- **Vue 3**: For building the frontend.
- **HTML/CSS**: For structuring and styling.
- **JavaScript**: For interactive behavior.
- **LocalStorage**: For saving and retrieving contact data.

---

## **How to Run This Project**

### **Step 1: Clone or Download the Repository**
#### Option 1: Clone the Repository
1. Open a terminal and run: 
git clone https://github.com/annanyax/contact-management-app.git
2. Navigate to the project folder:
cd contact-management-app

#### Option 2: Download as a ZIP File
1. Go to the GitHub repository in your browser.
2. Click on the green "Code" button and select "Download ZIP".
3. Extract the ZIP file and open the extracted folder.

### **Step 2: Install Dependencies**
1. Ensure you have Node.js and npm installed on your computer.
2. Open the project folder in your terminal and run:
npm install

### **Step 3: Start the Development Server**
1. Start the app locally by running:
npm run dev
2. Open the URL provided in the terminal (e.g., http://localhost:5173) in your browser to view the app.


### **File Descriptions**
1. **App.vue**:
   - The main file that manages the app's state and structure.
2. **AppHeader.vue**:
   - Contains the app's title and search functionality.
3. **ContactList.vue**:
   - Displays the contact list dynamically based on the search query.
4. **AddContactForm.vue**:
   - Provides the form to add new contacts to the list.
