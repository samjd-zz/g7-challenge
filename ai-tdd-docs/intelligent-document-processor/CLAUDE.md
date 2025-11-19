# CLAUDE.md - Intelligent Document Processor

## Project Context
You are working on the **Intelligent Document Processing & Knowledge Management System**, an AI-powered platform that transforms how public servants manage, process, and access vast volumes of unstructured information.

## Project Goals
- **G7 GovAI Challenge**: Statement 1 - Managing High Volumes of Information
- **Mission**: Dramatically reduce manual document processing time while improving information accessibility
- **Timeline**: 2-week MVP for competition (Nov 17 - Dec 1, 2025)
- **Target Impact**: 60-75% reduction in research time, 40-50% faster case processing

## Key Architecture Components

### 1. Intelligent Document Ingestion
- Multi-format support: PDF, Word, Excel, PowerPoint, emails, images, HTML
- OCR for scanned documents (98%+ accuracy)
- Batch processing with parallel pipelines
- Real-time ingestion from monitored sources
- Version control and duplicate detection

### 2. AI-Powered Classification & Categorization
- Document type identification (reports, memos, policies, etc.)
- Department/program routing
- Topic/subject multi-label classification
- Sensitivity level detection
- Urgency identification

### 3. Theme & Insight Identification
- Topic modeling to discover recurring themes
- Named entity recognition (people, organizations, locations)
- Sentiment analysis
- Relationship mapping between entities
- Trend detection over time

### 4. Semantic Search Engine
- Natural language queries
- Hybrid search (keyword + vector)
- Multi-lingual search capability
- Faceted filtering and relevance ranking
- Question answering with source citations

### 5. Intelligent Summarization
- Extractive and abstractive summaries
- Multi-document synthesis
- Query-focused summaries
- Executive summaries for leadership
- Action item extraction

### 6. Knowledge Management
- Centralized repository with version control
- Automatic knowledge graph construction
- Document relationships and dependencies
- Collaboration tools and annotations

## Technology Stack
- **Frontend**: React/Next.js web portal, React Native mobile
- **Backend**: Python FastAPI microservices, Node.js event processing
- **AI**: Hugging Face Transformers, GPT-4/Claude, Gemini API for RAG
- **Search**: Elasticsearch (full-text) + Pinecone/Weaviate (vectors)
- **Database**: PostgreSQL, Neo4j (knowledge graph), Redis (caching)
- **Queue**: Apache Airflow/Celery for job orchestration

## Critical Requirements

### Document Processing
- Support all common government document formats
- Maintain document structure (tables, formatting, metadata)
- Extract text with >98% OCR accuracy
- Process 10,000+ documents per hour
- Handle documents up to 1000+ pages

### AI Accuracy
- Classification precision >85%
- Search relevance >80% precision@10
- Summarization quality >4/5 user rating
- Confidence scores for all predictions
- Human review workflow for low-confidence results

### Security & Compliance
- Government security classifications support
- End-to-end encryption
- Role-based access control (RBAC)
- Complete audit trails
- FOIA/Access to Information compliance
- No PII in logs or analytics

### Performance
- Search response <500ms (p95)
- Ingestion throughput: 100+ docs/hour
- Summarization: 5-10 seconds per document
- System uptime: 99.9%
- Support 10,000+ concurrent users

## Development Approach

### AI-TDD Process
1. Define test datasets with labeled government documents
2. Establish accuracy baselines before implementation
3. Implement with continuous testing against benchmarks
4. Validate with real-world document variations
5. A/B test model improvements

### Document Processing Pipeline
```
Ingest → Format Detection → Text Extraction → Quality Check → 
Metadata Extraction → Classification → Embedding Generation → 
Index → Store → Make Searchable
```

### Testing Strategy
- Unit tests for all processing functions
- Integration tests for end-to-end document flow
- Performance tests at scale (100K+ documents)
- Accuracy validation against labeled datasets
- Security and access control testing
- User acceptance testing with public servants

## Common Scenarios to Handle

### Multi-Format Document Processing
```
Intake: Mix of PDFs, Word docs, scanned images, emails
- Detect format automatically
- Apply appropriate parser
- Extract text and structure
- Normalize to common format
- Index for search
```

### Semantic Search Query
```
User query: "Find all memos about climate policy from Q4"
- Parse natural language query
- Extract entities: doc type (memos), topic (climate policy), date (Q4)
- Hybrid search: keyword + semantic
- Filter by metadata
- Rank by relevance
- Return top 10 with snippets
```

### Document Summarization
```
Input: 200-page policy report
- Chunk document intelligently
- Identify key sections
- Extract important sentences
- Generate abstractive summary
- Highlight action items
- Provide citations
```

## Available Documentation
- `idea.md`: Complete feature proposal and architecture
- `prd.md`: Product requirements and specifications
- `design.md`: Technical design details
- `plan.md`: Implementation roadmap
- `README.md`: Project overview

## Key Metrics to Track
- Document processing throughput (docs/hour)
- OCR accuracy (% correct character recognition)
- Classification accuracy (precision/recall/F1)
- Search relevance (precision@10, MRR, nDCG)
- Summarization quality (ROUGE, human ratings)
- User satisfaction (ratings, usage patterns)
- Time savings (before/after comparison)

## What Makes This Project Unique
- **Government-Specific**: Trained on public sector documents and workflows
- **Hybrid Intelligence**: Combines AI automation with human expertise
- **Security-First**: Built for sensitive government information
- **Scalable**: Handles millions of documents across departments
- **Continuous Learning**: Improves from user feedback and corrections

## When Coding

### Always Consider
- Is this secure for sensitive documents?
- What's the processing throughput?
- Are confidence scores provided?
- Is there human review for uncertain cases?
- Are audit trails maintained?
- Is PII properly handled?

### Never Do
- Process documents without security classification checks
- Store unencrypted sensitive information
- Skip OCR quality validation
- Ignore document version history
- Expose PII in search results or logs
- Deploy models without bias testing
- Skip performance benchmarking

## Gemini API Integration
This project uses Gemini API's file search capabilities for RAG:
- Upload large document collections
- Automatic chunking and embedding
- Semantic search across documents
- Context-aware Q&A
- Multi-document synthesis
- See: https://ai.google.dev/gemini-api/docs/file-search

## Model Selection Guidelines
- **Classification**: Fine-tuned BERT/RoBERTa for government documents
- **NER**: SpaCy with custom entity types
- **Embeddings**: Sentence-BERT or OpenAI embeddings
- **Summarization**: BART, T5, or GPT-4 for abstractive
- **OCR**: Tesseract or AWS Textract for scanned documents

## Questions to Ask
When implementing features, ask:
1. What's the accuracy on government documents?
2. How fast can this process 10,000 documents?
3. Is this secure for classified information?
4. Can users explain why they got these results?
5. What happens when confidence is low?
6. Are we preserving document context and relationships?

## Success Looks Like
A system where public servants can:
- Upload thousands of documents automatically
- Find any information in seconds, not hours
- Get accurate summaries without reading entire documents
- Discover patterns and insights across document collections
- Make better decisions with complete information
- Spend 60-75% less time searching for documents
