```markdown
# Lab Management System  
**Oracle Forms & Reports**  

A centralized application to manage all aspects of laboratory operations—sample intake, inventory, equipment scheduling, experiment tracking and reporting—built with Oracle Forms & Reports on an Oracle database.

---

## ⚠️ Confidentiality Notice  
Some form modules and library files are omitted from this repository due to client‑side confidentiality and copyright restrictions.  
If you require full access, please contact the project owner under the appropriate NDAs.

---

## 📂 Repository Structure  
```

/                   ← this README.md
login\_test.fmb      ← login form (source)
/login\_test.fmx     ← login form (compiled)
/modules/           ← (confidential modules not included)
/reports/           ← (compiled reports; source withheld)
/sql/               ← schema creation & seed data scripts

````

---

## 🏗️ Main Modules & Forms  

| Module                      | Forms Source  | Forms Executable | Description                                        |
|:----------------------------|:--------------|:-----------------|:---------------------------------------------------|
| **Login & Security**        | `login_test.fmb` | `login_test.fmx`  | User authentication & role‑based access control     |
| **Sample Registration**     | `sample_reg.fmb` | `sample_reg.fmx`  | Capture specimen metadata (ID, type, origin, etc.) |
| **Inventory Management**    | `inventory.fmb`  | `inventory.fmx`   | Track reagents, consumables, reorder alerts        |
| **Equipment Booking**       | `equip_book.fmb` | `equip_book.fmx`  | Reserve instruments, view availability calendar    |
| **Calibration & Maintenance** | `calibration.fmb` | `calibration.fmx` | Schedule and log equipment calibration/maintenance  |
| **Experiment Scheduling**   | `schedule.fmb`   | `schedule.fmx`    | Assign experiments to labs, set timelines          |
| **Results Capture**         | `results_entry.fmb` | `results_entry.fmx` | Enter and validate experimental data/results       |
| **Reports & Analytics**     | `reports_menu.fmb` | `reports_menu.fmx` | Generate summary, compliance, and performance reports |
| **User & Role Administration** | `user_admin.fmb`  | `user_admin.fmx`   | Manage staff accounts, roles, permissions           |

> **Note:**  
> - Only the **Login** module is included here. All other `.fmb`/`.fmx` files have been excluded to protect proprietary logic.  
> - SQL scripts in `/sql/` define the schema for tables such as `USERS`, `SAMPLES`, `INVENTORY`, `EQUIPMENT`, `EXPERIMENTS`, etc.

---

## 🚀 Installation & Deployment  

1. **Database Setup**  
   - Run `sql/schema.sql` to create tables, sequences and constraints.  
   - Run `sql/seed_data.sql` to insert lookup values (e.g. roles, equipment types).

2. **Compile Forms**  
   - Open each `.fmb` in Oracle Forms Developer → **Compile** → produce `.fmx`.  
   - Copy compiled `.fmx` files to your Forms Server’s deployment directory.

3. **Configure Forms Server**  
   - Ensure `FORMS_PATH` (in `formsweb.cfg`) includes your deployment directory.  
   - Map each form name (e.g. `login_test`) in your `formsweb.cfg` or `registry`.

4. **Compile & Deploy Reports**  
   - Use Oracle Reports Developer to compile any `.rdf`/`.rep` modules.  
   - Register them on the Reports Server and grant access as needed.

5. **Launch Application**  
   - In a browser or Java Applet, navigate to:  
     ```
     http://<forms-server>:<port>/forms/frmservlet?config=labconfig&form=login_test.fmx
     ```

---

## 📞 Support & Contact  
For full source access or client‑specific modules, please reach out to the project lead under your existing support agreement.  
````
