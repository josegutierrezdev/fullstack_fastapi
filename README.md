# Enterprise AI Knowledge Assistant

### AI-Powered Document Search & Retrieval-Augmented Generation (RAG)

A full-stack AI knowledge management application designed to help users search, understand, and retrieve information from large collections of documents using natural language.

The project demonstrates how Retrieval-Augmented Generation (RAG), large language models, semantic search, and modern web technologies can work together to simplify enterprise knowledge discovery.

> **Portfolio Project:** This repository represents an independent demonstration of enterprise AI knowledge-assistant concepts. It does not contain proprietary code, documents, or infrastructure from any client or employer.

## Overview

Traditional enterprise search often requires employees to navigate multiple documents, internal portals, and knowledge bases to find relevant information.

This application explores a more efficient approach by combining document retrieval with AI-generated responses grounded in relevant source material.

### Key Capabilities

- **AI-Powered Question Answering:** Ask natural-language questions about uploaded documents
- **Retrieval-Augmented Generation:** Retrieve relevant document passages before generating responses
- **Semantic Search:** Find information based on meaning rather than exact keyword matches
- **Document Processing:** Extract, split, and prepare document content for indexing
- **Source References:** Associate generated responses with supporting document passages
- **Asynchronous Processing:** Support background document-processing workflows
- **Modern Web Interface:** Provide an intuitive experience for document search and knowledge discovery

## Technology Stack

| Category | Technologies |
|---|---|
| Frontend | React, TypeScript |
| Backend | Python, FastAPI |
| AI / LLM | Azure OpenAI, LangChain |
| AI Architecture | RAG, Embeddings, Semantic Search |
| Database | PostgreSQL |
| Caching | Redis |
| Background Processing | Celery |
| Infrastructure | Docker |
| Cloud & DevOps | Azure, CI/CD |

*The technologies above describe the intended reference architecture. Confirm which components are implemented in this repository.*

## System Architecture

The application follows a modular architecture separating the frontend, API layer, document-processing pipeline, retrieval system, and LLM integration.

**Document Processing Flow**

1. A user uploads a document
2. The backend extracts and validates its content
3. The content is divided into smaller searchable chunks
4. An embedding model generates vector representations
5. The resulting vectors and metadata are stored in a searchable index

**Question Answering Flow**

1. The user submits a natural-language question
2. The backend generates an embedding for the question
3. The retrieval system identifies relevant document chunks
4. The selected context is passed to an LLM
5. The application returns a generated answer with relevant source references

## Engineering Considerations

### Performance and Scalability

The architecture is designed to support efficient retrieval and document processing through:

- Asynchronous API operations
- Background processing for long-running document tasks
- Redis caching for appropriate workloads
- Database indexing and query optimization
- Containerized application components

### Reliability

Important reliability considerations include:

- Error handling and structured logging
- API request validation
- Retry handling for temporary external-service failures
- Monitoring of document-processing tasks
- Automated unit and integration testing

### Security

For production deployments, the system should include:

- Authentication and role-based access control
- Document-level access restrictions
- Secure storage of API credentials
- Encryption in transit
- Validation of uploaded files
- Protection against prompt injection and unsafe document content

## Example Use Cases

**Internal Knowledge Search**

Employees can ask questions about company policies, technical documentation, and operational procedures.

**Technical Documentation Assistant**

Engineering teams can locate implementation details and understand system documentation more efficiently.

**Customer Support Knowledge Base**

Support teams can retrieve relevant answers from product manuals, troubleshooting guides, and approved support documents.

## Example Interaction

**User Question:**

"What is the process for requesting access to a new internal application?"

**Illustrative AI Response:**

"According to the access management policy, employees should submit a request through the internal service portal, specify the required application and access level, and obtain approval from their manager."

**Source:** Access Management Policy — Section 3.2

*This is an illustrative example, not an output captured from the running application.*

## Local Development

The application
## Help needed

This project is currently experimental, so bugs or issues may occur. Please open an issue ticket against this repository to make us aware of issues and we will do our best to respond to them in a timely manner. Please leave feedback on features that would be very beneficial for developers who often leverage MongoDB in their FastAPI stack.


## Release Notes

**NOTE: There is no intention to have backwards compatibility between releases.**

See notes: 

## CalVer 2024.01.10
- Replaced Beanie usage with ODMantic
- Fixed TOTP login
- Added Page-Level route authentication
- Fixed issued with logged in user being unable to access `/settings` page
- Throw errors on every non-ok auth.ts response
- Fixed Poject Named generation in Footer.tsx
- Removed unused CORS routes
- Updated README
  - Added QuickStart
  - Added Requirements
  - Added Container URL Information
- Updated docs/
  - Placed docker_example.png
  - Removed lingering Nuxt and Beanie references
  - Updated Indexing


## CalVer 2023.11.10

- Replaced Next/Vue.js frontend framework with entirely React/Redux
- Replaced Backend native connection of PostgreSQL/SQLAlchemy with MongoDB Motor/Beanie ODM
- Removed Neo4j plugin
- Removed Alembic Usage
- Introduced new cookiecutter environment variables `mongodb_uri`, and `mongo_database`
- Introduced support for Pydantic 2

## License

This project is licensed under the terms of the MIT license.
