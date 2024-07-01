### Food Service application

This project was initiated during my master's studies. Even though I've finished my studies, I'm still working on and improving the app, adding new features to make it better.

Project is implemented using ReactJS (Hooks) library and Java Spring Boot framework (Hibernate, Spring Secuirty with JSON Web token, REST API) with some additional libraries (Bootstrap, AXIOS, Sweetalert, Redux and few more).

### Project specification

The main purpose of the application is to enable users to view restaurant menu, place food orders, then track the status of their orders, which can be updated by employees. The system consists of three user roles with specific capabilities:
- ADMIN
- EMPLOYEE
- USER

The application can also be accessed by unregistered users, who have the following abilities:
- Register an account
- Browse the menu, select a type of the meal, and view the complete offerings within that type
- Specify quantities and then add items to the cart
- Confirm the final order by inserting their address and phone number
- After successfully placing the final order, users will receive a message containing a link to track the status of their order

Registered users with the *USER* role can log into the system using their username and password. They have the following abilities:
- Update their personal information
- Order food similar to unregistered users, but without the need to enter their address and phone number since their data is already saved in the database.
- Receive a 10% discount on every order
- View their active orders (with *ORDERED* and *IN PREPARATION* status)
- View the history of their orders (with *IN DELIVERY* status)

Users with the *EMPLOYEE* role have the following abilities:
- Review all incoming orders and change their status to *IN PREPARATION* or *IN DELIVERY*, depending on whether the orders are being prepared or in the process of delivery.
- View the history of all orders.

Users with the *ADMIN* role have the following abilities:
- Create, delete (logically) and update meal types in the database (including uploading images)
- Create, delete (logically) and update meals (including uploading images)
- Logically delete users (change their isDeleted status, their data remains in the database)
- View active final orders
- Delete final orders and all their ordered items from the database
- View the order history
- Create, delete, and update employee data (users with the *EMPLOYEE* role)

Application has fully responsive design for users who order the food.

### Application UI preview:

Users first need to select the specific category, then they can see complete offers for that category.

![MainPage](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/bc57fdf3-e8cd-4eeb-acd4-751d65629667)

After choosing category (meal type), available meals (offers) will be listed.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/0b8f3117-2812-4b24-ab66-5e9841f4b42c)

Users can add items (meals) to the cart after they specify quantity. Default and minimum value for quantity is 1 and users can't go below that value. 
After clicking on *Confirm* button, item is successfully added to the cart.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/27c80f5b-3616-4bea-bcea-33eb1d0d0e0b)
![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/cc797f3c-b1ac-4cc4-bded-a9081f323498)

Clicking on the cart button or icon in the navigation, users can see items from the cart.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/d13a8ca6-eef5-4986-9556-6b31833a8d58)

Users that are not logged-in, need to insert details such as address and phone number.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/c09b7dd7-1fac-4577-b83a-faf795e4d5fa)

Without inserting details, not logged-in users can't confirm the final order 

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/ba76eeb8-e12b-46c7-b8bb-03a900382699)

Validation if inserted phone number is a number or it has less than 5 digits

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/c2554836-e571-4f49-933a-02b69ad1b210)
![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/7bf58263-4318-4e8a-8ce7-b36a2f996646)

After valid input, final order will be confirmed and not logged-in users can track their order status clicking on the link.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/51627eb9-c149-4859-b33a-fc8a07f80aba)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/73631c73-fe58-41c7-ac60-ef34127fca4f)

Clicking on *Show items* button, user can see all items from the (final) order that he ordered.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/a9b321ac-397e-41ce-8d67-6c646247b2ef)
![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/8284fe55-e336-483e-bda4-835c5acf38a7)

Logged-in users get 10% discount on the final price of their order. Also they don't need to insert details, such as address and phone number, because it's stored in the database after registration. Logged-in users also have more tabs and options.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/97d5e7cb-450e-467f-a382-a2e632b9b20a)

Logged-in users can track their active orders (*IN PREPARATION* and *ORDERED* status) clicking on *My active orders tab*. Final orders with *IN DELIVERY* status will be visible clicking on *My order history* tab.

Clicking on *Show items* button, user can see his ordered items

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/5f14538a-7c35-4911-ae7d-35f289e14634)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/a9d2e7fe-05bf-430e-9c25-0d044fc719b9)

Admin have option to delete final order and all its ordered items from the database, but he doesn't have an option to change status as employee can do (same component shows for both roles, but they don't have same available actions).

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/438b8159-19e2-4bfe-90cb-6e54b457094a)
![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/98da70c9-eed6-4c49-99e8-b9fce5506aca)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/77a8b579-1d34-48fd-8154-8979647a06a4)

Employee can see and change status of the final order depending on real status of the order, which user can track (but they can't delete them as Admin can do).

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/542d5342-913e-4089-b236-65a96bac0239)

Clicking on *Show items* button, employee can see all items from the (final) order.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/caae99fe-3414-412e-9147-9094c0bbfec6)

All orders with status *IN DELIVERY* are placed in order history, they aren't considered active anymore

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/e11bb8c8-31f1-4c40-9566-5274ce877b01)

Login component shows when the app starts.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/3a17c512-5f5b-43b8-a037-46bb1e1d8c1f)

Logged-in users can access their profile page where they edit profile or change password if necessary.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/f1d578de-609d-410b-b64d-6e8f5245fa9c)

Edit profile

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/7c0603cf-df88-47ec-9451-886b2f311de8)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/73e799c9-fb88-45e1-a3ca-2c9b337b2e86)

When user wants to change password, he needs to insert old password as well.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/0c902c27-ae49-4161-b454-dcac9ec0bfb3)

If inserted old password and password from the database don't match, he won't be allowed to save new password.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/7252002e-cf67-4ea2-88c0-7008a3033709)

If they match, new password will be saved successfully (will be encripted and saved in the database)

Registration (unregistered users can sign up and they will have 10% off on every order)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/dfd88fba-c89c-4658-b0ac-8a272e87a7d2)

Validation and alert if username already exists in the database.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/de4b46bd-bb6a-43b2-a1a3-f23a4c122257)

Validation and alert if email already exists in the database

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/9ca28303-b095-4c7b-b637-cf89eadaf1a7)

Admin can create new employees and manage them.
![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/9287014d-c71a-45eb-b9cc-9e6fd5db30e4)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/088fa978-2204-4fd5-bbef-df6bbf2f8b14)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/b5f794d9-fb0e-4fc5-a5e2-a4037d45dabf)

Admin can create, update, delete new mealtypes and meals.

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/0c6180aa-3ac6-4b79-9985-e000369ef0ba)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/f06159b0-c89d-4a6c-94d6-fefcb53d3cea)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/4a15f1eb-65e1-438f-9ee3-d804f58b36b2)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/e5517262-b169-4f7b-92fe-d126b5f1cd3e)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/d02c8c6a-cce4-4589-af63-f13192d93a54)

![image](https://github.com/prasadgade20/Food-Ordering-Application-frontend/assets/43978977/096bc131-e419-4348-ac8b-3465412f79e7)









