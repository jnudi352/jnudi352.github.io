# jnudi352.github.io

body {
    font-family: Arial, sans-serif;
    margin: 40px;
    background: #f7f7f7;
}

h1 {
    color: #333;
}

.form-box {
    background: white;
    padding: 15px;
    border-radius: 8px;
    width: 300px;
    margin-bottom: 20px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

input {
    width: 90%;
    padding: 8px;
    margin-top: 8px;
}

button {
    margin-top: 10px;
    padding: 8px 12px;
    cursor: pointer;
}

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Major Search</title>
    <link rel="stylesheet" href="styles.css" />
</head>
<body>
    <h1>Search by Major</h1>

    <div class="form-box">
        <label>Enter Major:</label><br>
        <input type="text" id="majorInput" placeholder="e.g. biology">
        <button onclick="searchMajor()">Search</button>
    </div>

    <h2>Results:</h2>
    <div id="results"></div>

    <script src="script.js"></script>
</body>
</html>

// Example database — replace with your own data
const peopleData = [
    { name: "Alice Johnson", major: "BIOLOGY", year: "2025", email: "alice@example.com" },
    { name: "Brian Smith", major: "COMPUTER SCIENCE", year: "2024", email: "brian@example.com" },
    { name: "Carlos Perez", major: "BIOLOGY", year: "2026", email: "carlos@example.com" }
];

function searchMajor() {
    let majorInput = document.getElementById("majorInput").value;

    // Convert input to ALL CAPS
    let majorUpper = majorInput.toUpperCase();

    // Filter database
    let matches = peopleData.filter(person => person.major === majorUpper);

    // Display results
    let resultsDiv = document.getElementById("results");
    resultsDiv.innerHTML = "";

    if (matches.length === 0) {
        resultsDiv.innerHTML = "<p>No matches found.</p>";
        return;
    }

    matches.forEach(person => {
        let entry = `
            <div class="result-item">
                <p><strong>Name:</strong> ${person.name}</p>
                <p><strong>Year:</strong> ${person.year}</p>
                <p><strong>Email:</strong> ${person.email}</p>
                <hr>
            </div>
        `;
        resultsDiv.innerHTML += entry;
    });
}

your-repo/
   index.html
   script.js
   styles.css
