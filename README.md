#    Run in powershell, while connected to exchange!!
#    Permission Types:
#    Owner.  Allows read, create, modify and delete all items and folders. Also allows manage items permissions
#    PublishingEditor.  Allows read, create, modify and delete items/subfolders.
#    Editor.  Allows read, create, modify and delete items.
#    PublishingAuthor.  Allows read, create all items/subfolders. You can modify and delete only items you create.
#    Author.  Allows create and read items; edit and delete own items.
#    NonEditingAuthor.  Allows full read access and create items. You can delete only your own items.
#    Reviewer.  Read only.
#    Contributor.  Allows create items and folders.
#    AvailabilityOnly.  Allows read free/busy information from calendar
#    LimitedDetails.  Allows view of the subject and location.
#    None.  No permissions to access folder and files.
 

foreach($user in Get-Mailbox -RecipientTypeDetails UserMailbox) {Set-MailboxFolderPermission -Identity ($user.alias+':\calendar’) -User Default -AccessRights Reviewer}
