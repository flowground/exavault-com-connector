# ![LOGO](logo.png) ExaVault **flow**ground Connector

## Description

A generated **flow**ground connector for the ExaVault API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/exavault.com/1.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:40:29+03:00

## API Description

ExaVault's API allows you to incorporate ExaVault's suite of file transfer and user management tools into your own application.

ExaVault supports both POST (recommended when requesting large data sets) and GET operations, and requires an API key in order to use.


## Authorization

This API does not require authorization.

## Actions

### Authenticates a user into the API

> Returns access token in the Response object

*Tags:* `v1`

#### Input Parameters
* `username` - _required_ - Name of of user to authenticate
* `password` - _required_ - User's password

### Checks to see if each file or folder in the array exists

> Requires access token obtained via the authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `filePaths` - _required_ - Array containing paths of the files or folders to check

### Copies files, folders to the destination path

> Requires access token obtained via the authenticateUser operation. Available to users with the 'upload' permission.

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `filePaths` - _required_ - Remote paths of the files or folders to copy
* `destinationPath` - _required_ - Remote destination path to copy files/folders to

### Create a folder at a specified path

> Requires access token obtained via the authenticateUser operation. Available to users with the 'upload' permission.

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `folderName` - _required_ - Name of the folder to create
* `path` - _required_ - Where to create the folder

### Creates a new Notification object

> Requires access token obtained via the authenticateUser operation. Available to users with 'notification' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `path` - _required_ - Full path of file/folder where notification is set.
* `action` - _required_ - Type of action to filter on: 'upload', 'download', 'delete', 'all'
* `usernames` - _required_ - User type to filter on: 'notice_user_all', 'notice_user_all_recipients', 'notice_user_all_users'
* `sendEmail` - _required_ - Set to true if the user should be notified by email when the notification is triggered.
* `emails` - _optional_ - Email addresses to send notification to. If not specified, sends to owner by default.

### Create a new Share object

> Requires access token obtained via the authenticateUser operation. Available to users with the 'share' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `type` - _required_ - The type of share to create: shared_folder, send, receive.
* `name` - _required_ - Name of the Share.
* `filePaths` - _required_ - Array of strings containing the file paths to share.
* `subject` - _optional_ - Share message subject (for email invitations).
* `message` - _optional_ - Share message contents (for email invitations).
* `emails` - _optional_ - Array of strings for email recipients (for email invitations).
* `ccEmail` - _optional_ - Specifies a CC email recipient.
* `requireEmail` - _optional_ - Requires a user's email to access (defaults to false if not specified).
* `accessMode` - _optional_ - Type of permissions share recipients have: upload, download, download_upload, download_upload_modify, download_upload_modify_delete. Defaults to download if no option specified.
* `embed` - _optional_ - Allows user to embed a widget with the share. Defaults to false if not specified.
* `isPublic` - _optional_ - True if share has a public URL, otherwise defaults to false
* `password` - _optional_ - If not null, value of password is required to access this Share
* `expiration` - _optional_ - The date the current Share should expire, formatted YYYY-mm-dd
* `hasNotification` - _optional_ - True if the user should be notified about activity on this Share.
* `notificationEmails` - _optional_ - An array of recipients who should receive notification emails.
* `fileDropCreateFolders` - _optional_ - If true, all receive folder submissions will be uploaded separate folders (only applicable for Receive folder types)

### Adds a new subaccount user to the current account

> Requires access token obtained via the authenticateUser operation. Available to users with the 'manage users' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `username` - _required_ - Name of the subaccount user to create
* `destinationFolder` - _required_ - The user's home folder
* `email` - _required_ - The user's email address
* `password` - _required_ - The user's password
* `role` - _required_ - The user's role, i.e: 'user' or 'admin'
* `permissions` - _required_ - A CSV string of user permissions. The following values are supported: upload, download, delete, modify, list, changePassword, share, notification.
* `timeZone` - _required_ - The user's timezone, used for accurate time display within SWFT. See <a href='https://php.net/manual/en/timezones.php' target='blank'>this page</a> for allowed values
* `nickname` - _optional_ - The user's nickname
* `expiration` - _optional_ - The date when the user should expire, formatted YYYY-mm-dd
* `locked` - _optional_ - If true, the user's account is locked by default
* `welcomeEmail` - _optional_ - If true, send a user email upon creation

### Deletes a Notification by ID

> Requires access token obtained via the authenticateUser operation. Available to users with 'notification' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `id` - _required_ - ID of the Notification to delete.

### Delete the specified files/folders

> Requires access token obtained via the authenticateUser operation. Available to users with the 'delete' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `filePaths` - _required_ - Array containing paths of the files or folder to delete

### Deletes a Share by ID

