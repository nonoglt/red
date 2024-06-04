<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub User Info</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        .profile {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>GitHub User Info</h1>
    <input type="text" id="username" placeholder="Enter GitHub username">
    <button onclick="fetchGitHubInfo()">Get Info</button>
    
    <div id="profile" class="profile"></div>

    <script>
        async function fetchGitHubInfo() {
            const username = document.getElementById('username').value;
            if (!username) {
                alert('Please enter a GitHub username');
                return;
            }

            const response = await fetch(`https://api.github.com/users/${username}`);
            if (response.ok) {
                const data = await response.json();
                displayProfile(data);
            } else {
                alert('User not found');
            }
        }

        function displayProfile(data) {
            const profileDiv = document.getElementById('profile');
            profileDiv.innerHTML = `
                <h2>${data.name} (@${data.login})</h2>
                <img src="${data.avatar_url}" alt="Avatar" width="150">
                <p><strong>Bio:</strong> ${data.bio}</p>
                <p><strong>Location:</strong> ${data.location}</p>
                <p><strong>Public Repos:</strong> ${data.public_repos}</p>
                <p><strong>Followers:</strong> ${data.followers}</p>
                <p><strong>Following:</strong> ${data.following}</p>
            `;
        }
    </script>
</body>
</html>
