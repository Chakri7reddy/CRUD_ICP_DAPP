
````markdown
# 🚀 ICP-based CRUD DApp

A simple **CRUD (Create, Read, Update, Delete)** Decentralized Application built on the **Internet Computer (ICP)**. This DApp allows users to perform operations on user data stored **on-chain** using **Rust-based smart contracts** and a **React frontend**.

---

## 🧩 Tech Stack

| Layer        | Technology                       |
| ------------ | -------------------------------- |
| 💻 Backend   | Rust + `ic-cdk`, `ic-cdk-macros` |
| 🎨 Frontend  | React.js + SCSS (`index.scss`)   |
| 🔁 Interface | Candid (`.did` file)             |
| 🔧 Tooling   | DFX SDK (dfx)                    |

---

## 🏗️ Backend Logic (Rust)

User data is managed using a `HashMap<u64, User>` stored via `ic_cdk::storage`.

### 📦 Data Structure

Each user is assigned a unique `id` and stored with:

```rust
struct User {
  id: u64,
  name: String,
  email: String,
}
```
````

### 🛠️ Exposed Canister Methods

| Method                         | Description                         |
| ------------------------------ | ----------------------------------- |
| `create_user(name, email)`     | ➕ Create a new user, returns ID    |
| `read_user(id)`                | 🔍 Read user by ID (returns Option) |
| `update_user(id, name, email)` | ✏️ Update existing user             |
| `delete_user(id)`              | ❌ Delete user by ID                |
| `list_users()`                 | 📋 List all users                   |

📎 **DID File**: Automatically generated using:

```rust
#[test]
fn generate_did() {
    export_service!();
    std::fs::write("src/icp_crud_dapp_backend.did", __export_service()).unwrap();
}
```

---

## 🌐 Frontend UI (React)

- Built using **React.js**
- Communicates with ICP backend using generated Candid JS bindings.
- Styled with **SCSS** (in `index.scss`).
- Fully functional UI with:

  - User creation form
  - Read by ID
  - Update user
  - Delete last user
  - Table listing all users

---

## 📦 Installation & Run

### 🧪 Local Development (DFX)

```bash
# 1. Create or navigate to project directory
dfx new icp-crud-dapp
cd icp-crud-dapp

# 2. Start local replica
dfx start --background

# 3. Build canisters
dfx build

# 4. Deploy canisters
dfx deploy
```

### ⚛️ Frontend Setup

```bash
# Navigate to frontend folder (if applicable)
cd src/icp_crud_dapp_frontend

# Install React dependencies
npm install

# Run frontend locally
npm run start
```

---

## 🧪 Useful Commands

| Command             | Purpose                       |
| ------------------- | ----------------------------- |
| `dfx new <project>` | Create new ICP project        |
| `dfx start`         | Start local ICP replica       |
| `dfx build`         | Compile Rust → WASM canisters |
| `dfx deploy`        | Deploy backend canisters      |
| `cargo test`        | Run Rust unit tests           |
| `npm install`       | Install frontend dependencies |
| `npm run start`     | Run frontend server           |

---

## 📜 License

MIT License © 2025 Chakri Reddy

---

## 🌍 Connect

- 🔗 [Internet Computer SDK](https://internetcomputer.org/docs/current/developer-docs/backend/overview)


---

✅ **Built with 💙 on the Internet Computer**

```

---

Let me know if you'd like this auto-saved as `README.md` or also want GitHub badges (like build, license, or deployment) added at the top.
```
