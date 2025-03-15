# 🍰 Dessert Shop

A visually appealing and interactive **Dessert Shop** web application that allows users to browse delicious desserts, add them to their cart, and dynamically adjust quantities before confirming an order.

---

## 📌 Features

- ✅ **Dynamic Dessert Display** - Desserts are loaded dynamically from a `data.json` file.
- ✅ **Add to Cart Functionality** - Users can add items to their cart with a single click.
- ✅ **Quantity Adjustment** - Users can increase or decrease item quantities within the cart.
- ✅ **Total Price Calculation** - The cart updates the total price dynamically as items are added or adjusted.
- ✅ **Responsive Design** - Works seamlessly across different screen sizes.
- ✅ **Order Confirmation** - A confirmation message is displayed when the order is placed.
- ✅ **Smooth UI Animations** - Hover effects and cart interactions enhance user experience.

---

## 🏗️ Tech Stack

- **HTML** - Structure
- **CSS** - Styling
- **JavaScript** - Functionality

---

## 📂 Project Structure
```
DessertShop/
│── assets/
│   ├── fonts/             # Custom fonts
│   ├── images/            # Dessert images
│   ├── data.json          # Dessert data
│── styles.css             # Stylesheet
│── script.js              # JavaScript functionality
│── index.html             # Main HTML file
│── README.md              # Documentation
```

---

## 🚀 Getting Started

### **1️⃣ Clone the Repository**
```sh
git clone https://github.com/yourusername/DessertShop.git
cd DessertShop
```

### **2️⃣ Open the Project**
Simply open `index.html` in a browser, or start a local server:
```sh
python3 -m http.server
```
Then visit `http://localhost:8000` in your browser.

### **3️⃣ Ensure the `data.json` File is Loaded**
Make sure `data.json` is inside the `assets/` folder and accessible at:
```
http://localhost:8000/assets/data.json
```

---

## 🛠️ Functionality Breakdown

### **📌 Load Desserts from JSON**
The desserts are loaded dynamically using JavaScript:
```js
fetch("./assets/data.json")
  .then(response => response.json())
  .then(data => displayDesserts(data));
```

### **🛒 Add to Cart Functionality**
```js
function addToCart(name, price) {
    let item = cart.find(i => i.name === name);
    if (item) {
        item.quantity++;
    } else {
        cart.push({ name, price, quantity: 1 });
    }
    updateCartDisplay();
}
```

### **➕ Quantity Adjustment**
```js
function changeQuantity(name, amount) {
    let item = cart.find(i => i.name === name);
    if (item) {
        item.quantity += amount;
        if (item.quantity <= 0) {
            cart = cart.filter(i => i.name !== name);
        }
        updateCartDisplay();
    }
}
```

### **✅ Confirm Order & Reset**
```js
function confirmOrder() {
    document.getElementById("order-confirmation").classList.remove("hidden");
}
function startNewOrder() {
    cart = [];
    updateCartDisplay();
    document.getElementById("order-confirmation").classList.add("hidden");
}
```

---

## 🎨 UI Design
The design is inspired by modern e-commerce layouts, ensuring a visually **clean, minimalist, and responsive** interface.

---

## 💡 Future Enhancements
- 🔹 **Save cart items in local storage** for persistence.  
- 🔹 **Discount codes & promotions**.  
- 🔹 **Dark mode toggle**.  

---

## 👩‍💻 Author
Developed by **Viola Ranjha** - Feel free to contribute!

📌 **GitHub Repo**: [https://github.com/yourusername/DessertShop](https://github.com/yourusername/DessertShop)

