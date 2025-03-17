# Modern Angular 19 E-commerce App

This project is a **simple two-page e-commerce application** built using **Angular 19** [1]. It showcases modern Angular features and best practices for building an online store [2].

## Overview

This e-commerce application consists of a product list and a shopping cart [2]. It's designed to demonstrate modern Angular development techniques, including the new control flow syntax and the Signals API [2, 3].

## Key Features

*   **Built with Angular 19** [1, 2].
*   **Two-page application** with a product list and a cart view [2].
*   **Utilizes the new Angular control flow** (`@for`, `@if`, `@else`) for rendering lists and conditional content [4].
*   Employs **Signals API** for reactive data management [3, 5-7].
*   Includes **computed signals** for derived data [8, 9].
*   Uses **string interpolation** for dynamic data display [4, 10-12].
*   Features **reusable components** like buttons (`PrimaryButtonComponent`, `NormalButtonComponent`) and product cards (`ProductCardComponent`) [4, 13-16].
*   Demonstrates **component communication** using `@Input` and `@Output` signals [17-20].
*   Styled with **Tailwind CSS**, a utility-first CSS framework [21-23].
*   Manages application state using **Angular Services** (`CardService`) for the shopping cart functionality [24-26].
*   Implements **client-side routing** using `RouterModule`, `Routes`, `routerLink`, and `router-outlet` for navigation between the product list (`/`) and the cart (`/cart`) [27-31].
*   Demonstrates **asynchronous data fetching** using the `fetch` API to retrieve product data from a fake online store API [32, 33].

## Technologies Used

*   **Angular CLI**: For project generation and component/service creation [34-41].
*   **TypeScript**: As the primary programming language [42-44].
*   **HTML**: For component templates [42, 45].
*   **Sass**: As the CSS preprocessor [27, 46, 47].
*   **Tailwind CSS**: For styling [21, 47-49].
*   **Node Package Manager (npm)**: For managing project dependencies [34, 35].

## Project Structure

The application source code is organized within the `src/app` directory with the following structure:

*   **`components`**: Contains reusable UI building blocks like `header`, `primary-button`, and `button` [14, 50].
*   **`pages`**: Holds components that represent different application views, such as `products-list` and `card` [51-53].
*   **`models`**: Defines data interfaces, like `product.model.ts` [44, 54].
*   **`services`**: Encapsulates business logic and manages state, for example, `card.service.ts` [41, 55].
*   **`app.component.ts`**: The root application component [30, 56, 57].
*   **`app.config.ts`**: For application-level configurations [56].
*   **`app.routes.ts`**: Defines the application's routing configuration [27, 53, 58].
*   **`styles.sass`**: The global stylesheet [27, 47].

## Component Architecture

Key components in the application include:

*   **`AppComponent`**: Sets up the main application layout with the header and the `router-outlet` [3, 30, 59, 60].
*   **`HeaderComponent`**: Displays the application title and the cart button with the number of items [22, 24, 26, 61-63].
*   **`ProductListComponent`**: Fetches and displays a list of products using the `@for` control flow and the `ProductCardComponent` [2, 32, 51, 53, 64-67].
*   **`ProductCardComponent`**: Renders individual product details, including image, title, price, and an "Add to Cart" button, and conditionally displays stock status [18, 68-72].
*   **`PrimaryButtonComponent`**: A customizable primary action button used for "Add to Cart" [4, 17, 26, 39, 59, 62, 73].
*   **`CardPageComponent`**: Displays the items in the shopping cart using the `CartItemComponent` and includes the `OrderSummaryComponent` [2, 53, 74-76].
*   **`CartItemComponent`**: Represents a single item in the cart with details and a "Remove" button [20, 77, 78].
*   **`NormalButtonComponent` (`ButtonComponent`)**: A standard button used for the "Remove" action in the cart [50, 79].
*   **`OrderSummaryComponent`**: Calculates and displays the total order summary using a computed signal [32, 80-82].

## State Management

*   **Signals**: Used within components like `ProductListComponent` (`products` signal) for managing local component state [54, 64].
*   **CardService**: A singleton service that manages the shopping cart state (`cart` signal) and provides methods to add and remove items [24, 25, 55, 75, 76, 83, 84]. Components inject this service to interact with the cart state [26, 76, 83, 84].
*   **Computed Signals**: In `OrderSummaryComponent` to calculate the total price based on the `cart` signal [9].

## Styling

*   **Tailwind CSS**: Utilized extensively for styling components through utility classes directly in the HTML templates [21-23, 49].
*   **Global Styles**: `styles.sass` imports Tailwind directives, making its utility classes available globally [27, 47].
*   **Component-Specific Styles**: While Tailwind is the primary approach, components can also have their own specific styles defined within their `.component.ts` files or separate style files if needed [42, 85, 86].

## Routing

*   **`app.routes.ts`**: Configures the application's routes [53, 58].
    *   `''` (empty path) is mapped to `ProductListComponent` [53, 58, 87].
    *   `'cart'` path is mapped to `CardPageComponent` [53, 74].
*   **`router-outlet`**: In `app.component.ts`, this component acts as a placeholder where the routed component is rendered [30, 88].
*   **`routerLink`**: Used in the `HeaderComponent` on the cart button to enable navigation to the `/cart` route [31].

## Data Fetching

*   The `ProductListComponent` demonstrates fetching product data from a fake API endpoint using the `fetch` API [32, 33, 89].
*   The fetched data is then processed (and potentially mapped to the `Product` interface) before updating the `products` signal [33, 90].

## Reusability

*   Components like `PrimaryButtonComponent` and `NormalButtonComponent` are designed to be reusable across the application with different labels and functionalities via `@Input` signals [4, 13-16, 50].
*   The `ProductCardComponent` is reused within the `ProductListComponent` to display individual product information [68, 69].
*   The use of services (`CardService`) promotes reusability of business logic and state management across different components [24].

## Development server

To start a local development server, run:

```bash
ng serve
```

Once the server is running, open your browser and navigate to `http://localhost:4200/`. The application will automatically reload whenever you modify any of the source files.

## Code scaffolding

Angular CLI includes powerful code scaffolding tools. To generate a new component, run:

```bash
ng generate component component-name
```

For a complete list of available schematics (such as `components`, `directives`, or `pipes`), run:

```bash
ng generate --help
```

## Building

To build the project run:

```bash
ng build
```

This will compile your project and store the build artifacts in the `dist/` directory. By default, the production build optimizes your application for performance and speed.

## Running unit tests

To execute unit tests with the [Karma](https://karma-runner.github.io) test runner, use the following command:

```bash
ng test
```

## Running end-to-end tests

For end-to-end (e2e) testing, run:

```bash
ng e2e
```

Angular CLI does not come with an end-to-end testing framework by default. You can choose one that suits your needs.

## Additional Resources

For more information on using the Angular CLI, including detailed command references, visit the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.
