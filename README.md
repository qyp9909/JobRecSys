# MF-based Job Recommendation System

A large-scale job recommendation system that integrates offline model training and real-time recommendation services. The system is designed to provide personalized job recommendations with high accuracy and low latency (<300ms).

Hybrid recommendation: combines offline matrix factorization with online real-time retrieval.

Large-scale data support: processes 100k+ job listings and 10k+ companies.

Low-latency serving: optimized with Redis caching.

Full-stack deployment: backend API + frontend UI for search, login, and personalized recommendations.

## System Architecture
The system follows a three-layer architecture:

### Data Layer
```
Data collection:

- Web crawling from job platforms.

Data storage:

- Relational DB: MySQL for structured data.
- NoSQL: MongoDB for unstructured job descriptions.
```

### Computation Layer
```
Offline module:

- Matrix Factorization (MF) with PyTorch to learn latent user-job vectors.
- Generates global recommendation lists.

Online module:

- Real-time candidate retrieval with cosine similarity over latent vectors.
- Personalized ranking adjustment.
- Redis caching for sub-300ms response.
```

### Application Layer
```
Backend:

- SpringBoot (Java) for RESTful APIs.
- Integration with Redis and MongoDB.

Frontend:

- React (JavaScript, HTML/CSS) for web interface.
- Functions: user login, job search, recommendation results, job details page.
```
