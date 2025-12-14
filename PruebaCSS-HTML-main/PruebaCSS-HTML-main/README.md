# Portfolio 

#  By JEFERSON ESCUDERO RUA
#  CLAN LINUS | LJEFERR@gmail.com | ID: 1000306313

This repository hosts the final module project—a personal portfolio website designed to showcase professional skills, projects, and accomplishments. The portfolio is built with modern web development practices to create a responsive, engaging, and user-friendly experience.

The main goal of this project is to provide a clean, interactive, and modern portfolio that highlights your work and experiences. The website is structured into several key sections:

Home: A landing page that introduces the portfolio.

About Me: A detailed biography describing personal and professional background.

Projects: A showcase of past work and projects, including descriptions, images, and links.

Contact: A section with a contact form or details, making it easy for potential employers or clients to get in touch.


# Features
  Responsive Design: Fully optimized for various devices including desktops, tablets, and smartphones.
  
  Modern UI/UX: Emphasis on a clean and contemporary layout with intuitive navigation.
  
  Interactive Elements: Hover effects, and other interactive components to enhance the user experience.
  
  Project Showcase: A dedicated section for displaying project details with visuals and links.
  
  Contact Integration: Ready-to-use contact form enabling easy communication from visitors.

# Technologies Used

  HTML5 – For semantic and well-structured webpage content.
  
  CSS3 – For styling and layout.
  
 # Run the website:

  Open the index.html file directly in your browser or use a local development server like Live Server in VS Code.

Bye


// Inventory object
let Inventory = {
    popcorn: { Price: 5.10, Quantity: 10 },
    coke: { Price: 20.30, Quantity: 3 },
    chocoramo: { Price: 15.40, Quantity: 10 },
    sparkies: { Price: 1.00, Quantity: 30 },
    lolete: { Price: 0.00, Quantity: 1 },
};

// AddProducts
function AddProducts(Inventory) {
    // Introduce name of the product
    while (true) {
        console.log("------------------------------------------");
        let Product = prompt("Introduce the Product name: ").toLowerCase().trim();
        if (["exit", "end", "finish"].includes(Product)) {
            console.log("------------------------------------------");
            console.log("Exiting...");
            return;
        } else if (!Product) {
            console.log("------------------------------------------");
            console.log("Product name cannot be empty");
            continue;
        } else if (Product in Inventory) {
            console.log("------------------------------------------");
            console.log("That product already exists");
            console.log("------------------------------------------");
        } else {
            console.log("------------------------------------------");
            console.log(`Product ${Product.charAt(0).toUpperCase() + Product.slice(1)} added`);
            break;
        }
    }
    // Looking for a Valid Product Price   
    while (true) {
        let Price = prompt("Introduce the price of the product: ").trim();
        if (["exit", "end", "finish"].includes(Price)) {
            console.log("------------------------------------------");
            console.log("Exiting...");
            return;
        } else if (!Price) {
            console.log("Introduce a Price pls");
            continue;
        } else if (isNaN(Price) || !/^\d*\.?\d*$/.test(Price)) {
            console.log("Price must be a number, no letters");
        } else {
            Price = parseFloat(Price);
            if (Price <= -1) {
                console.log("Price must be greater than 0");
            } else {
                console.log(`Price of ${Product.charAt(0).toUpperCase() + Product.slice(1)} added`);
                break;
            }
        }
    }
    // Looking for a Valid Product Quantity    
    while (true) {
        let Quantity = prompt("Enter the Product quantity: ").trim();
        if (["exit", "salir", "end"].includes(Quantity)) {
            console.log("----------");
            console.log("Exiting...");
            return;
        } else if (!Quantity) {
            console.log("------------------------------------------");
            console.log("Quantity cannot be empty");
        } else if (!/^\d+$/.test(Quantity)) {
            console.log("Quantity must be a valid number");
        } else {
            Quantity = parseInt(Quantity);
            if (Quantity <= -1) {
                console.log("Quantity must be greater than 0");
            } else {
                console.log(`Quantity of ${Product.charAt(0).toUpperCase() + Product.slice(1)} added`);
                break;
            }
        }
    }
    // Saving Data
    Inventory[Product] = { Price: Price, Quantity: Quantity };
    console.log("------------------------------------------");
    console.log(`Product ${Product.charAt(0).toUpperCase() + Product.slice(1)} added with Price $${Price.toFixed(2)} and quantity: ${Quantity}`);
    return Inventory;
}

