----------------------------Day 1-Completed-----------------------------------------------

Created a Salesforce Lightning App: My Recruitment App
Added custom objects: Company & Job Application
Added tabs and sample data
Repo created to document daily progress

----------------------------Day 2-Completed-----------------------------------------------

Added custom fields on Company object (Industry, Company Size, Website, Headquarters)
Added custom fields on Job Application object (Position Title, Status, Expected Salary, Notes, Interview Date)
Created lookup relationship (Job Application → Company)
Designed clean page layouts with proper sections
Updated page layouts for both objects
Added sample records and tested relationships

----------------------------Day 3-Completed-----------------------------------------------

Day 3 – Data Validation + Controls

Added validation rules on Job Application:
Interview date cannot be in the past
Expected salary must be greater than zero
Position required when Status = Interviewing
Marked important business fields as Required
Created multiple List Views for Job Applications (Applied, Interviewing, Offered, Rejected)
Filtered records to validate data quality

----------------------------Day 4-Completed-----------------------------------------------

Day 4 – Job Application Workflow & User Experience Enhancements

On Day 4, I focused on improving the Job Application workflow by enhancing usability, enforcing data quality, and guiding users through a structured hiring process.

1. Page Layout Optimization
Cleaned and reorganized page layouts for both Company and Job Application objects.
Grouped fields into meaningful sections such as:
Job Details
Compensation
Interview
Notes
Removed unnecessary system fields from the main view to improve readability and user focus.
2. Validation Rules for Data Integrity
Implemented validation rules to ensure correct data entry:

Prevented status progression to "Interviewing" unless Interview Date is filled.
Made Company selection mandatory to avoid orphan Job Applications. These rules simulate real-world business constraints commonly used in recruitment systems.

3. Salesforce Path Implementation
Configured Salesforce Path on the Job Application object using the Status picklist.
Defined stages: Applied → Interviewing → Offered → Rejected.
Added Guidance for Success at each stage to assist users in understanding next actions.

---path-Salesforce Path Implementation----

Alternative – Assign Permission Set (Safer Option)

If you should NOT be full admin:

Go to Setup

Search Permission Sets

Click New

Label: App Customization Access

Save

Open the Permission Set

Click System Permissions

Click Edit

Enable:

✅ Customize Application

Save

Assign Permission Set

Open the Permission Set

Click Manage Assignments

Click Add Assignments
Select your user

Click Assign

4. Celebration & User Feedback
Enabled Celebration for the final stage (Offered) to enhance user experience.
This provides visual feedback and improves adoption for business users.

5. Kanban View for Recruiter Workflow
Used Kanban view to visualize Job Applications by Status.
Enabled drag-and-drop status updates, simulating how recruiters track candidates in real time.

----------------------------Day 5-Completed-----------------------------------------------

Day 5 – Automating Recruitment Workflow with Salesforce Flow
Created a Record-Triggered Flow on the Job Application object to automate status updates and reduce manual recruiter work.

Automation Logic
Flow Type: Record-Triggered Flow (After Save)
Trigger: Job Application record is created or updated
Entry Conditions:
Interview Date is NOT null
Status is NOT equal to "Interviewing"
Flow runs only when record is updated to meet conditions

----------------------------Day 6-Completed-----------------------------------------------

Day 6 – Salesforce Flow Automation (Recruitment Workflow)
Implemented a production-style record-triggered Flow to automate Job Application status transitions based on real recruitment events.

What was done
Built a Record-Triggered Flow on the Job Application object
Configured selective entry conditions so the flow runs only when:
Interview Date is added, or
Offer Date is added
Used Decision elements to control valid status transitions:
Applied → Interviewing (when Interview Date is populated)
Interviewing → Offered (when Offer Date is populated)
Ensured the flow exits safely when conditions are not met
Prevented unnecessary executions and infinite loops by validating current status
Why this matters
This automation removes manual dependency on recruiters to update application status, improves data accuracy, and reflects a real-world recruitment lifecycle instead of demo-level automation.

Key learning
Effective Salesforce automation should be event-driven, selective, and controlled. Status changes should be driven by meaningful business actions, not by every record edit.
