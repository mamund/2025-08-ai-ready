graph TD
  Home -->|viewTools| ToolCollection
  Home -->|viewMembers| MemberCollection
  Home -->|viewSharings| SharingCollection

  ToolCollection -->|viewTool| ToolItem
  ToolCollection -->|addTool| ToolItem
  ToolItem -->|updateTool| ToolItem

  MemberCollection -->|viewMember| MemberItem
  MemberCollection -->|addMember| MemberItem
  MemberItem -->|updateMember| MemberItem
  MemberItem -->|suspendMember| MemberItem
  MemberItem -->|activateMember| MemberItem

  SharingCollection -->|createSharing| SharingItem
  SharingCollection -->|viewSharing| SharingItem
  SharingItem -->|closeSharing| SharingItem

