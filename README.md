# Project 4 — SmartSolutions Pvt Ltd

## Internal Name Resolution using DNS (Windows Server)

---

## Project Overview

SmartSolutions Pvt Ltd required an internal name resolution system so employees could access internal resources using **hostnames instead of IP addresses**.

The objective of this project was to configure **DNS in a Windows Server environment** to provide easy and structured access to internal services.

---

## Business Problem

Employees were accessing internal services using **IP addresses**, which created several issues:

* Difficult for employees to remember IP addresses
* Increased dependency on IT support
* Infrastructure changes caused service disruptions
* Lack of a structured internal network environment

Example of old access method:

```
\\192.168.10.10\Shared
http://192.168.10.10
```

---

## Project Objective

Implement **internal DNS name resolution** so employees can access services using **meaningful hostnames**.

Example after implementation:

```
\\fileserver\Shared
http://intranet
ping appserver
```

---

## Organization Structure

### Departments

* IT
* R&D
* Operations

### Total Users

10 Employees

Example distribution:

| Department | Users |
| ---------- | ----- |
| IT         | 3     |
| R&D        | 4     |
| Operations | 3     |

---

## Lab Environment

| Component   | Configuration                  |
| ----------- | ------------------------------ |
| Server      | Windows Server                 |
| Domain      | lab.local                      |
| DNS         | Installed on Domain Controller |
| Server Name | DC01                           |
| Server IP   | 192.168.10.10                  |

Note: Due to hardware limitations in the lab environment, all roles were configured on a **single Windows Server (DC01)**. In production environments, these services would typically run on separate servers.

---

## DNS Configuration

A **Forward Lookup Zone** was used to manage internal hostname resolution.

Zone Name:

```
lab.local
```

### DNS Records Created

| Record Type | Hostname   | IP Address    | Purpose              |
| ----------- | ---------- | ------------- | -------------------- |
| A Record    | dc01       | 192.168.10.10 | Domain Controller    |
| A Record    | fileserver | 192.168.10.10 | File Services        |
| A Record    | intranet   | 192.168.10.10 | Internal Website     |
| A Record    | appserver  | 192.168.10.10 | Application Services |

All hostnames resolve to the same server because this is a **lab setup**.

---

## User Access After Implementation

Employees can now access resources using simple hostnames.

### File Server Access

```
\\fileserver\Shared
```

### Internal Web Portal

```
http://intranet
```

### Application Access

```
http://appserver
```

---

## Verification Tests

### DNS Resolution Test

```
ping fileserver
ping intranet
ping appserver
```

Result:

All hostnames successfully resolved to:

```
192.168.10.10
```

---

### Shared Folder Access Test

```
\\fileserver
```

Result:

Users successfully accessed the shared folder using the hostname.

---

## Screenshots

The following screenshots demonstrate successful implementation:

* DNS Manager — Forward Lookup Zone Configuration
* DNS A Records for Internal Services
* Ping Test for Hostname Resolution
* Shared Folder Access via Hostname

---

## Skills Demonstrated

* Windows Server Administration
* DNS Configuration
* Forward Lookup Zones
* A Records
* Internal Name Resolution
* Hostname-based Resource Access
* Enterprise Network Design

---

## Outcome

After implementing the DNS name resolution system:

* Employees access resources using **simple hostnames**
* No need to remember **IP addresses**
* IT support requests are reduced
* Internal infrastructure becomes **structured and scalable**

---

## Author

**Vijay Partap Singh Salathia**
Windows Server & Infrastructure Practice Lab
