# 💳 Credit Card Advisor 💰

Java app using Selenium to scrape bank websites for credit card data. Spring Boot GUI matches user preferences with best card options. Simple but effective comparison system to find your ideal credit card without complex algorithms. Fast results, user-friendly interface! ✅

## Table of Contents
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Development](#development)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Features
- 🔍 **Web Scraping**: Automated collection of credit card offers from multiple bank websites
- 🔄 **Data Processing**: Standardization of credit card information for accurate comparison
- 👤 **User Profiling**: Simple form to capture user preferences and financial situation
- 🎯 **Card Matching**: Algorithm to match user profile with most suitable credit card options
- 📊 **Comparison View**: Side-by-side comparison of recommended credit cards
- 🖨️ **Export Results**: Save or print recommendation results

## Technology Stack
- **Java 11+**
- **Selenium WebDriver** for web scraping
- **Spring Boot** for application framework and GUI
- **Thymeleaf** for HTML templating
- **Bootstrap** for responsive design
- **Maven** for dependency management
- **H2/MySQL** for data storage

## Installation

### Prerequisites
- JDK 11 or higher
- Maven 3.6+
- Chrome/Firefox browser (for Selenium WebDriver)

### Steps
1. Clone the repository
   ```
   git clone https://github.com/yourusername/credit-card-advisor.git
   cd credit-card-advisor
   ```

2. Install dependencies
   ```
   mvn install
   ```

3. Configure database properties in `application.properties`
   ```
   spring.datasource.url=jdbc:mysql://localhost:3306/creditcarddb
   spring.datasource.username=root
   spring.datasource.password=yourpassword
   ```

4. Build the application
   ```
   mvn clean package
   ```

## Usage

### Running the Application
```
java -jar target/credit-card-advisor-1.0.0.jar
```
Then access the application at `http://localhost:8080`

### User Guide
1. Fill in the user profile form with financial information and preferences
2. Submit the form to initiate the search process
3. Review recommended credit cards on the results page
4. Compare details of selected cards
5. Export or save your preferred options

## Configuration

### WebDriver Setup
Update the `selenium.properties` file with your preferred browser driver:
```
webdriver.chrome.driver=path/to/chromedriver
selenium.headless=true
```

### Bank Website Configuration
Add or modify bank website scraping configurations in `banks.json`:
```json
{
  "banks": [
    {
      "name": "Example Bank",
      "url": "https://www.examplebank.com/credit-cards",
      "selectors": {
        "cardContainer": ".card-item",
        "cardName": ".card-title",
        "cardAPR": ".card-apr",
        "cardFees": ".annual-fee"
      }
    }
  ]
}
```

## Development

### Project Structure
```
src/
├── main/
│   ├── java/
│   │   └── com/creditadvisor/
│   │       ├── config/       # App configurations
│   │       ├── controller/   # MVC controllers
│   │       ├── model/        # Data models
│   │       ├── repository/   # Data access
│   │       ├── service/      # Business logic
│   │       │   └── scraper/  # Selenium scrapers
│   │       └── util/         # Utility classes
│   └── resources/
│       ├── static/           # CSS, JS files
│       └── templates/        # Thymeleaf templates
├── test/                     # Test classes
```

### Adding a New Bank
1. Create a new scraper implementation in `service/scraper/`
2. Add the bank's configuration to `banks.json`
3. Register the new scraper in `ScraperFactory.java`

## Testing
Run tests with:
```
mvn test
```

### Test Coverage
- Unit tests for service layer and matchers
- Integration tests for scrapers
- End-to-end tests for critical user flows

## Contributing
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.
