# Overview
The code uses the Page Object Model (POM) design pattern. POM helps in creating an object repository for web elements, making the code more maintainable, reusable, and readable.

# Classes and Their Responsibilities
HomePage
FlightSearchPage
FlightResultsPage
flightPageNavigation2

# HomePage.java
The HomePage class contains methods to interact with the elements on the home page of the MakeMyTrip flights section.

-- Constructor: Initializes WebDriver and WebDriverWait.
-- closePromotionModal(): Closes the promotional modal that appears on the home page.
selectFromCity(): Selects "Bangalore" as the departure city.
selectInternationalTrip(): Selects the option for planning an international holiday.
selectRoundTrip(): Changes the trip type from "One Way" to "Round Trip".
setToCity(): Sets the destination city to "Dubai".
selectDatesAndDuration(): Clicks on the "DATES&DURATION" option to set travel dates.

# FlightSearchPage.java
The FlightSearchPage class contains methods to interact with the elements on the flight search page where the user selects travel dates and duration.

Constructor: Initializes WebDriver and WebDriverWait.
selectDecember2024(): Selects "December 2024" as the travel month.
adjustTripDuration(): Adjusts the trip duration slider to 10 days using drag-and-drop action.
applyDates(): Clicks the "Apply" button to apply the selected dates.
initiateSearch(): Clicks the "Search" button to start the search for flights.

# FlightResultsPage.java
The FlightResultsPage class contains methods to interact with the elements on the flight results page where the user sees the available flights and prices.

Constructor: Initializes WebDriver and WebDriverWait.
getTripPriceList(): Returns a list of web elements representing the prices for different dates.
getTripDateList(): Returns a list of web elements representing the dates for the corresponding prices.
selectDate(): Selects a specific date for flight availability.
areFlightsAvailable(): Checks if flights are available for the selected date.

# flightPageNavigation.java
The flightPageNavigation2 class is the main class that drives the overall process of navigating through the MakeMyTrip website to find flight prices and dates.

calculateMedian(): A utility method to calculate the median of a list of integers.
main(): The main method that orchestrates the entire workflow using the HomePage, FlightSearchPage, and FlightResultsPage classes.

# Workflow in Main Method
Setup WebDriver:

Initializes WebDriver and maximizes the browser window.
Sets timeouts for different operations.
Navigates to the MakeMyTrip flights page.
Home Page Interactions:

Creates an instance of HomePage.
Closes the promotional modal.
Selects "Bangalore" as the departure city.
Selects the international trip option.
Changes the trip type to "Round Trip".
Sets the destination city to "Dubai".
Opens the "DATES&DURATION" option.
Flight Search Page Interactions:

Creates an instance of FlightSearchPage.
Selects "December 2024" as the travel month.
Adjusts the trip duration to 10 days.
Applies the selected dates.
Initiates the flight search.
Flight Results Page Interactions:

Creates an instance of FlightResultsPage.
Retrieves the lists of trip prices and dates.
Processes the prices and dates to calculate the median price and find dates with prices lower than the median.
Identifies weekend dates and the date with the lowest price.
Selects a date based on certain criteria (weekend dates or lowest price date).
Checks if flights are available for the selected date.

Cleanup:

Closes the browser
