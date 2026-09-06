GitHub REST API Testing with Postman
Project Overview
This project demonstrates how to explore, test, and automate interactions with the GitHub REST API using Postman.

The project focuses on authentication and CRUD operations using GitHub repositories, files, and issues.

Tools Used
GitHub REST API
Postman
GitHub
JSON
JavaScript for Postman test scripts
API Base URL
https://api.github.com

Authentication
The GitHub REST API is accessed using a Personal Access Token.

The token is stored in a Postman environment variable called:

auth_token

The token is not included in this repository for security reasons.

API Operations Tested
Operation	Method	Endpoint
Authentication	GET	/user
Get Repository	GET	/repos/{owner}/{repo}
Get File	GET	/repos/{owner}/{repo}/contents/{path}
Create Issue	POST	/repos/{owner}/{repo}/issues
Create File	PUT	/repos/{owner}/{repo}/contents/{path}
Update File	PUT	/repos/{owner}/{repo}/contents/{path}
Get Issue	GET	/repos/{owner}/{repo}/issues/{issue_number}
Update Issue	PATCH	/repos/{owner}/{repo}/issues/{issue_number}
Delete File	DELETE	/repos/{owner}/{repo}/contents/{path}
Postman Environment Variables
The following variables are used:

base_url - GitHub API base URL
owner - GitHub username
repo - Repository name
auth_token - Authentication token
file_path - File used for testing
file_sha - SHA of the GitHub file
issue_number - Number of the test issue
Automation
Postman scripts automatically save dynamic values from API responses.

For example:

The file SHA is saved into file_sha.
The issue number is saved into issue_number.
These variables are then reused by later requests.

Testing
Post-response test scripts are used to verify:

HTTP status codes
Authentication success
Repository information
File existence
Issue creation
Issue updates
File deletion
Collection Runner
The Postman Collection Runner is used to execute the requests in sequence.

The main workflow is:

Authenticate
Get repository
Create file
Get file
Update file
Create issue
Get issue
Update issue
Delete file
Confirm file deletion
Security
The actual GitHub authentication token must not be uploaded to GitHub.

Only the Postman collection and environment configuration are included in the repository. Sensitive credentials should be entered directly into Postman.
