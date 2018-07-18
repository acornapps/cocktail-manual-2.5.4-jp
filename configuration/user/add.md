### 2.1.1 Add User

---

This feature allows you to add user accounts.

The user ID must be in an email format \(cocktail@example.com\). The password settings feature is not currently supported, and thus, the password must be initialized and changed after creating an ID.
\(The password automatically assigned after initialization is 'Pass0000'.\)

##### a\) Configuration → User → Click the [+] button in the top-right corner.![](/assets/EN/2.5/2.1.1_1.png)

##### b\)Click the [Create] button after selecting the user ID, name, and privileges.![](/assets/EN/2.5/2.1.1_2.png)

| **Privilege** | **Dashboard** | **Service** | **Catalog** | **Cluster** | **Configuration** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ADMIN | ⃝ | ⃝ | ⃝ | ⃝ | ⃝ |
| MANAGER | ⃝ | ⃝ | ⃝ | ⃝ | X |
| DEVOPS | X | △ | ⃝ | X | X |

##### - ADMIN : Company-wide service management. Privileges include usage access to the dashboard, services, catalogs, clusters, and configuration.

##### - MANAGER : Company-wide service query. Privileges include usage access to the dashboard, services, and catalogs, as well as query access to clusters.

##### - DEVOPS : Service management via assigned members. Privileges include usage access to services and catalogs, as well as query access to clusters.



