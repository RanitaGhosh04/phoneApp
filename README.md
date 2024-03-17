Phone Hunting Web Application-

 This is a web application that allows users to search for phones and view their details using an external API. Users can enter search queries to find specific phones and access detailed information about them.

Features
 -Search Functionality: Users can search for phones by entering keywords in the search bar.
-Dynamic Loading: A loading spinner is displayed while fetching phone data from the API.
-Responsive Design: The application is designed using Tailwind CSS, ensuring a responsive and visually appealing layout.
-Show All Button: Users can choose to display all available phones by clicking the 'Show All' button.
-Modal Display: Detailed information about each phone is displayed in a modal when the 'Show Details' button is clicked.

How to Use
-Clone this repository to your local machine.
-Open the index.html file in your web browser.
-Enter search queries in the search bar to find specific phones.
-Click on the 'Show Details' button to view detailed information about a phone.
-Optionally, click the 'Show All' button to display all available phones.


Technical Implementation

1. searchHandler(isShowAll):
-Purpose: This function handles the search functionality triggered when the user clicks the search button.
-Parameters:
 isShowAll: An optional boolean parameter indicating whether to show all results. Defaults to false.

Steps:
-Retrieve the search text entered by the user from the input field with the id searchField.
-Call the loading(true) function to display the loading spinner.
-Call the loadPhone() function with the search text and isShowAll parameter.

2. loading(isLoading):
-Purpose: This function toggles the visibility of the loading spinner.
-Parameters:
 isLoading: A boolean parameter indicating whether to show (true) or hide (false) the loading spinner.
 Steps:
 Retrieve the loading spinner element by its id (loading).
 If isLoading is true, remove the 'hidden' class from the loading spinner to display it. If isLoading is false, add the 'hidden' class to hide the loading spinner.

3. loadPhone(searchText, isShowAll):
-Purpose: This function fetches phone data from an API based on the provided search text.
-Parameters:
 searchText: The search query entered by the user.
 isShowAll: A boolean parameter indicating whether to show all results.
 Steps:
-Construct the API URL with the search query.
-Fetch the data using the fetch() function.
-Upon receiving the data, extract the phone information from the response.
-Call the displayPhones() function to render the phone cards on the webpage.

5. displayPhones(phones, isShowAll):
-Purpose: This function dynamically creates HTML elements for each phone fetched from the API and displays them on the webpage.
-Parameters:
 phones: An array containing phone data fetched from the API.
 isShowAll: A boolean parameter indicating whether to show all results.
Steps:
-Clear the existing content of the phone container.
-Check if the number of phones is greater than 12 and whether isShowAll is false. If so, show the 'Show All' button.
-Limit the number of displayed phones to 12 if isShowAll is false.
-For each phone, create a card element with relevant details like image, name, and a button to show details.
-Call the loading(false) function to hide the loading spinner.

6. showBtn():
-Purpose: This function handles the 'Show All' button functionality.
Steps:
-Simply calls the searchHandler(true) function, indicating that all phones should be displayed.
8. showDetailsHandler(id):
-Purpose: This function fetches detailed information about a specific phone when its 'Show Details' button is clicked.

Parameters:
-id: The unique identifier of the phone.
Steps:
-Construct the API URL to fetch detailed information about the phone.
-Fetch the data using the fetch() function.
-Upon receiving the data, call the showPhoneDetails() function to display the details in a modal.

10. showPhoneDetails(details):
-Purpose: This function populates the modal with the details of the selected phone.
Parameters:
-details: An object containing information about the phone.
Steps:
-Retrieve various elements in the modal by their ids and populate them with corresponding phone details, such as name, brand, specifications, release date, and image.
-These functions work together to provide a seamless user experience for searching and displaying phone details on the webpage. Each function has a specific role in handling different aspects of the application's functionality.




