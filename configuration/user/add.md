### 2.1.1 Add User

---

This feature allows you to add user accounts.

The user ID must be in an email format \(cocktail@example.com\). The password settings feature is not currently supported, and thus, the password must be initialized and changed after creating an ID.
\(The password automatically assigned after initialization is 'Pass0000'.\)

##### a\) Environment Settings → User → Click the [+] button in the top-right corner.![](/assets/2.5.0 환경설정 사용자 추가1.png)

##### b\)Click the [Create] button after selecting the user ID, name, and privileges.![](/assets/2.5.0 환경설정 사용자 추가2.png)

| **Privilege** | **Dashboard** | **Service** | **Catalog** | **Cluster** | **Environment Settings** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ADMIN | ⃝ | ⃝ | ⃝ | ⃝ | ⃝ |
| MANAGER | ⃝ | ⃝ | ⃝ | ⃝ | X |
| DEVOPS | X | △ | ⃝ | X | X |

##### - ADMIN : Company-wide service management. Privileges include usage access to the dashboard, services, catalogs, clusters, and environment settings.

##### - MANAGER : Company-wide service query. Privileges include usage access to the dashboard, services, and catalogs, as well as query access to clusters.

##### - DEVOPS : Service management via assigned members. Privileges include usage access to services and catalogs, as well as query access to clusters.



