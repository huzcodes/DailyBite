# DailyBite Docs

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Welcome to the official documentation repository for **DailyBite**  an open-source application designed to deliver daily food inspiration. Whether you're cooking at home or deciding where to order from, DailyBite helps you make that choice with a smart, AI-powered engine.



## Project Overview

**DailyBite** is a modern food suggestion platform that leverages intelligent APIs and clean architecture to provide personalized meal ideas. The application supports both home-cooked recipes and recommendations for takeout options 
all tailored to the user’s language and preferences.



## Architecture & Technical Flow

### - Authentication
- **People API** handles authentication and authorization.
- Uses [`huzcodes.Extensions`](https://www.nuget.org/packages/huzcodes.Extensions) for JWT generation.

### - Recipe Logic
- **Recipes API** processes requests after authentication.
- Users provide:
  - Preferred **language**
  - Preference to **cook** or **order**
- Application calls **OpenAI API** with those parameters.
- Results are:
  - Stored in a **SQL Database**
  - Tagged with a **unique key** to prevent duplication
  - Archived after 30 days, with the option to reuse or regenerate

### - Internal Communication
- A **gRPC Skeleton Service** facilitates communication between People API and Recipes API.

### - Frontend
- **Web App**: Built with **Blazor**
- **Mobile App**: Built with **.NET MAUI**

<br/>

## Architecture Diagram

![image](https://github.com/user-attachments/assets/d1590196-0e7c-4f20-bd6d-22804d769b73)

<br/>

## Installation

To install DailyBite, follow these steps:

1. Clone the repository: `git clone https://github.com/YOUR_USERNAME/dailybite-docs.git`
2. Install .NET 8 SDK.
3. Build and run the project using `dotnet run`.

## Contributing

We welcome contributions from the community! If you'd like to contribute to DailyBite, please follow these guidelines:

1. Fork the repository  
2. Create a new branch (`git checkout -b feature-branch`)  
3. Make your changes  
4. Commit your changes (`git commit -am 'Add new feature'`)  
5. Push to the branch (`git push origin feature-branch`)  
6. Create a new Pull Request

## License

DailyBite is licensed under the MIT License. See [LICENSE](LICENSE) for more information.

## Contact

For questions or feedback, please contact Ahmed Hussain aka huzcodes at huzcodes@outlook.com.
