# rewardpoints
# Reward Points Calculation API

## Overview
This project provides a REST API to calculate reward points based on transactions. The API is built using Spring Boot and exposes endpoints to calculate rewards for given transactions.

## Features
- Calculate reward points based on transaction amounts.
- Mock transactions for demonstration purposes.
- RESTful endpoints for easy integration.

## Technologies Used
- Java
- Spring Boot
- Maven

## Getting Started

### Prerequisites
- Java 11 or higher
- Maven
- Spring Tool Suite (STS) or any IDE of your choice

### Installation
1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   ```
# Navigate to the project directory

cd rewardpoints
# Build the project:
mvn clean install

# Running the Application
1.Run the Application
  mvn spring-boot:run
# Access the API:
Open your browser or API client (e.g., Postman) and navigate to:
http://localhost:8080/api/rewards/calculate

# API Endpoints
Calculate Rewards
Endpoint: /api/rewards/calculate
Method: GET
Description: Calculates reward points for mock transactions.
Response:
{
  "1": {
    "JANUARY": 90,
    "FEBRUARY": 40
  },
  "2": {
    "JANUARY": 150,
    "MARCH": 250
  }
}
# Example Usage
@GetMapping("/calculate")
public Map<Long, Map<Month, Integer>> getRewards() {
    List<Transaction> mockTransactions = List.of(
        new Transaction(1L, 120.0, LocalDate.of(2025, 1, 15)),
        new Transaction(1L, 90.0, LocalDate.of(2025, 2, 10)),
        new Transaction(2L, 150.0, LocalDate.of(2025, 1, 20)),
        new Transaction(2L, 200.0, LocalDate.of(2025, 3, 5))
    );

    return rewardService.calculateRewards(mockTransactions);
}