> Requires access token obtained via the authenticateUser operation. Available to users with 'share' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `id` - _required_ - ID of the Share to delete.

### Deletes a subaccount user for the current account

> Requires access token obtained via the authenticateUser operation. Available to users with 'manage users' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `username` - _required_ - Name of the subaccount user to delete

### Gets the account object for the currently logged in user

> Requires access token obtained via the authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call

### Gets the user object for the currently logged in user

> Requires access token obtained via the authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call

### Returns a unique URL for handling file downloads

> Requires access token obtained via the authenticateUser operation. URL points at the appropriate storage server for file download.

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `filePaths` - _required_ - Path of file to be downloaded
* `downloadName` - _optional_ - The name of the file to be downloaded

### Returns a list of account activity. Allows for searching the activity log.

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `offset` - _optional_ - Starting record in the result set. Can be used for pagination.
* `sortBy` - _optional_ - Sort method ['sort_logs_date' or 'sort_logs_ip_address' or 'sort_logs_username' or 'sort_logs_file' or 'sort_logs_file_source' or 'sort_logs_operation', or 'sort_logs_duration', or 'sort_logs_size', or 'sort_logs_protocol']
* `sortOrder` - _optional_ - Sort in either ascending or descending order: asc, desc
* `filterBy` - _optional_ - Field to search on ['filter_logs_date' or 'filter_logs_ip_address' or 'filter_logs_username' or 'filter_logs_operation' or 'filter_logs_file']
* `filter` - _optional_ - Search criteria. For date ranges, use format 'start_date::end_date'
* `itemLimit` - _optional_ - Number of logs to return. Can be used for pagination.

### Get folders for a specified path

> Requires access token obtained via the authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `path` - _required_ - The remote file path

### Returns a notification based on the given ID

> Requires access token obtained via the authenticateUser operation. Available to users with the 'notification' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `id` - _required_ - ID of the Notification

### Returns all notification activity for the current user

> Requires access token obtained via the authenticateUser operation. Available to users with the 'notification' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call

### Returns all notifications for the current user

> Requires access token obtained via the authenticateUser operation. Available to users with the 'notification' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `type` - _required_ - Type of notification to filter on: 'file', 'folder', 'shared_folder', 'send_receipt', 'share_receipt', 'file_drop'
* `sortBy` - _optional_ - Sort by one of the following: 'sort_notifications_folder_name', 'sort_notifications_path', 'sort_notifications_date'
* `sortOrder` - _optional_ - Sort by 'asc' or 'desc' order.
* `filter` - _optional_ - Filter by the provided search terms.

### Get a listing of files/folders for the specified path

> Requires access token obtained via the authenticateUser operation. Available to users with 'list files' permission.

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `path` - _required_ - The remote file path
* `sortBy` - _required_ - Sort according to attribute: sort_files_name, sort_files_size, sort_files_date, sort_files_type, sort_files_timeline
* `sortOrder` - _required_ - Sort in either ascending or descending order: asc, desc
* `offset` - _required_ - Determines which item to start on for pagination
* `limit` - _required_ - The number of files to limit the result
* `detailed` - _optional_ - If true, returns sharedFolder, notifications or other objects associated with specified path
* `pattern` - _optional_ - Regex string. If not null, perform a search with specified pattern

### Get the properties for each of the specified files/folders

> Requires access token obtained via the authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `filePaths` - _required_ - Array containing paths of the files or folder to get

### Returns a share by the specified ID

> Requires access token obtained via the authenticateUser operation. Available to users with the 'share' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `id` - _required_ - ID of the requested Share

### Return activity log entries for the specified Share ID

> Requires access token obtained via the authenticateUser operation. Available to users with the 'share' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `id` - _required_ - ID of the Share

### Returns all Shares for the current user

> Requires access token obtained via the authenticateUser operation. Available to users with the 'share' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `type` - _optional_ - The type of share to return: 'shared_folder', 'send', or 'receive'. If no argument specified, will return all Shares types.
* `sortBy` - _optional_ - Sort by one of the following: 'sort_shares_name', 'sort_shares_date', 'sort_shares_user', 'sort_shares_access_mode'.
* `sortOrder` - _optional_ - Sort by 'asc' or 'desc' order.
* `filter` - _optional_ - Filter by the provided search terms.
* `include` - _optional_ - Filter by all, active-only, or current user's only.
* `offset` - _optional_ - Start position of results to return, for pagination.
* `limit` - _optional_ - Maximum number of elements to return or 0 if no limit.

### Returns a unique URL for handling file uploads

> Requires access token obtained via the authenticateUser operation. Called before an upload is started to get URL to appropriate storage server. Available to users with the 'write' permission.

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `fileSize` - _required_ - Size of the file to upload, in bytes
* `destinationPath` - _required_ - Path relative to account's home directory, including file name
* `allowOverwrite` - _optional_ - True if the file should be overwritten, false if different file names should be generated
* `resume` - _optional_ - True if upload resume is supported, false if it isn't