// AskProductsDetails
function AskProductsDetails(Inventory) {
    console.log("Enter the name of the Product to search or type 'exit' to return to the menu: ");
    while (true) {
        let Product = prompt("Enter the name of the Product to search: ").toLowerCase().trim();
        if (["exit", "salir", "end"].includes(Product)) {
            console.log("----------");
            console.log("Exiting...");
            return;
        } else if (!Product) {
            console.log("------------------------------------------");
            console.log("Product name cannot be empty");
            console.log("------------------------------------------");
        } else if (Product in Inventory) {
            let Details = Inventory[Product];
            console.log("------------------------------------------");
            console.log(`Product: ${Product.charAt(0).toUpperCase() + Product.slice(1)} | Price: $${Details.Price.toFixed(2)} | Quantity: ${Details.Quantity}`);
            break;
        } else {
            console.log("------------------------------------------");
            console.log(`The Product ${Product.charAt(0).toUpperCase() + Product.slice(1)} is not in the inventory. Please try again or exit`);
            console.log("------------------------------------------");
        }
    }
}

// Update Product Information by option
function UpdateProductInfo() {
    FullInventory();
    while (true) {
        console.log("------------------------------------------");
        // Looking for product
        let LookForProduct = prompt("Enter the name of the product to update or type 'exit' to return to the menu: ").toLowerCase().trim();
        if (["salir", "exit", "end"].includes(LookForProduct)) {
            console.log("----------");
            console.log("Exiting...");
            return;
        } else if (!LookForProduct) {
            console.log("------------------------------------------");
            console.log("The name cannot be empty");
        } else if (LookForProduct in Inventory) {
            while (true) {
                // Choose an option
                let WhatYouWantToChange = prompt("What do you want to change? Price/Quantity: ").toLowerCase().trim();
                if (["salir", "exit", "end"].includes(WhatYouWantToChange)) {
                    console.log("----------");
                    console.log("Exiting...");
                    return;
                } else if (["price", "precio", "value", "valor"].includes(WhatYouWantToChange)) {
                    while (true) {
                        let ChangePrice = prompt("What is the new price? ").trim();
                        if (!ChangePrice) {
                            console.log("Can't be none");
                        } else if (isNaN(ChangePrice) || !/^\d*\.?\d*$/.test(ChangePrice)) {
                            console.log("No letters");
                        } else {
                            ChangePrice = parseFloat(ChangePrice);
                            if (ChangePrice <= -1) {
                                console.log("Price must be greater than 0");
                            } else {
                                Inventory[LookForProduct].Price = ChangePrice;
                                console.log("------------------------------------------");
                                console.log(`The price of ${LookForProduct.charAt(0).toUpperCase() + LookForProduct.slice(1)} has been updated to $${ChangePrice.toFixed(2)}`);
                                return;
                            }
                        }
                    }
                } else if (["quantity", "cantidad", "stock"].includes(WhatYouWantToChange)) {
                    while (true) {
                        let ChangeQuantity = prompt("What is the new quantity? ").trim();
                        if (!ChangeQuantity) {
                            console.log("Can't be none");
                        } else if (!/^\d+$/.test(ChangeQuantity)) {
                            console.log("No letters");
                        } else {
                            ChangeQuantity = parseInt(ChangeQuantity);
                            if (ChangeQuantity < -1) {
                                console.log("The quantity cannot be less than 0, or are you giving it away?");
                            } else {
                                Inventory[LookForProduct].Quantity = ChangeQuantity;
                                console.log("------------------------------------------");
                                console.log(`The quantity of ${LookForProduct.charAt(0).toUpperCase() + LookForProduct.slice(1)} has been updated to ${ChangeQuantity}`);
                                return;
                            }
                        }
                    }
                } else {
                    console.log("Please follow instructions and enter an option");
                }
            }
        } else {
            console.log("------------------------------------------");
            console.log(`The product ${LookForProduct.charAt(0).toUpperCase() + LookForProduct.slice(1)} is not in the inventory`);
        }
    }
}

