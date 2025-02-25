# HBnB Architecture Design

## Overview
The architecture of the HBnB application follows a **three-layered architecture** with the **Facade pattern** used to simplify interactions between these layers. The layers are:

1. **Presentation Layer (API/Services)**: Handles the interaction between the user and the application.
2. **Business Logic Layer (Models)**: Contains the core models and the application-specific logic.
3. **Persistence Layer**: Manages data access and persistence operations.

The **Facade pattern** provides a unified interface for interacting with these layers, abstracting away the complexities of the underlying interactions.

## Layers and Their Responsibilities

### 1. Presentation Layer
- **Responsibilities**: 
  - Exposes the user-facing services and API endpoints.
  - Interacts directly with the user (or client-side application) via service requests.
  - Examples: REST API endpoints, controllers for handling user interactions.
  
- **Key Components**:
  - `ServiceAPI`: The public interface exposed to the user.
  - `Controller`: Handles user requests and forwards them to the business logic layer.

### 2. Business Logic Layer
- **Responsibilities**:
  - Contains the core business models and logic for the application.
  - Interacts with the persistence layer to fetch, create, update, or delete data.
  
- **Key Components**:
  - `UserModel`: Represents user entities in the system.
  - `PlaceModel`: Represents places (e.g., properties) in the system.
  - `ReviewModel`: Represents user reviews for places.
  - `AmenityModel`: Represents amenities associated with places.
  - `BusinessLogicService`: Contains the logic for managing models and interacting with the persistence layer.

### 3. Persistence Layer
- **Responsibilities**: 
  - Manages database operations like retrieving, updating, or deleting data.
  - Encapsulates database logic and abstracts it from other layers.

- **Key Components**:
  - `UserRepository`: Handles data access for the `UserModel`.
  - `PlaceRepository`: Handles data access for the `PlaceModel`.
  - `ReviewRepository`: Handles data access for the `ReviewModel`.
  - `AmenityRepository`: Handles data access for the `AmenityModel`.
  - `DatabaseConnection`: Manages the database connection and interaction.

## Facade Pattern

The **Facade pattern** simplifies the interaction between the user and the internal layers of the application. Instead of exposing complex interfaces from the business logic or persistence layers, the **Facade** class provides a simplified, unified interface.

- **Facade API**:
  - `createUser()`: Creates a new user in the system.
  - `getPlace()`: Retrieves information about a specific place.
  - `addReview()`: Adds a new review for a place.

The **Facade** acts as an intermediary, allowing the **Presentation Layer** to make high-level requests without needing to understand the internal workings of the **Business Logic Layer** or **Persistence Layer**.

## Communication Between Layers
- The **Presentation Layer** communicates with the **Facade** for interactions with the user.
- The **Facade** handles communication with the **Business Logic Layer** to perform tasks like creating users or adding reviews.
- The **Business Logic Layer** interacts with the **Persistence Layer** via repositories to fetch or persist data.

## Benefits of the Facade Pattern
- **Simplifies the client-side interaction**: The client only needs to interact with the facade, rather than dealing directly with each layer.
- **Decouples layers**: The client and the business logic layer are decoupled, which allows changes to one layer without affecting others.
- **Encapsulates complexity**: The facade hides the complexity of the underlying layers and provides a clean and simple API.

## Conclusion
The use of a three-layered architecture with the Facade pattern provides a clean separation of concerns in the HBnB application. It ensures that each layer has a clear responsibility, making the application easier to maintain and scale.
# HBnB Architecture Design

## Overview
The architecture of the HBnB application follows a **three-layered architecture** with the **Facade pattern** used to simplify interactions between these layers. The layers are:

1. **Presentation Layer (API/Services)**: Handles the interaction between the user and the application.
2. **Business Logic Layer (Models)**: Contains the core models and the application-specific logic.
3. **Persistence Layer**: Manages data access and persistence operations.

The **Facade pattern** provides a unified interface for interacting with these layers, abstracting away the complexities of the underlying interactions.

## Layers and Their Responsibilities

### 1. Presentation Layer
- **Responsibilities**: 
  - Exposes the user-facing services and API endpoints.
  - Interacts directly with the user (or client-side application) via service requests.
  - Examples: REST API endpoints, controllers for handling user interactions.
  
- **Key Components**:
  - `ServiceAPI`: The public interface exposed to the user.
  - `Controller`: Handles user requests and forwards them to the business logic layer.

### 2. Business Logic Layer
- **Responsibilities**:
  - Contains the core business models and logic for the application.
  - Interacts with the persistence layer to fetch, create, update, or delete data.
  
- **Key Components**:
  - `UserModel`: Represents user entities in the system.
  - `PlaceModel`: Represents places (e.g., properties) in the system.
  - `ReviewModel`: Represents user reviews for places.
  - `AmenityModel`: Represents amenities associated with places.
  - `BusinessLogicService`: Contains the logic for managing models and interacting with the persistence layer.

### 3. Persistence Layer
- **Responsibilities**: 
  - Manages database operations like retrieving, updating, or deleting data.
  - Encapsulates database logic and abstracts it from other layers.

- **Key Components**:
  - `UserRepository`: Handles data access for the `UserModel`.
  - `PlaceRepository`: Handles data access for the `PlaceModel`.
  - `ReviewRepository`: Handles data access for the `ReviewModel`.
  - `AmenityRepository`: Handles data access for the `AmenityModel`.
  - `DatabaseConnection`: Manages the database connection and interaction.

## Facade Pattern

The **Facade pattern** simplifies the interaction between the user and the internal layers of the application. Instead of exposing complex interfaces from the business logic or persistence layers, the **Facade** class provides a simplified, unified interface.

- **Facade API**:
  - `createUser()`: Creates a new user in the system.
  - `getPlace()`: Retrieves information about a specific place.
  - `addReview()`: Adds a new review for a place.

The **Facade** acts as an intermediary, allowing the **Presentation Layer** to make high-level requests without needing to understand the internal workings of the **Business Logic Layer** or **Persistence Layer**.

## Communication Between Layers
- The **Presentation Layer** communicates with the **Facade** for interactions with the user.
- The **Facade** handles communication with the **Business Logic Layer** to perform tasks like creating users or adding reviews.
- The **Business Logic Layer** interacts with the **Persistence Layer** via repositories to fetch or persist data.

## Benefits of the Facade Pattern
- **Simplifies the client-side interaction**: The client only needs to interact with the facade, rather than dealing directly with each layer.
- **Decouples layers**: The client and the business logic layer are decoupled, which allows changes to one layer without affecting others.
- **Encapsulates complexity**: The facade hides the complexity of the underlying layers and provides a clean and simple API.

## Conclusion
The use of a three-layered architecture with the Facade pattern provides a clean separation of concerns in the HBnB application. It ensures that each layer has a clear responsibility, making the application easier to maintain and scale.