### Get the specified subaccount user for the current account

> Requires access token obtained via the authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `username` - _required_ - Name of the subaccount user to get

### Gets the user object for the currently logged in user

> Requires access token obtained via the authenticateUser operation. Available to users with the 'manage users' permission set

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `sortBy` - _required_ - sort method ['sort_users_username' or 'sort_users_nickname' or 'sort_users_email' or 'sort_users_home_folder']
* `sortOrder` - _required_ - sort order, i.e. 'asc' or 'desc'

### Removes user's access token from database, logging them out of API

> Requires access token obtained via the authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call

### Moves files, folders to the destination path

> Requires access token obtained via the authenticateUser operation. Available to users with the 'upload' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `filePaths` - _required_ - Remote paths of the files or folders to move
* `destinationPath` - _required_ - Remote destination path to move files/folders to

### Returns a resized image of the specified document for support file types

> Requires access token obtained via authenticateUser operation

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `path` - _required_ - Path of the image relative to the user's home directory
* `size` - _required_ - The size of the image: small, medium, large
* `width` - _optional_ - Overrides sizes. Sets to a specific width
* `height` - _optional_ - Overrides sizes. Sets to a specific height
* `page` - _optional_ - Page number for the document

### Rename a file or folder at the specified path

> Requires access token obtained via the authenticateUser operation. Available to users with the 'modify' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `filePath` - _required_ - Remote path of the files or folder to rename
* `newName` - _required_ - The new name of the file or folder

### Updates an existing notification by ID

> Requires access token obtained via the authenticateUser operation. Available to users with 'notification' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `id` - _required_ - The notification ID
* `path` - _optional_ - Full path of file/folder where notification is set.
* `action` - _optional_ - Type of action to filter on: 'upload', 'download', 'delete', 'all'
* `usernames` - _optional_ - User type to filter on: 'notice_user_all', 'notice_user_all_recipients', 'notice_user_all_users'
* `emails` - _optional_ - Email addresses to send notification to. If not specified, sends to owner by default.
* `sendEmail` - _optional_ - Set to true if the user should be notified by email when the notification is triggered.

### Update an existing Share by ID

> Requires access token obtained via the authenticateUser operation. Available to users with the 'share' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `id` - _required_ - The ID of the Share to update.
* `name` - _optional_ - Name of the Share.
* `filePaths` - _optional_ - Array of strings containing the file paths to share.
* `subject` - _optional_ - Share message subject (for email invitations).
* `message` - _optional_ - Share message contents (for email invitations).
* `emails` - _optional_ - Array of strings for email recipients (for email invitations).
* `ccEmail` - _optional_ - Specifies a CC email recipient.
* `requireEmail` - _optional_ - Requires a user's email to access.
* `accessMode` - _optional_ - Type of permissions share recipients have: upload, download, download_upload, download_upload_modify, download_upload_modify_delete.
* `embed` - _optional_ - Allows user to embed a widget with the share.
* `isPublic` - _optional_ - True if share has a public URL, otherwise defaults to false
* `password` - _optional_ - If not null, value of password is required to access this Share
* `expiration` - _optional_ - The date the current Share should expire, formatted YYYY-mm-dd
* `hasNotification` - _optional_ - True if the user should be notified about activity on this Share.
* `notificationEmails` - _optional_ - An array of recipients who should receive notification emails.
* `fileDropCreateFolders` - _optional_ - If true, all receive folder submissions will be uploaded separate folders (only applicable for Receive folder types)

### Updates a subaccount user for the current account

> Requires access token obtained via the authenticateUser operation. Available to users with 'manage users' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `userId` - _required_ - The user ID, must be obtained from getUser method first
* `username` - _optional_ - Name of the subaccount user to modify
* `nickname` - _optional_ - The user's nickname
* `expiration` - _optional_ - The date when use should expire in format: YYYY-MM-DD
* `email` - _optional_ - The user's email
* `destinationFolder` - _optional_ - The user's home folder
* `password` - _optional_ - The user's password
* `locked` - _optional_ - If true, the user's account is locked by default
* `role` - _optional_ - The user's role, i.e: 'user', 'admin', 'master'
* `permissions` - _optional_ - A CSV string of user permissions.

### Returns true if requested username has not already been taken in the system

> Requires access token obtained via the authenticateUser operation. Available to users with the 'manage users' permission

*Tags:* `v1`

#### Input Parameters
* `access_token` - _required_ - Access token required to make the API call
* `username` - _required_ - Username to check

## License

**flow**ground :- Telekom iPaaS / exavault-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
