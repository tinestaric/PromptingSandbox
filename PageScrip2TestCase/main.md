Convert the provided page scripting recording in YAML format from Business Central into a structured and understandable Test Case.

- Analyze the YAML structure to extract necessary details for a Test Case.
- Transform the information into a human-readable format.
- Ensure the Test Case covers all steps and interactions as recorded in the YAML.
- Use clear language and include any necessary steps for setup, execution, and verification.

# Steps

1. **Parse the YAML:** Identify and extract key components and actions from the YAML file, such as fields, inputs, and outcomes.
2. **Identify Objectives:** Determine the main objectives and purpose of the page recording to create relevant test scenarios.
3. **Create Test Steps:** 
   - Write clear and sequential steps based on the actions extracted from the YAML.
   - Include any setup or prerequisites required for the test.
4. **Define Expected Results:** Specify expected outcomes for each action or step based on the recording details.
5. **Format Test Case:** Arrange the extracted information into a standard Test Case format, typically including Title, Preconditions, Steps, and Expected Results.

# Output Format

Each Test Case should be presented in a structured format with the following sections:
- **Title:** A clear, concise name for the Test Case.
- **Test Steps:** Numbered list of actions to take, extracted from the YAML.

# Examples
**Example 1**
**Input:**
```yaml
name: Recording
description: Test recording
start:
  profile: BUSINESS MANAGER
steps:
  - type: navigate
    target:
      - page: Item List
    description: Navigate to Items
  - type: page-shown
    source:
      page: Item List
    modal: false
    runtimeId: b69m
    description: Page <caption>Items</caption> was shown.
  - type: invoke
    target:
      - page: Item List
        runtimeRef: b69m
      - action: Control_New
    invokeType: New
    description: Invoke New on <caption>New</caption>
  - type: page-shown
    source:
      page: Select Item Templ. List
    modal: true
    runtimeId: b6om
    description: Page <caption>Select a template for a new item</caption> was shown.
  - type: invoke
    target:
      - page: Select Item Templ. List
        runtimeRef: b6om
    invokeType: LookupOk
    description: Invoke LookupOk on <caption>Select a template for a new item</caption>
  - type: page-closed
    source:
      page: Select Item Templ. List
    runtimeId: b6om
    description: Page <caption>Select a template for a new item</caption> was closed.
  - type: page-shown
    source:
      page: Item Card
    modal: false
    runtimeId: b6pj
    description: Page <caption>New - Item Card</caption> was shown.
  - type: input
    target:
      - page: Item Card
        runtimeRef: b6pj
      - field: Description
    value: Table
    description: Input <value>Table</value> into <caption>Description</caption>
  - type: input
    target:
      - page: Item Card
        runtimeRef: b6pj
      - field: Unit Cost
    value: "15.00"
    description: Input <value>15.00</value> into <caption>Unit Cost</caption>
  - type: input
    target:
      - page: Item Card
        runtimeRef: b6pj
      - field: Unit Price
    value: "18.00"
    description: Input <value>18.00</value> into <caption>Unit Price</caption>
  - type: navigate
    target:
      - page: Item Journal
    description: Navigate to Item Journals
  - type: page-shown
    source:
      page: Item Journal
    modal: false
    runtimeId: b71e
    description: Page <caption>Item Journals</caption> was shown.
  - type: focus
    target:
      - page: Item Journal
        runtimeRef: b71e
      - repeater: Control1
      - field: Posting Date
    description: Focus <caption>Posting Date</caption>
  - type: input
    target:
      - page: Item Journal
        runtimeRef: b71e
      - repeater: Control1
      - field: Item No.
    value: ""
    isFilterAsYouType: true
    description: Input <value></value> into <caption>Item No.</caption>
  - type: focus
    target:
      - page: Item Journal
        runtimeRef: b71e
      - repeater: Control1
      - field: Item No.
    description: Focus <caption>Item No.</caption>
  - type: page-shown
    source:
      page: lookup:Item No.
    modal: false
    runtimeId: b79j
    description: Page <caption>Select</caption> was shown.
  - type: input
    target:
      - page: Item Journal
        runtimeRef: b71e
      - repeater: Control1
      - field: Item No.
    value: "1010"
    isFilterAsYouType: true
    description: Input <value>1010</value> into <caption>Item No.</caption>
  - type: invoke
    target:
      - page: lookup:Item No.
        runtimeRef: b79j
      - repeater: repeater
    parameters:
      AlwaysCommit: true
    description: Invoke row on <caption>Item</caption>
  - type: page-closed
    source:
      page: lookup:Item No.
    runtimeId: b79j
    description: Page <caption>Select</caption> was closed.
  - type: focus
    target:
      - page: Item Journal
        runtimeRef: b71e
      - repeater: Control1
      - field: Item No.
    description: Focus <caption>Item No.</caption>
  - type: focus
    target:
      - page: Item Journal
        runtimeRef: b71e
      - repeater: Control1
      - field: Quantity
    description: Focus <caption>Quantity</caption>
  - type: input
    target:
      - page: Item Journal
        runtimeRef: b71e
      - repeater: Control1
      - field: Quantity
    value: "50"
    description: Input <value>50</value> into <caption>Quantity</caption>
  - type: focus
    target:
      - page: Item Journal
        runtimeRef: b71e
      - field: null
        automationId: fb8cccf3-54ac-4d77-9ad8-136cec25583a
        caption: null
    description: Focus <caption>null</caption>
  - type: invoke
    target:
      - page: Item Journal
        runtimeRef: b71e
      - action: Post
    parameters: {}
    description: Invoke <caption>Post</caption>
  - type: page-shown
    source:
      page: null
      automationId: 8da61efd-0002-0003-0507-0b0d1113171d
      caption: Confirm
    modal: true
    runtimeId: b7a8
    description: Page <caption>Confirm</caption> was shown.
  - type: invoke
    target:
      - page: null
        automationId: 8da61efd-0002-0003-0507-0b0d1113171d
        caption: Confirm
        runtimeRef: b7a8
    invokeType: Yes
    description: Invoke Yes on <caption>Confirm</caption>
  - type: page-closed
    source:
      page: null
    runtimeId: b7a8
    description: Page <caption>Confirm</caption> was closed.
  - type: message
    automationId: 8da61efd-0002-0003-0507-0b0d1113171d
    text: The journal lines were successfully posted.
    description: "Message: <value>The journal lines were successfully posted.</value>"
  - type: navigate
    target:
      - page: Item List
    description: Navigate to Items
  - type: page-shown
    source:
      page: Item List
    modal: false
    runtimeId: b7as
    description: Page <caption>Items</caption> was shown.
  - type: set-current-row
    target:
      - page: Item List
        runtimeRef: b7as
      - repeater: Control1
    targetRecord:
      relative: 7
    description: Set current row in <caption>Item</caption>
  - type: invoke
    target:
      - page: Item List
        runtimeRef: b7as
      - repeater: Control1
    invokeType: Edit
    parameters:
      AlwaysCommit: false
    description: Invoke row on <caption>Item</caption>
  - type: page-shown
    source:
      page: Item Card
    modal: false
    runtimeId: b7ps
    description: Page <caption>Item Card</caption> was shown.
```

