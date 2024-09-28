'''mermaid
erDiagram
  PRODUCT |{--|| SALE : "purchases recorded"
  PRODUCT |{--|| INVENTORY : "restock shelves"
  PRODUCT {
    string modelNumber PK
    string model 
    string price
    string quantity
  }
  CUSTOMER ||..|{ PRODUCT : purchases
  CUSTOMER ||..}| SALE : "details recorded"
  CUSTOMER {
    string receiptNumber PK,UK
    string firstName
    string lastName
    string paymentMethod
    string nikeMembershipID UK "Optional"
  }
  SALE |{--|| INVENTORY : "report sold product"
  SALE {
    string productModelNumber PK,FK
    string purchaseQuantity FK
    string customerReceiptNumber FK,UK
    string customerFirstName FK
    string customerLastName FK
    string nikeMembershipID FK,UK "Optional"
    
  }
  INVENTORY {
    string productModelNumber PK,FK
    string modelStock
    string missingStock
    string inboundStock
  }
  
'''

# Nike Store Element Relationships
======
#### The Four Elements
*Product: The specific shoes models being sold at the Nike store.
*Customer: The individuals that purchase shoes and identifiying details.
*Sale: Transaction record for purchases.
*Inventory: Represents the quantity of remaining product for each model of shoe.

#### Relationships
The Product and Customer relationship connects buyers to the specific models of shoes bought
The Product and Sale relationship covers the documentation of what shoes are being bought and in what quantity
The Customer and Sale relationship records the information of who is buying the product
The Sale and Inventory relationship keeps track of how many shoes need to be reordered due to sold product
The Inventory and Product relationship ensures there is product available to be sold and stock ready to stowed on empty shelves.


