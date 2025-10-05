Perfect — inline anchors are the connective tissue that make an API Story navigable while keeping it readable as a single Markdown file.

Below is your **Tool Shed Sharing Program** in the **Classic Story Format with anchors**. Every resource and action name is linkable, following the standard convention (`[ActionName](#actionname)`).

---

# Tool Shed Sharing Program

## Purpose

We need to track the borrowing and returning of tools in a shared community tool shed, in order to make tool usage efficient, fair, and accountable. Members can browse available tools, check them out, and return them, similar to a public library system.

---

## Data Properties

In this first version of the application, we need to keep track of the following data properties. These properties form the shared vocabulary of the system and are reused throughout resources and actions.

* **toolId** : a unique identifier for each tool stored in the system [string]
* **toolName** : the name of the tool as it would appear to members [string]
* **toolType** : the category or classification of the tool (for example, drill, saw, wrench) [string]
* **condition** : the current state of the tool’s wear or usability [enumerated string: new, good, worn, broken]
* **memberId** : a unique identifier for each registered member [string]
* **memberName** : the full name of the member [string]
* **membershipStatus** : the current standing of the member account [enumerated string: active, suspended, expired]
* **borrowDate** : the date the member checks out the tool [date]
* **dueDate** : the date the borrowed tool is expected to be returned [date]
* **returnDate** : the date the borrowed tool is actually returned [date]
* **isOverdue** : indicates whether the tool’s return is past the due date [boolean]
* **maxBorrowDays** : the maximum number of days any tool can be borrowed [number]
* **depositRequired** : identifies whether a deposit is required to borrow this tool [boolean]

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

This version of the application supports the following operations. Each action has zero or more input properties, always returns a single resource, and is marked with its type: Safe (read), Unsafe (create), Idempotent (update), or Delete (remove).

---

### [viewTools](#viewtools)

Use this action to display the list of all tools available in the system.

*Inputs:* none
*Returns:* **ToolCollection**
*Type:* Safe

---

### [viewMembers](#viewmembers)

Use this action to display all registered members in the system.

*Inputs:* none
*Returns:* **MemberCollection**
*Type:* Safe

---

### [viewSharings](#viewsharings)

Use this action to display all borrowing records (open or closed).

*Inputs:* none
*Returns:* **SharingCollection**
*Type:* Safe

---

### [addTool](#addtool)

Use this action to add a new tool record to the collection.

*Inputs:* toolName, toolType, condition
*Required:* toolName, toolType, condition
*Returns:* **ToolItem**
*Type:* Unsafe

---

### [viewTool](#viewtool)

Use this action to view details of a single tool.

*Inputs:* toolId
*Required:* toolId
*Returns:* **ToolItem**
*Type:* Safe

---

### [updateTool](#updatetool)

Use this action to change the details of an existing tool (for example, update its condition).

*Inputs:* toolId, condition
*Required:* toolId
*Returns:* **ToolItem**
*Type:* Idempotent

---

### [addMember](#addmember)

Use this action to register a new member in the system.

*Inputs:* memberName
*Required:* memberName
*Returns:* **MemberItem**
*Type:* Unsafe

---

### [viewMember](#viewmember)

Use this action to retrieve information about a specific member.

*Inputs:* memberId
*Required:* memberId
*Returns:* **MemberItem**
*Type:* Safe

---

### [updateMember](#updatemember)

Use this action to modify information for an existing member, such as changing their membership status.

*Inputs:* memberId, membershipStatus
*Required:* memberId
*Returns:* **MemberItem**
*Type:* Idempotent

---

### [suspendMember](#suspendmember)

Use this action to suspend a member account (making them temporarily ineligible to borrow tools).

*Inputs:* memberId
*Required:* memberId
*Returns:* **MemberItem**
*Type:* Idempotent

---

### [activateMember](#activatemember)

Use this action to reactivate a suspended member account.

*Inputs:* memberId
*Required:* memberId
*Returns:* **MemberItem**
*Type:* Idempotent

---

### [createSharing](#createsharing)

Use this action when a member borrows a tool from the shed. It creates a new sharing record and associates the tool with the borrowing member.

*Inputs:* memberId, toolId, borrowDate, dueDate
*Required:* memberId, toolId, borrowDate, dueDate
*Returns:* **SharingItem**
*Type:* Unsafe
*Rules:* [MemberMustBeActive](#membermustbeactive), [ToolMustBeAvailable](#toolmustbeavailable)

---

### [viewSharing](#viewsharing)

Use this action to retrieve a specific sharing record by its identifier.

*Inputs:* sharingId
*Required:* sharingId
*Returns:* **SharingItem**
*Type:* Safe

---

### [closeSharing](#closesharing)

Use this action when a member returns a borrowed tool, closing the transaction.

*Inputs:* sharingId, returnDate
*Required:* sharingId, returnDate
*Returns:* **SharingItem**
*Type:* Idempotent
*Rules:* [ToolConditionUpdateRequired](#toolconditionupdaterequired)

---

## Rules

The following rules apply to specific actions in the system.

* **[MemberMustBeActive](#membermustbeactive)** : A tool may only be borrowed by a member whose `membershipStatus` is **active**.
* **[ToolMustBeAvailable](#toolmustbeavailable)** : A tool can only be borrowed if it is not currently part of an open sharing record.
* **[ToolConditionUpdateRequired](#toolconditionupdaterequired)** : When a sharing record is closed, the tool’s condition must be reviewed and updated before it can be borrowed again.

---

## Design Notes

This story models tool sharing as a series of states rather than endpoints. Each action transitions between resources (for example, from a collection to an item), preserving a narrative of intent. The system enforces borrowing constraints through rules, ensuring that only active members borrow available tools, and that all tools are re-evaluated upon return.


