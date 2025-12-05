---
title: "Proposal"
date: "2025-11-25"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


# GENERATIVE AI TRAVEL PLANNER
## A Conversational Itinerary Platform Using Serverless Architecture and Foundation Models

### 1. Executive Summary
The Generative AI Travel Planner is a serverless web application designed to help travelers, travel agencies, and tourism professionals create personalized travel itineraries efficiently. By inputting destination, trip duration, and interests, users receive AI-generated day-by-day plans with activities, timing, and descriptions tailored to their preferences. The platform is built on AWS services such as AWS Lambda and Bedrock to enhance user experiences in real-world applications, with potential applications in tourism businesses, travel startups, and personal trip planning.

### 2. Problem Statement
### The Problem?
Planning a multi-day trip requires significant time and effort to research destinations, coordinate activities, and create a cohesive itinerary. Travelers often spend hours browsing multiple websites, blogs, and reviews to piece together daily plans that match their interests and available time. Travel agencies and tourism professionals face similar challenges when creating customized itineraries for clients, leading to repetitive manual work. There is a need for an intelligent, automated solution that can generate personalized travel plans quickly while maintaining quality and relevance to user preferences.

### The Solution and Benefits
The platform leverages AWS Amplify to provide a fully serverless web application with continuous deployment capabilities. User requests are processed through a GraphQL API built with AWS AppSync, which communicates with AWS Lambda functions for backend logic. Amazon Bedrock with the Claude Haiku foundation model generates intelligent, context-aware itineraries based on user inputs. Amplify Auth manages user authentication and secure access to the application. The solution offers a simple HTML-based interface where users submit their destination, trip duration, and interests, then receive comprehensive day-by-day itineraries with activities, timing, and descriptions.

Key benefits include rapid itinerary generation that saves hours of manual research, personalized recommendations tailored to individual preferences, and a scalable architecture that can handle multiple concurrent users. The serverless approach ensures cost efficiency through pay-per-use pricing while demonstrating practical integration of generative AI with modern AWS services. The platform can be extended for travel agencies, tourism businesses, or personal trip planning applications.


### 3. Solution Architecture
The platform employs a serverless AWS architecture to deliver an AI-powered travel itinerary generation system. User requests flow through AWS Amplify's hosted web interface, where inputs are processed via a GraphQL API managed by AWS AppSync. Backend logic is handled by AWS Lambda functions, which interact with Amazon Bedrock to generate personalized itineraries using the Claude Haiku foundation model. User authentication and access control are managed through Amplify Auth with Amazon Cognito integration. The architecture is detailed below:

![GenAI Travel Planner Architecture](/images/Project_Architecture.drawio.png)


### AWS Services Used
- **AWS Amplify**: Hosts the HTML-based web interface with continuous deployment capabilities.
- **AWS AppSync**: Manages the GraphQL API for efficient data operations and real-time communication between frontend and backend.
- **AWS Lambda**: Executes backend processing logic and handles requests for AI-generated itineraries.
- **Amazon Bedrock**: Provides access to the Claude Haiku foundation model for intelligent itinerary generation.
- **Amazon Cognito (via Amplify Auth)**: Manages user authentication and secures application access.

### Component Design
- **Web Interface**: AWS Amplify hosts the HTML-based user interface where users input destination, trip duration, and interests, then view generated itineraries.
- **API Layer**: AWS AppSync provides a GraphQL API that facilitates communication between the frontend and backend services.
- **Backend Processing**: AWS Lambda functions handle business logic, process user requests, and coordinate interactions with other AWS services.
- **AI Generation**: Amazon Bedrock with Claude Haiku foundation model generates personalized, context-aware travel itineraries based on user inputs.
- **User Management**: Amplify Auth with Amazon Cognito manages user registration, authentication, and secure access to the application.

### 4. Technical Implementation
- **Frontend Application**: HTML-based user interface with form inputs for destination, number of days, and interests. The interface displays AI-generated itineraries in a structured format with day-by-day breakdown including activities, timing, and descriptions.
- **Backend Services**: AWS Lambda functions to handle API requests, process user inputs, and interact with Amazon Bedrock. Knowledge of AWS SDK for invoking Bedrock foundation models and constructing prompts for the Claude Haiku model.
- **API and Data Management**: AWS AppSync configuration for GraphQL API schema definition, resolvers, and data sources. Understanding of GraphQL operations to connect frontend requests with backend functions.
- **Authentication**: Amplify Auth setup with Amazon Cognito for user authentication, enabling secure registration, login, and session management with protected API endpoints.
- **AI Integration**: Practical knowledge of Amazon Bedrock API for model invocation, prompt engineering for travel itinerary generation, and response handling. Understanding of Claude Haiku model capabilities and constraints.
Deployment: AWS Amplify configuration for continuous deployment, environment management, and web application hosting.

### 5. Timeline & Milestones
**Project Timeline**
- Month 1: Study AWS foundation concepts and services
- Month 2: Plan and design project architecture
- Month 3: Develop, test and deploy
    - Week 1: AWS service setup and configuration
    - Week 2: Backend development and Bedrock integration
    - Week 3: Frontend development and API connection
    - Week 4: Testing, debugging, and deployment


### 6. Budget Estimation
<!-- You can find the budget estimation on the [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=621f38b12a1ef026842ba2ddfe46ff936ed4ab01).  
Or you can download the [Budget Estimation File](../attachments/budget_estimation.pdf). -->

### Infrastructure Costs
- AWS Services:
    - Amazon Bedrock: 2.10$/month
    - AWS Lambda: 0$/month
    - AWS Amplify: 0.27$/month
    - AWS Appsync: 0.11$/month
    - Amazon Cognito: 0.25$/month


Total: 2.73$/month, 32.76$/month


### 7. Risk Assessment
- Risk
    - Potential service quotas or regional availability issues with Amazon Bedrock in the Singapore region.
    - Hitting Bedrock or Lambda invocation limits during testing.
    - Inconsistent itinerary quality from AI model responses.
- Mitigation
    - Monitor service health dashboards.
    - Implement prompt validation and response filtering.
- Contingency
    - Use alternative AWS regions or models if primary services face limitations.
    - Create template-based fallback itineraries.


### 8. Expected Outcomes
- Fully functional serverless application deployed on AWS
- Seamless integration between Amplify, AppSync, Lambda, and Bedrock
- Effective prompt engineering for travel itinerary generation
- Optimized token usage maintaining cost under $3/month
- Reliable model responses with consistent formatting

