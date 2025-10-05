# Tool Shed Sharing Program

## Purpose

We need to track the borrowing and returning of tools in a shared community tool shed, in order to make tool usage efficient, fair, and accountable. Members can browse available tools, check them out, and return them, similar to a public library system.

---

## Data Properties

In this version of the application, we need to keep track of the following data properties. These properties form the shared vocabulary of the system and are reused throughout resources and actions.

* **toolId**

  * **Description:** a unique identifier for each tool stored in the system
  * **Type:** string
  * **Example:** `"TL-1021"`

* **toolName**

  * **Description:** the name of the tool as it would appear to members
  * **Type:** string
  * **Example:** `"Cordless Drill"`

* **toolType**

  * **Description:** the category or classification of the tool (for example, drill, saw, wrench)
  * **Type:** string
  * **Example:** `"Drill"`

* **condition**

  * **Description:** the current state of the tool’s wear or usability
  * **Type:** enum [new, good, worn, broken]
  * **Example:** `"good"`

* **memberId**

  * **Description:** a unique identifier for each registered member
  * **Type:** string
  * **Example:** `"MBR-0473"`

* **memberName**

  * **Description:** the full name of the member
  * **Type:** string
  * **Example:** `"Alex Ramirez"`

* **membershipStatus**

  * **Description:** the current standing of the member account
  * **Type:** enum [active, suspended, expired]
  * **Example:** `"active"`

* **borrowDate**

  * **Description:** the date the member checks out the tool
  * **Type:** date
  * **Example:** `"2025-04-12"`

* **dueDate**

  * **Description:** the date the borrowed tool is expected to be returned
  * **Type:** date
  * **Example:** `"2025-04-19"`

* **returnDate**

  * **Description:** the date the borrowed tool is actually returned
  * **Type:** date
  * **Example:** `"2025-04-18"`

* **isOverdue**

  * **Description:** indicates whether the tool’s return is past the due date
  * **Type:** boolean
  * **Example:** `false`

* **maxBorrowDays**

  * **Description:** the maximum number of days any tool can be borrowed
  * **Type:** number
  * **Example:** `7`

* **depositRequired**

  * **Description:** identifies whether a deposit is required to borrow this tool
  * **Type:** boolean
  * **Example:** `true`

---

## Resources

The following are **resources** or **states** within the system. Each represents a meaningful point in the interaction flow, and each has one or more **actions** available.

