# Motioncut_Assignment3
## Assignment objective
Create a functional and visually appealing e-commerce product page using HTML and CSS.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Page</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
        }
        .header {
            background-color: #e67e22;
            color: white;
            padding: 10px 20px;
            text-align: right;
        }
        .cart-counter {
            font-size: 18px;
        }
        .container {
            display: flex;
            flex-wrap: wrap;
            max-width: 1200px;
            margin: 20px auto;
            justify-content: space-between;
        }
        .product-card {
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin: 10px;
            flex: 1 1 calc(30% - 20px); /* Adjusts to 3 products per row */
            max-width: calc(30% - 20px);
            overflow: hidden;
        }
        .product-image {
            padding: 20px;
        }
        .product-image img {
            max-width: 100%;
            border-radius: 8px;
        }
        .product-details {
            padding: 20px;
        }
        .product-name {
            font-size: 20px;
            margin-bottom: 10px;
        }
        .product-description {
            font-size: 14px;
            margin-bottom: 20px;
            line-height: 1.5;
        }
        .product-price {
            font-size: 18px;
            font-weight: bold;
            color: #e67e22;
            margin-bottom: 20px;
        }
        .add-to-cart {
            background-color: #e67e22;
            color: white;
            border: none;
            padding: 10px 15px;
            font-size: 14px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .add-to-cart:hover {
            background-color: #d35400;
        }
    </style>
</head>
<body>
 <title>Product Page</title>
    <div class="header">
        Cart: <span class="cart-counter" id="cartCounter">0</span> items
    </div>
    <div class="container" id="productContainer">
        <!-- Product Cards will be inserted here by JavaScript -->
    </div>
    <script>
        let cartCount = 0;
        const products = [
            {
                name: "Beats Headphones",
                description: "Experience the best sound quality with our stylish headphones.",
                price: "$37799.99",
                image: "https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/MQTQ3?wid=1144&hei=1144&fmt=jpeg&qlt=90&.v=1687660671363"
            },
            {
                name: "Wireless Mouse",
                description: "A sleek and ergonomic wireless mouse for your convenience.",
                price: "$799.99",
                image: "https://arcticfox.com/cdn/shop/files/White.jpg?v=1706945815&width=1946"
            },
            {
                name: "Mechanical Keyboard",
                description: "Type with precision and speed using our mechanical keyboard.",
                price: "$6599.99",
                image: "https://aulaindia.com/wp-content/uploads/2024/06/Untitled-design-6.jpg"
            },
            {
                name: "BeatXp Smartwatch",
                description: "Stay connected with our feature-rich smartwatch.",
                price: "$1199.99",
                image: "https://www.jiomart.com/images/product/original/rv0s65ihpq/beatxp-flux-1-45-round-hd-display-with-bluetooth-calling-smartwatch-always-on-display-60-hz-refresh-rate-rotary-crown-500-nits-brightness-iced-silver-product-images-orv0s65ihpq-p602997768-1-202307071527.jpg?im=Resize=(420,420)"
            },
            {
                name: "Bluetooth Speaker",
                description: "Enjoy high-quality sound with our portable Bluetooth speaker.",
                price: "$1549.99",
                image: "https://www.boat-lifestyle.com/cdn/shop/products/74a6b20d-9842-49da-b279-022812b81e1f.png?v=1673001663"
            },
            {
                name: "Lenovo Ideapad 512 Gb",
                description: "Experience mixture of comfort and technology.",
                price: "$52999.99",
                image: "https://techterms.com/img/xl/laptop_586.png"
            },
            {
                name: "Laptop Stand",
                description: "Improve your posture with our adjustable laptop stand.",
                price: "$699.99",
                image: "https://jinzo.in/wp-content/uploads/2020/07/415KtTZCr1L.jpg"
            },
            {
                name: "Apple iPhone 15 256Gb",
                description: "Expand your connectivity options with our specialized and high tech smartphone.",
                price: "$64499.99",
                image: "https://m.media-amazon.com/images/I/71d7rfSl0wL._AC_UF1000,1000_QL80_.jpg"
            },
            {
                name: "Portable SSD",
                description: "Store your data securely with our portable SSD.",
                price: "$18699.99",
                image: "https://www.onlyssd.com/wp-content/uploads/2023/03/Samsung-4TB-T7-Shield-Portable-SSD-Black.jpg"
            },
            {
                name: "Webcam",
                description: "Enhance your video calls with our high-definition webcam.",
                price: "$5999.99",
                image: "https://images-cdn.ubuy.co.in/64f09fcf6f127a351930f051-1080p-web-cam-hd-camera-webcam-with-mic.jpg"
            }
        ];
        function updateCartCounter() {
            document.getElementById('cartCounter').innerText = cartCount;
        }
        function addToCart() {
            cartCount++;
            updateCartCounter();
            alert('Item added to cart!');
        }
        function renderProducts() {
            const productContainer = document.getElementById('productContainer');
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <div class="product-image">
                        <img src="${product.image}" alt="${product.name}">
                    </div>
                    <div class="product-details">
                        <h2 class="product-name">${product.name}</h2>
                        <p class="product-description">${product.description}</p>
                        <span class="product-price">${product.price}</span>
                        <button class="add-to-cart" onclick="addToCart()">Add to Cart</button>
                    </div>
                `;
                productContainer.appendChild(productCard);
            });
        }
        renderProducts();
    </script>
</body>
</html>
```
