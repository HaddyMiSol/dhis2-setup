## Step 2: PostgreSQL Installation (Ubuntu WSL)

### 2.1 Install PostgreSQL 14
To install PostgreSQL on your Linux/Ubuntu WSL environment using Homebrew:

```bash
brew install postgresql@14
```

Start the PostgreSQL service using Linux brew services:

```bash
brew services start postgresql@14
```

### 2.2 Verify Installation
Check the version to ensure PostgreSQL is installed correctly:

```bash
psql --version
```

### Output Example

The output should display something like:

```text
psql (PostgreSQL) 14.5
```

### 2.3 Managing Databases on Linux/WSL
Since GUI applications like pgAdmin (installed via Homebrew casks) are designed for macOS and are not natively supported inside standard headless Linux/WSL environments without complex X11/Wayland forwarding, you can manage your PostgreSQL databases via the command line using `psql`, or install a web-based client like **pgweb** or **Adminer**.

To install a lightweight web-based interface like `pgweb` via Homebrew:

```bash
brew install pgweb
```

Run pgweb to access your database through your Windows browser:

```bash
pgweb --db=dhis2 --user=dhis --pass=dhis
```
*(Then open `http://localhost:8080` in your Windows web browser).*

### 2.4 Create a User and Database
Create a new user named `dhis`:

```bash
createuser -s dhis
```

Set the password for the user:

```bash
psql -c "ALTER USER dhis WITH PASSWORD 'dhis';"
```

Create a new database owned by the user:

```bash
createdb -O dhis dhis2
```

This confirms that PostgreSQL 14 is successfully installed and configured on your Ubuntu WSL environment.