# Laravel Large File Upload Challenge

## Objective
The goal of this task is to build a robust file upload feature using the **latest version of Laravel** that can handle very large files (1GB+) without crashing the server, timing out, or consuming excessive memory. 

## Time Limit
**2 Hours**

## Test File
You can download a sample large file for testing your implementation from this [Google Drive Link](https://drive.google.com/drive/folders/13vwUrdlHr3-gg0xM05iz02qCc0m7KL6U?usp=sharing).

## Core Requirements
- **Framework**: You must use the latest version of Laravel for the backend.
- Build backend endpoints to handle large file uploads safely.
- Implement a simple frontend (vanilla HTML/JS, Blade, Livewire, or Vue/React is fine) to select and upload the file.
- The server must not read the entire file into memory at once (e.g., utilize chunking or streaming).
- Provide clear instructions on how to run your application.

## Passing Scenarios (Acceptance Criteria)
To successfully pass this task, the solution must meet the following criteria:
1. **Successful Large Upload**: A user can successfully upload a file that is significantly larger than the server's available RAM or typical request size limits (e.g., 1GB - 5GB).
2. **Stable Memory Footprint**: The server's memory usage remains low and stable during the upload process (no `Out of Memory` crashes).
3. **Graceful Error Handling**: If the upload is interrupted (e.g., network failure or user cancels), the server handles it gracefully and cleans up any abandoned partial files/chunks.
4. **Concurrent Uploads**: The server does not block other requests while a large file is being uploaded.

## Bonus Points (Stand Out!)
If you finish the core requirements early, consider implementing any of the following to stand out:
- **Resumable Uploads**: If an upload drops midway, the user can resume from the last successful chunk instead of starting over.
- **Real-time Progress Indicator**: A smooth progress bar on the frontend showing upload speed, time remaining, and percentage.
- **File Integrity Check**: Calculate the hash (e.g., MD5/SHA-256) of the uploaded file and verify it against the frontend's hash to ensure no data corruption occurred during transit.
- **Streaming directly to Cloud Storage**: Stream the incoming file chunks directly to a service like AWS S3 rather than saving them to the local disk first.
- **Dockerized Environment**: Include a `Dockerfile` and/or `docker-compose.yml` to allow reviewers to spin up the project with a single command.

## Submission Guidelines
- Ensure your `README.md` includes clear steps to install dependencies, configure environment variables, and start the server.
- Document the approach you took (e.g., chunking vs streaming) and why you chose it.
