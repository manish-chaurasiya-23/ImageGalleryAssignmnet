# Image Gallery

A simple image gallery application built with SwiftUI that fetches photos from an API, allows for search functionality, features a pull-to-refresh mechanism, and includes a custom input form.

## Table of Contents

## Features

- **Search Photos**: Users can search for images based on a query.
- **Infinite Scrolling**: The app loads more images automatically as the user scrolls down.
- **Pull-to-Refresh**: Users can refresh the image list by pulling down the view.
- **Custom Input Form**: Includes a form to submit user information with validation.

## How to Run the Project

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/ImageGallery.git
   cd ImageGallery


- Open the project in Xcode:
Open the ImageGallery.xcodeproj file in Xcode.

- Build and run:
Select a simulator or connect a device.
Click the "Run" button (or press Cmd + R) in Xcode.

- Libraries Used
SDWebImageSwiftUI: This library is used for loading images asynchronously from the web and caching them efficiently, which simplifies image downloading and improves performance.

- Challenges Faced
Pagination Issues: Initially, images did not load when scrolling down due to incorrect threshold checks for loading more data. This was resolved by ensuring the logic correctly identifies when the last visible image is near the end of the current list.

Asynchronous Data Handling: Managing asynchronous API calls while updating the UI state required careful consideration to avoid race conditions. SwiftUI's state management was utilized effectively to ensure the UI reflects the current data state.

- Architectural Choices
MVVM Architecture: The project follows the Model-View-ViewModel (MVVM) pattern to separate concerns:
Model: Contains data structures (Photo, ImageURLs) representing the data fetched from the API.
ViewModel: (GalleryVM) manages fetching images, handling pagination, and storing the search query and results. It also handles UI-related state management.
View: SwiftUI views that present the data and respond to user interactions.


- Description of Key Files
Photo.swift: Contains the Photo model that represents individual photo data.
ImageURLs.swift: Defines the ImageURLs model containing different sizes of the image.
GalleryVM.swift: Implements the logic for loading images, managing pagination, and searching.
GalleryView.swift: The main SwiftUI view that displays the photo gallery and includes search and input functionalities.
CustomTextField.swift: A reusable text field component with styling.

- Documentation
GalleryView: Displays images in a grid, implements search functionality, and manages user input for the form.
GalleryVM: Handles all business logic related to data fetching, pagination, and user interactions.
Photo: Represents an image with properties such as ID and URLs for various sizes.
ImageURLs: Provides different resolutions for the fetched images.
NetworkManager: A utility for making API calls.

- Future Improvements
Implement detailed error handling and user feedback for network errors.
Enhance UI design and add animations for loading states and transitions.
Consider adding features like bookmarking images or creating a user collection.

