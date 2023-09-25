# JSAssignment
![Login_Screen_Screenshot](https://github.com/lavanya032/JSAssignment/assets/144023989/a2e3c5d6-f18d-4f49-904b-3b4029c3dcba)
![Dashboard_Screen_Screenshot](https://github.com/lavanya032/JSAssignment/assets/144023989/5db57d95-ce15-4eb0-b891-21a1e2f01b0b)
![Edit Update_Screen_Screenshot](https://github.com/lavanya032/JSAssignment/assets/144023989/2b99dbef-0875-4260-994b-8e380f99fcca)

```html
<!-- Login Page -->
<!DOCTYPE html>
<html lang="en">
<head>
  
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
</head>
<body style="font-family: Arial, sans-serif; background-color: #f4f4f4; text-align: center; padding: 100px;">

    <div style="background-color:#ddecf0
                ; width: 300px; margin: 0 auto; padding: 20px; border-radius: 5px; box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);">
        <h2>Login</h2>
        <form style="text-align: left;">
            <div style="
                        margin-bottom: 10px;">
                <label for="username">Username:</label>
                <input type="text" id="username" style="width:50%; padding: 5px; border: 1px solid #ccc; border-radius: 3px;" required>
            </div>
            <div style="margin-bottom: 10px;">
                <label for="password">Password:</label>
                <input type="password" id="password" style="width: 50%; padding: 5px; border: 1px solid #ccc; border-radius: 3px;" required>
            </div>
              <script src="app.js"></script>
            <div>
                <button type="submit" style="background-color: #007BFF; color: white; border: none; padding: 10px 20px; border-radius: 3px; cursor: pointer;">Login</button>
            </div>
        </form>
    </div>

</body>
</html>
<!-- Dashboard Screen-->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Dashboard</title>
</head>
<body style="font-family: Arial, sans-serif; background-color: #f4f4f4; text-align: center; padding: 20px;">

    <div style="background-color: white; width: 80%; margin: 0 auto; padding: 20px; border-radius: 5px; box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);">
        <h2>User Dashboard</h2>
        <table style="width: 100%; border-collapse: collapse;">
            <thead>
                <tr>
                    <th style="padding: 10px; background-color: #007BFF; color: white;">Name</th>
                    <th style="padding: 10px; background-color: #007BFF; color: white;">Email</th>
                    <th style="padding: 10px; background-color: #007BFF; color: white;">Action</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="padding: 10px;">John Doe</td>
                    <td style="padding: 10px;">john@example.com</td>
                    <td style="padding: 10px;"><button style="background-color: #007BFF; color: white; border: none; padding: 5px 10px; border-radius: 3px; cursor: pointer;">Edit</button></td>
                </tr>
                <tr>
                    <td style="padding: 10px;">Jane Smith</td>
                    <td style="padding: 10px;">jane@example.com</td>
                    <td style="padding: 10px;"><button style="background-color: #007BFF; color: white; border: none; padding: 5px 10px; border-radius: 3px; cursor: pointer;">Edit</button></td>
                  <script src="app.js"></script>
                </tr>
                <!-- Add more user rows as needed -->
            </tbody>
        </table>
    </div>

</body>
</html>

<!--Edit&Update Screen -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edit User</title>
</head>
<body style="font-family: Arial, sans-serif; background-color: #f4f4f4; text-align: center; padding: 20px;">

    <div style="background-color: white; width: 300px; margin: 0 auto; padding: 20px; border-radius: 5px; box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);">
        <h2>Edit User</h2>
        <form style="text-align: left;">
            <div style="margin-bottom: 10px;">
                <label for="newName">New Name:</label>
                <input type="text" id="newName" style="width: 100%; padding: 5px; border: 1px solid #ccc; border-radius: 3px;" required>
            </div>
            <div style="margin-bottom: 10px;">
                <label for="newEmail">New Email:</label>
                <input type="email" id="newEmail" style="width: 100%; padding: 5px; border: 1px solid #ccc; border-radius: 3px;" required>
            </div>
              
            <div>
                <button type="button" onclick="updateUser()" style="background-color: #007BFF; color: white; border: none; padding: 10px 20px; border-radius: 3px; cursor: pointer;">Update</button>
            </div>
        </form>
    </div>

    <script>
        function updateUser() {
            // Get the new name and email values
            var newName = document.getElementById("newName").value;
            var newEmail = document.getElementById("newEmail").value;

            // Perform the update (you can implement your logic here)
            alert("User updated successfully!\nNew Name: " + newName + "\nNew Email: " + newEmail);
        }
    </script>
<script src="app.js"></script>
</body>
</html>
```

```javascript
document.addEventListener("DOMContentLoaded", () => {
    const loginForm = document.getElementById("login-form");
    const dashboardContainer = document.querySelector(".dashboard-container");
    const editUserButton = document.getElementById("edit-user-button");
    const editForm = document.getElementById("edit-form");

    // Sample user data
    const users = [
        { id: 1, name: "John Doe", email: "john@example.com" },
        { id: 2, name: "Jane Smith", email: "jane@example.com" },
        // Add more user data here
    ];

    // Function to populate the user dashboard
    function populateUserDashboard() {
        const userTable = document.getElementById("user-table");
        const tbody = userTable.querySelector("tbody");

        tbody.innerHTML = "";

        users.forEach((user) => {
            const row = document.createElement("tr");
            row.innerHTML = `
                <td>${user.name}</td>
                <td>${user.email}</td>
                <td><button class="edit-button" data-id="${user.id}">Edit</button></td>
            `;
            tbody.appendChild(row);
        });
    }

    // Function to show the dashboard
    function showDashboard() {
        dashboardContainer.style.display = "block";
        loginForm.style.display = "none";
        editForm.style.display = "none";
        populateUserDashboard();
    }

    // Function to edit a user
    function editUser(userId) {
        const userToEdit = users.find((user) => user.id === userId);

        if (!userToEdit) {
            return;
        }

        const newName = prompt("Enter new name:", userToEdit.name);
        const newEmail = prompt("Enter new email:", userToEdit.email);

        if (newName !== null && newEmail !== null) {
            userToEdit.name = newName;
            userToEdit.email = newEmail;
            populateUserDashboard();
        }
    }

    // Event listeners
    loginForm.addEventListener("submit", (e) => {
        e.preventDefault();

        // Implement authentication logic here (e.g., check username and password)
        // For simplicity, always show the dashboard for now
        showDashboard();
    });

    editUserButton.addEventListener("click", () => {
        showDashboard();
        editForm.style.display = "block";
    });

    document.addEventListener("click", (e) => {
        if (e.target.classList.contains("edit-button")) {
            const userId = parseInt(e.target.getAttribute("data-id"), 10);
            editUser(userId);
        }
    });
```

















