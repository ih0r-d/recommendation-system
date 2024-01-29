# Database Structure

## User Service Database

### Users Table
- Stores information about registered users.
- Columns:
  - `user_id`: Unique identifier for each user (primary key).
  - `username`: User's username.
  - `password`: User's hashed password.
  - `email`: User's email address.
  - `created_at`: Timestamp indicating when the user account was created.
  - `updated_at`: Timestamp indicating when the user account was last updated.

### User Activity Table
- Tracks user activity on the platform.
- Columns:
  - `activity_id`: Unique identifier for each activity (primary key).
  - `user_id`: Foreign key referencing the `user_id` in the Users table.
  - `activity_type`: Type of activity (e.g., browsing, purchasing).
  - `activity_timestamp`: Timestamp indicating when the activity occurred.
  - Additional columns can be added based on the specific types of activities being tracked (e.g., product ID for product browsing).

## Product Service Database

### Products Table
- Stores information about products available in the e-commerce platform.
- Columns:
  - `product_id`: Unique identifier for each product (primary key).
  - `name`: Name of the product.
  - `description`: Description of the product.
  - `category`: Category of the product.
  - `price`: Price of the product.
  - `inventory`: Quantity of the product in stock.
  - `created_at`: Timestamp indicating when the product was added to the platform.
  - `updated_at`: Timestamp indicating when the product information was last updated.

### Product Views Table
- Tracks views of each product by users.
- Columns:
  - `view_id`: Unique identifier for each view (primary key).
  - `product_id`: Foreign key referencing the `product_id` in the Products table.
  - `user_id`: Foreign key referencing the `user_id` in the Users table.
  - `view_timestamp`: Timestamp indicating when the product was viewed by the user.

## Recommendation Service Database

### User Preferences Table
- Stores user preferences for product recommendations.
- Columns:
  - `user_id`: Foreign key referencing the `user_id` in the Users table (primary key).
  - Additional columns representing user preferences (e.g., preferred categories, brands).

### Recommendations Table
- Stores personalized product recommendations for users.
- Columns:
  - `recommendation_id`: Unique identifier for each recommendation (primary key).
  - `user_id`: Foreign key referencing the `user_id` in the Users table.
  - `product_id`: Foreign key referencing the `product_id` in the Products table.
  - `recommended_at`: Timestamp indicating when the recommendation was generated.

## Notification Service Database

### Notifications Table
- Stores notifications sent to users.
- Columns:
  - `notification_id`: Unique identifier for each notification (primary key).
  - `user_id`: Foreign key referencing the `user_id` in the Users table.
  - `message`: Content of the notification.
  - `sent_at`: Timestamp indicating when the notification was sent.

