
## Project Description

Create a basic e-commerce system that consists of the following entities: `Product`, `Cart`, and `Order`. The system should allow users to:

- Add products to a shopping cart.
- Remove products from the shopping cart.
- Place an order with the products in the cart.
- Check the status of an order.

After implementing the e-commerce system, write JUnit test cases to verify its functionality. Mock the behavior of methods as needed to thoroughly test the system.

## Entity Descriptions

### Product

- **Attributes**: `id`, `name`, `price`.
- **Description**: The `Product` entity represents individual products available in the e-commerce system. Each product has a unique identifier (`id`), a name (`name`), and a price (`price`).

### Cart

- **Functionality**:
    - **Add a Product to the Cart**: You can add a product to the shopping cart using the `addProductToCart` method. It adds the product to the list of products in the cart.
    - **Remove a Product from the Cart**: The `removeProductFromCart` method allows you to remove a product from the cart. It also handles exceptions if the product is not in the cart.

### Order

- **Attributes**: `orderId`, `products`, `status`.
- **Functionality**:
    - **Create an Order with Products**: You can create an order using the `createOrder` method, providing the cart, order ID, and order status. It checks if the cart is empty and throws an exception if it is.
    - **Check the Status of an Order**: You can check the status of an order using the `getStatus` method.

## Methods Providing Actions and Logic

### Cart Class

1. `addProductToCart(Product product)`: This method allows you to add a `Product` to the shopping cart. It adds the product to the list of products in the cart.

2. `removeProductFromCart(Product product)`: This method allows you to remove a `Product` from the shopping cart. If the product is not in the cart, it throws an `IllegalArgumentException` to handle this exceptional case.

### Order Class

1. `createOrder(Cart cart, String orderId, String status)`: This is a factory method that creates an `Order` object. It checks if the `Cart` provided is empty (has no products). If the cart is empty, it throws an `IllegalArgumentException` with a message "You cannot create an order with an empty cart." Otherwise, it creates an `Order` with the provided `orderId` and `status`.

2. `getStatus()`: This method allows you to check the status of an order. It returns the status of the order.

## Testing

This project includes a comprehensive suite of tests to verify the functionality of the e-commerce system. The tests are written using JUnit, a popular Java testing framework, and Mockito, a mocking framework. Below, you'll find details about the tests and their methods.

### Cart Tests

1. **addProductFromCartTest**: This test case verifies the ability to add products to the shopping cart. It uses the `addProductToCart` method of the `Cart` class to add products and asserts that they were successfully added to the cart.

2. **removeProductFromCartTest**: This test case focuses on removing products from the shopping cart using the `removeProductFromCart` method.
3. **removeAbsentProductFromCartTest**: This test ensures that an `IllegalArgumentException` is thrown when attempting to remove a product that is not in the cart.

### Order Tests

1. **createOrderWithRightArgumentsTest**: This test case checks the proper creation of an order with the correct arguments. It uses the `Order.createOrder` factory method to create an order with a non-empty cart, order ID, and status.

2. **createOrderWithWrongArgumentsTest**: This test case checks the handling of exceptions when creating an order with an empty cart. It uses Mockito to mock the cart behavior, ensuring it returns an empty product list.

3. **getOrderStatusTest**: This test case verifies the functionality of checking the status of an order. It creates an order and checks that the status matches the expected value.

The tests are designed to cover various scenarios and edge cases to ensure the reliability of the e-commerce system.