// Delete Products
function DelProduct(Inventory) {
    if (Object.keys(Inventory).length > 0) {
        console.log("------------------------------------------");
        console.log("Inventory:");
        console.log("------------------------------------------");
        for (let Product in Inventory) {
            console.log(`-> ${Product.charAt(0).toUpperCase() + Product.slice(1)}`);
        }
        while (true) {
            let Eliminar = prompt("Enter the name of the product to delete or type exit to return to the menu: ").toLowerCase().trim();
            console.log("------------------------------------------");
            if (["salir", "exit"].includes(Eliminar)) {
                console.log("Exiting...");
                break;
            } else if (Eliminar in Inventory) {
                delete Inventory[Eliminar];
                console.log(`Product ${Eliminar.charAt(0).toUpperCase() + Eliminar.slice(1)} removed`);
                break;
            } else if (!Eliminar) {
                console.log("The name cannot be empty");
                console.log("------------------------------------------");
            } else {
                console.log(`The product ${Eliminar.charAt(0).toUpperCase() + Eliminar.slice(1)} is not in the inventory`);
                console.log("------------------------------------------");
            }
        }
    } else {
        console.log("------------------------------------------");
        console.log("No products in the inventory");
    }
}

// TotalValue first checks the inventory then calculates the total value
function TotalValue(Inventory) {
    if (Object.keys(Inventory).length === 0) {
        console.log("------------------------------------------");
        console.log("No products in the inventory");
        return 0.0;
    }
    let value = Object.values(Inventory).reduce((sum, details) => sum + details.Price * details.Quantity, 0);
    console.log("------------------------------------------");
    console.log(`Total value of the inventory: $${value.toFixed(2)}`);
    return value;
}

// FullInventory displays the entire inventory
function FullInventory() {
    if (Object.keys(Inventory).length === 0) {
        console.log("------------------------------------------");
        console.log("No products in the inventory");
    } else {
        console.log("------------------------------------------");
        console.log("This is the list of products in the inventory");
        console.log("------------------------------------------");
        for (let Product in Inventory) {
            let details = Inventory[Product];
            console.log(`Product: ${Product.charAt(0).toUpperCase() + Product.slice(1)} | Price: $${details.Price.toFixed(2)} | Quantity: ${details.Quantity}`);
        }
    }
}

// Menu
function Menu() {
    while (true) {
        console.log("------------------------------------------");
        console.log("Welcome to the inventory management system");
        console.log("------------------------------------------");
        console.log("1. Add Products");
        console.log("2. Search for product");
        console.log("3. Update product info");
        console.log("4. Delete product");
        console.log("5. Total stock value");
        console.log("6. Show Full Inventory");
        console.log("7. Exit | End | Finish | Close");
        console.log("------------------------------------------");
        let Option = prompt("Select an option to proceed: ").toLowerCase().trim();
        switch (Option) {
            case "1":
            case "add products":
            case "addproducts":
            case "add":
                AddProducts(Inventory);
                break;
            case "2":
            case "search":
            case "search product":
            case "ask for product":
            case "searchproduct":
            case "ask":
                AskProductsDetails(Inventory);
                break;
            case "3":
            case "uptadate product":
            case "update":
            case "updateproduct":
                UpdateProductInfo();
                break;
            case "4":
            case "delete":
            case "delproduct":
            case "delete product":
            case "deleteproduct":
            case "del":
                DelProduct(Inventory);
                break;
            case "5":
            case "total":
            case "total value":
            case "totalvalue":
                TotalValue(Inventory);
                break;
            case "6":
            case "show":
            case "showfullinventory":
            case "show full":
                FullInventory();
                break;
            case