---
share: true
---
# Lab: File path traversal, simple case

- **Category**: Path Traversal
- **Difficulty**: Apprentice
- **Date Solved**: 2025-05-09

---

## Goal

This lab contains a path traversal vulnerability in the display of product images.
To solve the lab, retrieve the contents of the `/etc/passwd` file.

---

## Key Concept

Using `../` to access parent directories.

---

## Exploitation Steps

###### 1. Find a request that include a file path.
![Screenshot From 2025-05-09 18-36-36.png](./01_PROJECTS/PortSwigger-Web-Security-Academy/Attachment/Screenshot%20From%202025-05-09%2018-36-36.png)
###### 2. Modify the file path to `../../../etc/passwd`.
![Screenshot From 2025-05-09 18-37-35.png](./01_PROJECTS/PortSwigger-Web-Security-Academy/Attachment/Screenshot%20From%202025-05-09%2018-37-35.png)
###### 3. Check the response.
![Screenshot From 2025-05-09 18-38-40.png](./01_PROJECTS/PortSwigger-Web-Security-Academy/Attachment/Screenshot%20From%202025-05-09%2018-38-40.png)


---

## Result

`/etc/passwd` contents were displayed.

---

## Notes

`filename=/etc/passwd` does not work because the file path is interpreted as a relative path. Most web applications do not allow access to the root directory, so absolute paths like `/etc/passwd` are blocked.


