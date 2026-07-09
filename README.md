# rule-hive
RuleHive is a powerful, flexible rule engine framework built on Spring Boot that enables developers to define, manage, and execute business rules efficiently. Inspired by the organized nature of a beehive, RuleHive provides a structured yet adaptable environment for complex rule processing.

## Architecture Overview

The Rule Hive ecosystem is designed to be modular, scalable, and easy to manage. It consists of four main components that work together to provide an end-to-end solution for rule creation, deployment, execution, and monitoring.

### 1. Rule Hive Studio

The **Studio** is a web-based, visual editor for creating and managing rulebooks.
*   **Visual Workflow:** Provides an n8n-style canvas where users can build logic by connecting nodes (Triggers, Conditions, Actions).
*   **Real-time Feedback:** A "Data River" flows through the canvas, allowing users to see how their rules affect the data in real-time.
*   **Rulebook Persistence:** Workflows are saved as JSON objects, which can be stored in the browser, downloaded, or published to the Rule Registry.

### 2. The Hive Engine

The **Engine** is a lightweight, embeddable runtime that executes the rulebooks.
*   **Headless & Portable:** It's a standalone library (e.g., a Java JAR, NPM package) designed to be embedded in any application—backend, frontend, or serverless function.
*   **Efficient Execution:** Its sole purpose is to take a rulebook JSON and input data, execute the logic at high speed, and return the result.
*   **Decoupled:** The Engine is completely decoupled from the Studio, fetching its rulebooks from the Rule Registry.

### 3. The Rule Registry

The **Registry** is the central source of truth for all published rulebooks.
*   **Centralized Storage:** A cloud-based server that stores all versioned rulebook JSONs.
*   **Versioning & Publishing:** The Studio publishes new rulebook versions to the Registry. Each version gets a unique, stable ID.
*   **Deployment Control:** Production applications using the Hive Engine fetch their rulebooks from the Registry, ensuring they are always running the correct, published version.

### 4. The Honeycomb Dashboard

The **Dashboard** is a real-time mission control for monitoring deployed rulebooks.
*   **Observability:** Provides a web-based dashboard to visualize the health and performance of all running Hive Engines.
*   **Telemetry:** Engines send telemetry (e.g., rules executed, latency, errors) to the Dashboard.
*   **Insights:** Allows developers and business users to understand rule performance, spot errors, and gain insights into their automated decisions.
