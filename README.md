<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: Georgia, 'Times New Roman', Times, serif;
            margin: 0;
            padding: 0;
            height: 44vh; /* Full height */
            overflow: hidden; /* Prevent scrolling */
            position: relative; /* Position relative for absolute children */
        }

        .background {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: url('https://www.accuramech.com/wp-content/uploads/LogoAccuramech_LARGE-scaled.jpg'); /* High-quality background image */
            background-size: cover; /* Cover the entire background */
            background-position: center; /* Center the background image */
            filter: blur(8px); /* Apply blur effect */
            z-index: 0; /* Ensure background is behind everything */
        }

        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(255, 255, 255, 0.1); /* Light white overlay with reduced opacity */
            z-index: 1; /* Ensure overlay is above the background */
        }

        .content {
            position: relative; /* Position relative for z-index */
            z-index: 1; /* Ensure content is above the overlay */
            color: hsl(216, 100%, 1%); /* Text color */
            text-align: center; /* Center the text */
            padding: 20px; /* Add some padding */
        }

        .catalogue {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
            margin: 20px 0; /* Add margin for spacing */
        }

        .product {
            border: 1px solid rgb(227, 236, 235);
            border-radius: 20px; 
            padding: 20px;
            margin: 30px;
            width: 200px;
            text-align: center;
            background-color: #97c9f4ee; /* Semi-transparent background for readability */
        }

        .pagination {
            text-align: center;
            margin: 20px 2; /* Add margin for spacing */
        }

        .pagination button {
            margin:  5px;
            padding: 15px 30px; /* Increase padding for larger buttons */
            background-color: hsl(211, 71%, 73%); /* Change to a more visible color */
            color: white;
            border: 5px solid #0056b3; /* Add a border */
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.1s, border-color 0.1s; /* Add transition for hover effect */
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Add shadow for depth */
        }

        .pagination button:hover {
            background-color: #0056b3; /* Darker blue on hover */
            border-color: #004085; /* Darker border on hover */
        }
    </style>
</head>
<body>
    <div class="background"></div> <!-- Background image with blur effect -->
    <div class="overlay"></div> <!-- Overlay for additional effect -->
    
    <div class="content">
        <div class="intro">
            <h2>ACCURAMECH</h2>
            <p> High quality Precision Mechanical Parts (Subsidiary of Verallia Group).</p>
            <p>Thank you for choosing ACCURAMECH. We look forward to serving you!</p>
        </div>

        <div class="catalogue" id="catalogue"></div>

        <div class="pagination">
            <button onclick="showCategory('variables')">VARIABLES</button>
            <button onclick="showCategory('assembly')">ASSEMBLY</button>
            <button onclick="showCategory('spareParts')">SPARE PARTS</button>
        </div>
    </div>

    <script>
        // Sample data (can replace this with data from Python backend)
        const products = {
            variables: [
                {
                    name: 'VARIABLES',
                    indexlink:'C:\Users\s8513154\description.html',
                }
            ],
            assembly: [
                {
                    name: 'ASSEMBLY',
                    indexlink:'C:\Users\s8513154\Downloads\Catlogue\Assembly(D).html',
                }
            ],
            spareParts: [
                {
                    name: 'Spare Part ',
                    indexlink:'C:\Users\s8513154\sparepart(d).html',
                }
            ]
        };

        // Function to display products based on category
        function displayProducts(category) {
            const catalogueDiv = document.getElementById('catalogue');
            catalogueDiv.innerHTML = ''; // Clear previous products
            products[category].forEach(product => {
                const productDiv = document.createElement('div');
                productDiv.className = 'product';
                productDiv.innerHTML = `
                    <h2>${product.name}</h2>
                    </a>
                    <p>
                        <a href="${product.descriptionLink}" target="_blank" style="color: white; text-decoration: underline;">
                            View Index
                        </a>
                    </p>
                `;
                catalogueDiv.appendChild(productDiv);
            });
        }

        // Function to show selected category
        function showCategory(category) {
            displayProducts(category);
        }

        // Display the first category by default
        showCategory('variables');
    </script>
    
</body>
</html>