* **Home** : The home or landing page of the API. Members typically start here.

  * Actions: [**viewTools**](#viewtools), [**viewMembers**](#viewmembers), [**viewSharings**](#viewsharings)

* **ToolCollection** : Displays a list of all tools in the shed that can be viewed or added.

  * Actions: [**viewTool**](#viewtool), [**addTool**](#addtool)

* **ToolItem** : Shows details for a single tool, including its type, condition, and availability.

  * Actions: [**updateTool**](#updatetool)

* **MemberCollection** : Displays a list of all registered members of the program.

  * Actions: [**viewMember**](#viewmember), [**addMember**](#addmember)

* **MemberItem** : Shows details for a single member, including their current status and borrowing history.

  * Actions: [**updateMember**](#updatemember), [**suspendMember**](#suspendmember), [**activateMember**](#activatemember)

* **SharingCollection** : Displays all current and past tool-borrowing transactions between members and the shed.

  * Actions: [**createSharing**](#createsharing), [**viewSharing**](#viewsharing)

* **SharingItem** : Displays details of a specific borrowing transaction.

  * Actions: [**closeSharing**](#closesharing)

---

## Actions

Each action has zero or more input properties, always returns a single resource, and is marked with its type: Safe (read), Unsafe (create), Idempotent (update), or Delete (remove).

---

### [viewTools](#viewtools)

Use this action to display the list of all tools available in the system.

* **Inputs:** none
* **Returns:** **ToolCollection**
* **Type:** Safe

---

### [viewMembers](#viewmembers)

Use this action to display all registered members in the system.

* **Inputs:** none
* **Returns:** **MemberCollection**
* **Type:** Safe

---

### [viewSharings](#viewsharings)

Use this action to display all borrowing records (open or closed).

* **Inputs:** none
* **Returns:** **SharingCollection**
* **Type:** Safe

---

### [addTool](#addtool)

Use this action to add a new tool record to the collection.

* **Inputs:** toolName (`"Cordless Drill"`), toolType (`"Drill"`), condition (`"new"`)
* **Required:** toolName, toolType, condition
* **Returns:** **ToolItem**
* **Type:** Unsafe

---

### [viewTool](#viewtool)

Use this action to view details of a single tool.

* **Inputs:** toolId (`"TL-1021"`)
* **Required:** toolId
* **Returns:** **ToolItem**
* **Type:** Safe

---

### [updateTool](#updatetool)

Use this action to change the details of an existing tool (for example, update its condition).

* **Inputs:** toolId (`"TL-1021"`), condition (`"worn"`)
* **Required:** toolId
* **Returns:** **ToolItem**
* **Type:** Idempotent

---

### [addMember](#addmember)

Use this action to register a new member in the system.

* **Inputs:** memberName (`"Alex Ramirez"`)
* **Required:** memberName
* **Returns:** **MemberItem**
* **Type:** Unsafe

---

### [viewMember](#viewmember)

Use this action to retrieve information about a specific member.

* **Inputs:** memberId (`"MBR-0473"`)
* **Required:** memberId
* **Returns:** **MemberItem**
* **Type:** Safe

---

### [updateMember](#updatemember)

Use this action to modify information for an existing member, such as changing their membership status.

* **Inputs:** memberId (`"MBR-0473"`), membershipStatus (`"suspended"`)
* **Required:** memberId
* **Returns:** **MemberItem**
* **Type:** Idempotent

---

### [suspendMember](#suspendmember)

Use this action to suspend a member account (making them temporarily ineligible to borrow tools).

* **Inputs:** memberId (`"MBR-0473"`)
* **Required:** memberId
* **Returns:** **MemberItem**
* **Type:** Idempotent

---

### [activateMember](#activatemember)

Use this action to reactivate a suspended member account.

* **Inputs:** memberId (`"MBR-0473"`)
* **Required:** memberId
* **Returns:** **MemberItem**
* **Type:** Idempotent

---

### [createSharing](#createsharing)

Use this action when a member borrows a tool from the shed. It creates a new sharing record and associates the tool with the borrowing member.

* **Inputs:** memberId (`"MBR-0473"`), toolId (`"TL-1021"`), borrowDate (`"2025-04-12"`), dueDate (`"2025-04-19"`)
* **Required:** memberId, toolId, borrowDate, dueDate
* **Returns:** **SharingItem**
* **Type:** Unsafe
* **Rules:** [MemberMustBeActive](#membermustbeactive), [ToolMustBeAvailable](#toolmustbeavailable)

---

### [viewSharing](#viewsharing)

Use this action to retrieve a specific sharing record by its identifier.

* **Inputs:** sharingId (`"SHR-0015"`)
* **Required:** sharingId
* **Returns:** **SharingItem**
* **Type:** Safe

---

### [closeSharing](#closesharing)

Use this action when a member returns a borrowed tool, closing the transaction.

* **Inputs:** sharingId (`"SHR-0015"`), returnDate (`"2025-04-18"`)
* **Required:** sharingId, returnDate
* **Returns:** **SharingItem**
* **Type:** Idempotent
* **Rules:** [ToolConditionUpdateRequired](#toolconditionupdaterequired)

---

## Rules

* **[MemberMustBeActive](#membermustbeactive)** :

  A tool may only be borrowed by a member whose `membershipStatus` is **active**.

* **[ToolMustBeAvailable](#toolmustbeavailable)** :

  A tool can only be borrowed if it is not currently part of an open sharing record.

* **[ToolConditionUpdateRequired](#toolconditionupdaterequired)** :

  When a sharing record is closed, the tool’s condition must be reviewed and updated before it can be borrowed again.

---

## Design Notes

This story models tool sharing as a series of **resources and transitions**, not endpoints. Each action expresses an intent (view, add, update, borrow, return), and the system’s constraints ensure fairness and data consistency. Rules maintain operational integrity by enforcing member status and tool availability, while structured property definitions now make this story both **human-readable** and **machine-transformable**.

