**Charles Liu**
Dr. Parteek Kumar
$9/25/2025$

___

### **Class Diagram**
![[Class Diagram.jpeg]]

___

### **Sequence Diagram**

![[Sequence Diagram(1).jpeg]]

___

### **GenAI-Refined Diagrams**

The AI didn't suggest any great refinements. What's different is it missed a bunch of classes as it couldn't handle the data overload. It also hallucinated a bunch of methods (e.g. updateProduct) in random places (randomly placed between Catalog and Product).


___

### **Reflection**

1. Which part of your design took the most thought or revision -- and why?

Thinking about the various component's and their interactions in the class diagram took the most thought and revision since it was the most involved.

2. Alternatives you considered for relationships/responsibilities.

I thought about whether Catalogs should or shouldn't exist without products (ended up going with should).

3. Why you chose inheritance vs. association/aggregation in specific cases.

It made sense for customers and admins to inherit from user, as both have common "user" attributes. Others aggregated (like CartItem and ShoppingCart) since they worked together, Shopping Cart uses a bunch of carts.

4. How GenAI influenced your process — did it improve, confirm, or challenge your thinking?

GenAI wasn't really helpful in my process as it had a bunch of hallucinations and couldn't handle the scope of the question. It also wasn't good at diagramming.

___