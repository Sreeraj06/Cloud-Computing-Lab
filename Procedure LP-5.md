# TECHNICAL PROCEDURE: IMPLEMENTING REUSABLE APEX EMAIL SERVICE

## 1. OBJECTIVE
To establish a centralized, reusable, and secure Apex utility class for programmatically sending HTML or plain-text email notifications within the Salesforce platform.

## 2. PREREQUISITES
* Salesforce Permissions: System Administrator profile or a custom profile/permission set with the "Author Apex" permission.
* Deliverability Settings: The organization's Email Deliverability must be configured to "All Email" to allow outbound programmatic messages.

## 3. IMPLEMENTATION STEPS

### Step 3.1: Create the Apex Utility Class
1. Navigate to the top right corner of the Salesforce interface and click the Gear Icon (Setup).
2. Click Developer Console from the dropdown options.
3. In the Developer Console menu bar, select File > New > Apex Class.
4. Enter 'EmailService' as the class name and click OK.
5. Replace the default boilerplate structure by copying and pasting the full execution source code provided in the technical repository.
6. Commit the code to the platform metadata by executing the save command (Ctrl + S on Windows / Cmd + S on Mac). Verify that no compilation or syntax errors appear in the Problems tab.

### Step 3.2: Verify Outbound Deliverability (Sandbox Check)
1. Close the Developer Console tab and return to the main Salesforce Setup interface.
2. In the Quick Find search box on the left, type 'Deliverability'.
3. Under the Email section, select Deliverability.
4. Locate the Access level dropdown menu under the Access to Send Email section.
5. Ensure the value is set to 'All email'. If it is set to 'No email' or 'System email only', alter it to 'All email' and click Save.

### Step 3.3: Execute Functional Integration Testing
1. Return to the Developer Console window.
2. Navigate to the top menu bar, select Debug, and click Open Execute Anonymous Window.
3. Clear any preexisting scripts from the text field.
4. Input the test script, replacing the placeholder parameter with a valid, accessible external target email address.
5. Select the Open Log option checkbox located at the bottom of the dialogue window.
6. Click the Execute button to initiate the transaction thread.

### Step 3.4: Validate Execution Logs and Output
1. Once execution finishes, inspect the execution log file that opens automatically.
2. Apply the Debug Only filter constraint located at the base of the log interface viewer.
3. Confirm the appearance of the confirmation string: USER_DEBUG | [Line...] | DEBUG | Email sent successfully.
4. Log into the external recipient mailbox used during Step 3.3 and check both the Inbox and Spam folders to verify physical receipt of the test transmission.
