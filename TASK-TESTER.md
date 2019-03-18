# Scenario

Firstly, suspend your disbelief. This is a little contrived ;)

We (your team) have been tasked with generating more traffic to our deals page. We have had an idea that we could include a playable game in adverts on third-party sites. Completing the game successfully would allow the user to click through to a special deals page. For example we might advertise on a football related site, and offer a ‘special lowest price’ deal on a games console bundled with a popular football game. Our hypothesis is that by enticing the user to spend a few minutes playing the game, they’ll feel a sense of engagement and be more likely to purchase from the deals page.

Rather than build something from scratch, we have investigated if there are any off the shelf solutions for this and have found an open-source sudoku game that provides game functionality over an HTTP interface. If you are not familiar with the game of sudoku you can have a look here: https://en.wikipedia.org/wiki/Sudoku.

We need to assess the codebase to gain an understanding about its quality and if there are any issues that need to be addressed before we would be prepared to build new features.

# Your task

The objective of this exercise is for you to show how you would test an API and the application code.
Take testing notes on what you test, the heuristics you have used to stem test ideas, what you’ve discovered (good and bad) and any other information you deem important.

You are free to take your testing notes in any format you choose.

You are also free to use any tools you deem appropriate, but please also detail the list of tools that you do use.

Please spend no more than *90 minutes* testing this puzzle, excluding setup time.

# Running the application

## Requirements
You will need the following installed:
- Java JDK 1.8
- Maven 3

## Starting up the server
Once maven is installed, navigate into the root folder for this project (where you can find the file `pom.mxl`) and run:
```bash
mvn spring-boot:run
```
This will download the required dependencies, compile, and run the application.

## Getting started
This application presents a REST api. There are 3 resources that can be accessed through localhost at port 8080:

```
GET /board/
GET /board/{id}
PUT /board/validate
```

## Project Structure

The project is a simple Spring Boot application. 
Within the main source code, the majority of the application code is under the `game` package, including the domain model (`board`) and logic (`BoardLogic`).

The API Specific code lives under the `resource` package.
The API is defined in the `BoardResource` class. Other classes in this package provide some basic server configuration mapping and error handling configuration.

The main method for the application is under the `Application` class, in `com.ebay.epd.soduku`.

Tests are provided under the `test` source package.

Maven configuration for the project, including dependencies, is provided in the `pom.xml` file. 
