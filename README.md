# MyQuery — Database SQL Query Tool

<img width="1188" height="728" alt="Screenshot 2026-10-17 at 12 59 15 PM" src="https://github.com/user-attachments/assets/642ca5dc-684e-4370-b252-db9dd9a56f69" />

**MyQuery** ("My Database Query App") is a platform-independent Java Swing desktop SQL client that utilizes JDBC drivers to connect to Oracle, PostgreSQL, SDB, and MySQL databases. It allows users to securely save and manage connections to both local and remote environments. Beyond manual and UI-driven SQL query generation, the application enables database object exploration and seamless data import/export across different database systems. For administrators, MyQuery provides tools to monitor system resources (CPU, memory, and disk usage for Oracle), track active database locks, and terminate resource-intensive queries.

## What's in this package

| File | Description |
|------|-------------|
| `myquery.jar` | Application JAR |
| `myquery2.sh` | Linux/Mac launcher |
| `myquery2.bat` | Windows launcher |
| `myquery.xml` | Driver configuration |
| `myquery.ini` | JAVA_HOME config |
| `log4j2.xml` | Logging config |
| `jdbc/` | JDBC driver jars (PostgreSQL bundled) |
| `misc/` | Runtime dependency jars |

## Supported databases

| Database | Driver | Bundled? | Where to get |
|----------|--------|----------|--------------|
| PostgreSQL | `org.postgresql.Driver` | Yes (BSD) | Bundled |
| Oracle | `oracle.jdbc.driver.OracleDriver` | No | [Oracle JDBC](https://www.oracle.com/database/technologies/appdev/jdbc-downloads.html) |
| MySQL | `com.mysql.cj.jdbc.Driver` | No | [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/) |

## Quick start

Prerequisite: JDK 17+

```bash
# Linux/macOS
./myquery2.sh

# Windows
.\myquery2.bat
```

If `java` is not on your PATH, set `JAVA_HOME` in `myquery.ini`.

## Adding a JDBC driver

1. Download the driver jar from the vendor (see table above)
2. Place it in the `jdbc/` directory
3. The launcher scripts auto-detect jars in `jdbc/`

## Features

- Tree-based connection browser with schema/table/views/indexes navigation
- SQL editor with multi-statement support
- Paginated query results (configurable fetch limit)
- Table import and export: XML, CSV, HTML (XSL), DDL generation
- LOB cell inspection: MIME type detection, text/image/HTML render, content download
- Content detect, translate, and dump for LOB/CLOB/BLOB columns
- Detect encoding for file content
- Explain plan / execution plan per database backend
- Long running queries and lock info
- List statistics and bind variable support
- Server monitor: CPU, memory, disk, and table usage charts
- Language & character set detection (Apache Tika)