**Output:**
Create Item
1.	Navigate to Items. Item list opened.
2.	Click on + New.Templates card opened.
3.	Select template ITEM and press OK. Item card opened.
4.	Enter „Table“ in Description field. Description field has been filled.
5.	Enter 15,00 in Unit Cost. Unit Cost entered.
6.	Enter 18,00 in Unit Price. Unit Price entered.
7.	Navigate to Item Journals. Item Journal opened.
8.	Enter current item No. in Item No. column.  Item no. entered
9.	Enter 50 in Quantity column. Quantity entered.
10.	Click Post. Question notification pop-up.
11.	Press Yes. Notification pop-up.
12.	Press OK. Navigate to Items. Item list opened.
13.	Open Item with Description Table. Item card opened.
**Example 2**
**Inputs**
```yaml
name: Recording
description: Test recording
start:
  profile: BUSINESS MANAGER
steps:
  - type: navigate
    target:
      - page: Purchase Order List
    description: Navigate to Purchase Orders
  - type: page-shown
    source:
      page: Purchase Order List
    modal: false
    runtimeId: bm1
    description: Page <caption>Purchase Orders</caption> was shown.
  - type: invoke
    target:
      - page: Purchase Order List
        runtimeRef: bm1
      - action: Control_New
    invokeType: New
    description: Invoke New on <caption>New</caption>
  - type: page-shown
    source:
      page: Purchase Order
    modal: false
    runtimeId: btv
    description: Page <caption>New - Purchase Order</caption> was shown.
  - type: focus
    target:
      - page: Purchase Order
        runtimeRef: btv
      - field: Buy-from Vendor Name
    description: Focus <caption>Vendor Name</caption>
  - type: focus
    target:
      - page: Purchase Order
        runtimeRef: btv
      - field: Buy-from Vendor No.
    description: Focus <caption>Vendor No.</caption>
  - type: invoke
    target:
      - page: Purchase Order
        runtimeRef: btv
      - field: Buy-from Vendor No.
    invokeType: Lookup
    description: Invoke Lookup on <caption>Vendor No.</caption>
  - type: page-shown
    source:
      page: lookup:Buy-from Vendor No.
    modal: false
    runtimeId: b1ge
    description: Page <caption>Select</caption> was shown.
  - type: invoke
    target:
      - page: lookup:Buy-from Vendor No.
        runtimeRef: b1ge
      - repeater: repeater
    parameters:
      AlwaysCommit: true
    description: Invoke row on <caption>Vendor</caption>
  - type: page-closed
    source:
      page: lookup:Buy-from Vendor No.
    runtimeId: b1ge
    description: Page <caption>Select</caption> was closed.
  - type: input
    target:
      - page: Purchase Order
        runtimeRef: btv
      - field: Vendor Invoice No.
    value: INV20241205_2
    description: Input <value>INV20241205_2</value> into <caption>Vendor Invoice
      No.</caption>
  - type: input
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: No.
    value: ""
    isFilterAsYouType: true
    description: Input <value></value> into <caption>No.</caption>
  - type: focus
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: No.
    description: Focus <caption>No.</caption>
  - type: page-shown
    source:
      page: lookup:No.
    modal: false
    runtimeId: b1ho
    description: Page <caption>Select</caption> was shown.
  - type: input
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: No.
    value: "1908"
    isFilterAsYouType: true
    description: Input <value>1908</value> into <caption>No.</caption>
  - type: input
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: No.
    value: 1908-
    isFilterAsYouType: true
    description: Input <value>1908-</value> into <caption>No.</caption>
  - type: input
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: No.
    value: 1908-s
    isFilterAsYouType: true
    description: Input <value>1908-s</value> into <caption>No.</caption>
  - type: invoke
    target:
      - page: lookup:No.
        runtimeRef: b1ho
      - repeater: repeater
    parameters:
      AlwaysCommit: true
    description: Invoke row on <caption>Item</caption>
  - type: page-closed
    source:
      page: lookup:No.
    runtimeId: b1ho
    description: Page <caption>Select</caption> was closed.
  - type: input
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: Quantity
    value: "2"
    description: Input <value>2</value> into <caption>Quantity</caption>
  - type: focus
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
    description: Focus <caption>Lines</caption>
  - type: set-current-row
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
    targetRecord:
      relative: 1
    description: Set current row in <caption>Control1</caption>
  - type: invoke
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: No.
    invokeType: Lookup
    description: Invoke Lookup on <caption>No.</caption>
  - type: page-shown
    source:
      page: lookup:No.
    modal: false
    runtimeId: b1id
    description: Page <caption>Select</caption> was shown.
  - type: set-current-row
    target:
      - page: lookup:No.
        runtimeRef: b1id
      - repeater: repeater
    targetRecord:
      relative: 11
    description: Set current row in <caption>Item</caption>
  - type: invoke
    target:
      - page: lookup:No.
        runtimeRef: b1id
      - repeater: repeater
    parameters:
      AlwaysCommit: true
    description: Invoke row on <caption>Item</caption>
  - type: page-closed
    source:
      page: lookup:No.
    runtimeId: b1id
    description: Page <caption>Select</caption> was closed.
  - type: input
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
      - page: Purchase Order Subform
      - repeater: Control1
      - field: Quantity
    value: "4"
    description: Input <value>4</value> into <caption>Quantity</caption>
  - type: focus
    target:
      - page: Purchase Order
        runtimeRef: btv
      - part: PurchLines
    description: Focus <caption>Lines</caption>
  - type: invoke
    target:
      - page: Purchase Order
        runtimeRef: btv
      - action: Release
    parameters: {}
    description: Invoke <caption>Release</caption>
  - type: invoke
    target:
      - page: Purchase Order
        runtimeRef: btv
      - action: Post
    parameters: {}
    description: Invoke <caption>Post...</caption>
  - type: page-shown
    source:
      page: null
      automationId: 8da61efd-0002-0003-0507-0b0d1113171d
      caption: Choose
    modal: true
    runtimeId: b1j2
    description: Page <caption>Choose</caption> was shown.
  - type: invoke
    target:
      - page: null
        automationId: 8da61efd-0002-0003-0507-0b0d1113171d
        caption: Choose
        runtimeRef: b1j2
    invokeType: Ok
    description: Invoke Ok on <caption>Choose</caption>
  - type: page-closed
    source:
      page: null
    runtimeId: b1j2
    description: Page <caption>Choose</caption> was closed.
  - type: page-shown
    source:
      page: null
      automationId: 8da61efd-0002-0003-0507-0b0d1113171d
      caption: Confirm
    modal: true
    runtimeId: b1j8
    description: Page <caption>Confirm</caption> was shown.
  - type: invoke
    target:
      - page: null
        automationId: 8da61efd-0002-0003-0507-0b0d1113171d
        caption: Confirm
        runtimeRef: b1j8
    invokeType: Yes
    description: Invoke Yes on <caption>Confirm</caption>
  - type: page-closed
    source:
      page: null
    runtimeId: b1j8
    description: Page <caption>Confirm</caption> was closed.
  - type: page-closed
    source:
      page: Purchase Order
    runtimeId: btv
    description: Page <caption>New - Purchase Order - 106026 ∙ Fabrikam,
      Inc.</caption> was closed.
  - type: page-shown
    source:
      page: Posted Purchase Invoice
    modal: false
    runtimeId: b1ji
    description: Page <caption>Posted Purchase Invoice - 108006 ∙ Fabrikam,
      Inc.</caption> was shown.
```
**Outputs**
1.	Navigate to Purchase Orders. Purchase Order list opened.
2.	Click on + New. New Purchase Order card opened.
3.	Click on the arrow on the „Vendor No“ field. Vendor dropdown list opened. 
4.	Select Vendor Fabrikam. Vendor Fabrikam selected, additional information from Vendor card has been applied on other Purchase Order fields.
5.	Enter „INV2024125_1“ in Vendor Invoice No. field. Vendor Invoice no. was filled.
6.	Enter item „1908-S“. In No. column. Item 1908-S added.
7.	On the same line enter „2“ in the Quantity column. Quantity 2 entered. Line Amount recalculated.
8.	On the second line hover to „No.“ column and open dropdown list. Dropdown list opened.
9.	Search for item 1925-W. Select it. Item selected.
10.	On the same line enter „4“ in the „Quantity“ column. Quantity 4 entered. Line Amount recalculated.
11.	Press Release. Document Status changed to Released.
12.	Click on Post.  Notification pop-up.
13.	Select Receive and Invoice. Press OK.  Document Received and Invoiced. Notification pop-up.
14.	On notification message press Yes. Posted Purchase Invoice card opened.

# Notes

- Always ensure the Test Case accurately reflects actions recorded in the YAML.
- Make notes of any assumptions or interpretations made due to ambiguity in the YAML.
- Focus on Description tags in YAML
