# moztw-space-backend
The Backend of the Live Status System for MozTW Space http://moztw.org/space/

# Discussion
https://moztw.hackpad.com/lfbTlV3Aq8Y

# Service
https://api.moztw-space.rmstudio.tw

# APIs

## Version 1
| Feature Name | URI | Method | Fields | Returns |
|:--------------:|:-------------:|--------|--------|---------|
| Register | /v1/register | POST | <ul><li>(string) `nickname` Nickname of the User</li><li>(string) `mozillians` Mozillians ID</li><li>(string) `id` ID for Login</li></ul> | <ul><li>(boolean) `status` Status of the Registration<ul><li>`true` successful</li><li>`false` failed</li></ul></li><li>(int) `error` Error Code<ul><li>0: no errors</li><li>1: `id` is duplicated</li><li>2: `mozillians` is already taken by another user</li></ul></li></ul> |
| Sign In | /v1/signin/`id` | GET | (none) | <ul><li>(boolean) `status` Status of Sign In<ul><li>`true` successful</li><li>`false` failed</li></ul></li><li>(string) `nickname` Nickname of the Signing Out User</li><li>(int) `timestamp` Timestamp of Signing Out</li></ul> |
| Sign Out | /v1/signout/`id` | GET | (none) | <ul><li>(boolean) `status` Status of Sign Out<ul><li>`true` successful</li><li>`false` failed</li></ul></li><li>(string) `nickname` Nickname of the Signing Out User</li><li>(int) `timestamp` Timestamp of Signing Out</li></ul> |
| Profile Fetch | /v1/profile/`id` | GET | (none) | <ul><li>(boolean) `status` Profile is Exists or not<ul><li>`true` successful</li><li>`false` failed</li></ul></li><li>(string) `nickname` Nickname of the User</li><li>(string) `mozillians` Mozillians ID</li><li>(string) `id` ID for Login</li></ul> |
| Profile Update | /v1/profile/`id` | POST | <ul><li>(string) `nickname` Nickname of the User</li><li>(string) `mozillians` Mozillians ID</li><li>(string) `id` ID for Login</li></ul> | <ul><li>(boolean) `status` Status of Profile Updating<ul><li>`true` successful</li><li>`false` failed</li></ul></li><li>(int) `error` Error Code<ul><li>0: no errors</li><li>1: `id` is not registed</li></ul></li></ul> |
| Status Fetch | /v1/status | GET | (none) | <ul><li>(object array) `active` List of Users in the Space<ul><li>(string) `nickname` Nickname of the User</li><li>(string) `mozillians` Mozillians ID</li><li>(string) `id` ID of the User</li><li>(int) `stays` The Time of the User Stay in the Space in seconds</li></ul></li></ul> |
