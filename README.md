<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Online Store</title>
    <style>
        /* Basic styling, you can customize this */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em;
        }
        main {
            padding: 20px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Your Online Store</h1>
    </header>
    <main>
        <h2>Welcome to our store!</h2>
        <p>Check out our amazing products below:</p>
        
        <!-- Example product listing -->
        <div class="product">
            <img src="product1.jpg" alt="Product 1">
            <h3>Product 1</h3>
            <p>Description of Product 1. Price: €20</p>
            <button onclick="addToCart('Product 1', 20)">Add to Cart</button>
        </div>

        <div class="product">
            <img src="product2.jpg" alt="Product 2">
            <h3>Product 2</h3>
            <p>Description of Product 2. Price: €25</p>
            <button onclick="addToCart('Product 2', 25)">Add to Cart</button>
        </div>

        <!-- Shopping cart -->
        <div id="shopping-cart">
            <h2>Shopping Cart</h2>
            <ul id="cart-items"></ul>
            <p>Total: <span id="cart-total">€0</span></p>
        </div>
    </main>

    <script>
        // JavaScript for adding items to the shopping cart
        let cartItems = [];
        let total = 0;

        function addToCart(productName, price) {
            cartItems.push({ name: productName, price: price });
            total += price;

            updateCart();
        }

        function updateCart() {
            let cartList = document.getElementById('cart-items');
            let totalElement = document.getElementById('cart-total');
            cartList.innerHTML = '';
            
            cartItems.forEach(item => {
                let listItem = document.createElement('li');
                listItem.textContent = `${item.name}: €${item.price}`;
                cartList.appendChild(listItem);
            });

            totalElement.textContent = `€${total.toFixed(2)}`;
        }
    </script>
</body>
</html>
