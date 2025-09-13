💻 Laptop Request Catalog Item - ServiceNow Project
demo video link - https://github.com/adhirajj2307/Laptop-Request-Catalog-Item-Project.git

📌 Problem Statement Employees in the organization need a quick and efficient way to request laptops for work. The current process is manual, inconsistent, and prone to delays due to a lack of dynamic form behavior and validation. To streamline this, a Service Catalog item is developed in ServiceNow, enabling users to easily request laptops with guided inputs and efficient approval workflows.

📘 Introduction In today’s fast-paced work environment, timely access to laptops is essential for productivity and onboarding. This project introduces a modern, user-friendly self-service interface using ServiceNow's Service Catalog, eliminating the drawbacks of the manual process.

Key Features: ✅ Dynamic form behavior (fields that show/hide based on input) ✅ Field validations and mandatory conditions 🔁 Reset form functionality 📊 Change tracking for governance ⚙️ Support for XML export/import between instances 🛠️ Project Setup Steps 1️⃣ Create Local Update Set Go to System Update Sets > Local Update Sets Click New, name it Laptop Request, submit and click Make Current Ensure all changes are made under this set 2️⃣ Create Service Catalog Item Go to Service Catalog > Maintain Items Click New Fill: Name: Laptop Request Catalog: Service Catalog Category: Hardware Short Description: Use this item to request a new laptop Save the form 3️⃣ Add Variables Go to the related list → Variables → Add:

Variable Type Name Order Laptop Model Single Line Text laptop_model 100 Justification Multi Line Text justification 200 Additional Accessories Checkbox additional_accessories 300 Accessories Details Multi Line Text accessories_details 400 Save the catalog item after adding variables.

4️⃣ Create Catalog UI Policy Go to the Catalog Item → Catalog UI Policies Create Policy: Description: Show Accessories Details Condition: additional_accessories is true In Catalog UI Policy Actions, make accessories_details: Visible ✅ Mandatory ✅ Order: 100 5️⃣ Add UI Action - Reset Button Go to System Definition > UI Actions Create new: Table: sc_cart (Shopping Cart) Action Name: Reset form Client: Checked ✅ Script: function resetForm() { g_form.clearForm(); alert("The form has been reset."); }

6️⃣ Export Update Set Go to your Update Set

Set state to Complete

Export to XML

7️⃣ Import Update Set on Another Instance Open another instance

Go to System Update Sets > Retrieved Update Sets

Import the XML file

Preview and Commit the update set

✅ Testing the Catalog Item Navigate to Service Catalog > Hardware > Laptop Request

Test dynamic behavior:

By default, only 3 variables show

When Additional Accessories is checked → Accessories Details field appears and becomes mandatory

Confirm functionality meets all requirements

📈 Outcome Simplified and standardized laptop request process

Real-time validations and guided form completion

Trackable changes and easily deployable between instances

Improved user experience and IT governance

✅ Conclusion The Laptop Request Catalog Item project successfully modernizes the organization's equipment request process using ServiceNow's Service Catalog. It ensures accuracy, reduces delays, and provides a self-service, dynamic, and user-friendly interface—significantly improving both employee experience and IT efficiency.

📂 Technologies Used ServiceNow Platform

Service Catalog

UI Policies

Catalog Client Scripts

Update Sets (XML)

JavaScript (Client-side)
