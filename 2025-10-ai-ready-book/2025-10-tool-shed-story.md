# Tool Shed Sharing Program

**Purpose:**
Members can borrow tools from the shared tool shed, similar to checking out books from a library.

---

## Properties (Shared Vocabulary)

| Name                 | Type    | Description                                                                                |
| -------------------- | ------- | ------------------------------------------------------------------------------------------ |
| **toolId**           | string  | Unique identifier for each tool in the shed.                                               |
| **toolName**         | string  | The common name of the tool.                                                               |
| **toolType**         | string  | Category or type of the tool (e.g., drill, saw, wrench).                                   |
| **condition**        | enum    | Current condition of the tool. Possible values: `new`, `good`, `worn`, `broken`.           |
| **memberId**         | string  | Unique identifier for each registered member.                                              |
| **memberName**       | string  | The name of the member borrowing or returning a tool.                                      |
| **membershipStatus** | enum    | Current status of the member’s account. Possible values: `active`, `suspended`, `expired`. |
| **borrowDate**       | date    | Date when a member borrows a tool.                                                         |
| **dueDate**          | date    | Expected date when the borrowed tool should be returned.                                   |
| **returnDate**       | date    | Date when the borrowed tool is actually returned.                                          |
| **isOverdue**        | boolean | Indicates whether the tool is overdue for return.                                          |
| **maxBorrowDays**    | number  | Maximum number of days a tool may be borrowed.                                             |
| **depositRequired**  | boolean | Indicates whether the tool requires a refundable deposit.                                  |

---

## Resources

### Home

**Description:** The starting point for the API, offering entry to members and tools.
**Available Actions:**

* `viewTools` → returns **ToolCollection**
* `viewMembers` → returns **MemberCollection**
* `viewSharings` → returns **SharingCollection**

---

### ToolCollection

**Description:** A list of all tools available in the shed.
**Available Actions:**

* `viewTool` → returns **ToolItem**
* `addTool` → returns **ToolItem**

---

### ToolItem

**Description:** Details for a single tool, including condition and availability.
**Available Actions:**

* `updateTool` → returns **ToolItem**

---

### MemberCollection

**Description:** A list of all registered members.
**Available Actions:**

* `viewMember` → returns **MemberItem**
* `addMember` → returns **MemberItem**

---

### MemberItem

**Description:** Details for a single member, including borrowing history and status.
**Available Actions:**

* `updateMember` → returns **MemberItem**
* `suspendMember` → returns **MemberItem**
* `activateMember` → returns **MemberItem**

---

### SharingCollection

**Description:** A record of all borrowing transactions between members and tools.
**Available Actions:**

* `createSharing` → returns **SharingItem**
* `viewSharing` → returns **SharingItem**

---

### SharingItem

**Description:** Details of a single borrowing transaction.
**Available Actions:**

* `closeSharing` → returns **SharingItem**

---

## Actions

### viewTools

Type: **Safe**
**Inputs:** none
**Returns:** ToolCollection

### viewMembers

Type: **Safe**
**Inputs:** none
**Returns:** MemberCollection

### viewSharings

Type: **Safe**
**Inputs:** none
**Returns:** SharingCollection

---

### addTool

Type: **Unsafe**
**Inputs:**

* `toolName` (required)
* `toolType` (required)
* `condition` (required)
  **Returns:** ToolItem

### viewTool

Type: **Safe**
**Inputs:**

* `toolId` (required)
  **Returns:** ToolItem

### updateTool

Type: **Idempotent**
**Inputs:**

* `toolId` (required)
* `condition` (optional)
  **Returns:** ToolItem

---

### addMember

Type: **Unsafe**
**Inputs:**

* `memberName` (required)
  **Returns:** MemberItem

### viewMember

Type: **Safe**
**Inputs:**

* `memberId` (required)
  **Returns:** MemberItem

### updateMember

Type: **Idempotent**
**Inputs:**

* `memberId` (required)
* `membershipStatus` (optional)
  **Returns:** MemberItem

### suspendMember

Type: **Idempotent**
**Inputs:**

* `memberId` (required)
  **Returns:** MemberItem

### activateMember

Type: **Idempotent**
**Inputs:**

* `memberId` (required)
  **Returns:** MemberItem

---

### createSharing

Type: **Unsafe**
**Inputs:**

* `memberId` (required)
* `toolId` (required)
* `borrowDate` (required)
* `dueDate` (required)
  **Returns:** SharingItem
  **Rules:** MemberMustBeActive, ToolMustBeAvailable

### viewSharing

Type: **Safe**
**Inputs:**

* `sharingId` (required)
  **Returns:** SharingItem

### closeSharing

Type: **Idempotent**
**Inputs:**

* `sharingId` (required)
* `returnDate` (required)
  **Returns:** SharingItem
  **Rules:** ToolConditionUpdateRequired

---

## Rules

| Rule                            | Description                                                                                                         |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **MemberMustBeActive**          | A tool may only be borrowed by a member whose membershipStatus is active.                                           |
| **ToolMustBeAvailable**         | A tool can only be borrowed if it is not currently part of an open sharing record.                                  |
| **ToolConditionUpdateRequired** | When a sharing record is closed, the tool’s condition must be reviewed and updated before it can be borrowed again. |

---

That’s the **Classic API Story** layout: clear prose, linked semantics, and transform-ready structure.

Would you like me to append a short **narrative introduction** and **closing summary** (as if this were part of a published Story file in a repository)? It’s common practice to open with a short “Why this API exists” paragraph and close with a “Design Notes” section.

