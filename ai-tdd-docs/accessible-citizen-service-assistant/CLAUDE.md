# CLAUDE.md - Accessible Citizen Service Assistant

## Project Context
You are working on the **Accessible Citizen Service Assistant**, an AI-powered platform designed to transform how citizens interact with government services by providing personalized, culturally sensitive, and accessible communication across all channels.

## Project Goals
- **G7 GovAI Challenge**: Statement 4 - Accessible Government Communication
- **Mission**: Reduce barriers in government interactions for all citizens regardless of language, culture, or abilities
- **Timeline**: 2-week MVP for competition (Nov 17 - Dec 1, 2025)
- **Target Impact**: 70% reduction in accessibility barriers, 50-70% time reduction for form completion

## Key Architecture Components

### 1. Multi-Modal Interface Layer
- Web portal, mobile apps, voice interface, SMS/chat, video sign language
- WCAG AAA compliant with adaptive UI
- Support for 100+ languages with real-time translation

### 2. Intelligent Communication Engine
- Natural language processing with intent recognition
- Multi-lingual support with dialect handling
- Context maintenance across sessions and channels

### 3. Information Ingestion & Verification
- Document upload with OCR and image analysis
- Voice transcription to structured data
- External verification with fraud detection

### 4. Form Completion Assistant
- Auto-fill from verified documents
- Field-by-field guidance in plain language
- Real-time validation and error prevention

### 5. Communication Drafting Support
- Email/letter generation with cultural adaptation
- Meeting preparation guides and role-play
- Rights and options explanation

### 6. Accessibility Adaptation System
- Visual, audio, motor, and cognitive disability support
- Personalized accessibility profiles
- Neurodiversity accommodations

## Technology Stack
- **Frontend**: React with accessibility libraries (react-aria, radix-ui)
- **Backend**: FastAPI (Python) or Node.js
- **AI**: Gemini API for multilingual RAG and translation
- **Speech**: Whisper, Azure TTS, ElevenLabs
- **Database**: PostgreSQL (metadata), MongoDB (conversations), Redis (sessions)

## Critical Requirements

### Accessibility (Non-Negotiable)
- WCAG 2.2 Level AAA compliance required
- Screen reader compatibility (NVDA, JAWS, VoiceOver)
- Keyboard navigation for all features
- 7:1 contrast ratio for text
- Support for assistive technologies

### Multilingual Support
- Translation accuracy >95% for pilot languages
- Cultural localization, not just word-for-word translation
- Handle code-switching and multiple dialects
- Plain language principles for all content

### Security & Privacy
- End-to-end encryption for personal information
- Minimal data retention
- GDPR/PIPEDA compliance
- Consent management for data sharing

## Development Approach

### AI-TDD Process
1. Define accessibility and translation test cases first
2. Test with diverse user scenarios (various disabilities, languages)
3. Validate with actual assistive technologies
4. Implement with accessibility built-in from start

### Testing Strategy
- Automated accessibility testing (axe-core, pa11y)
- Manual testing with screen readers
- User testing with diverse populations
- Performance testing with assistive technologies
- Translation quality validation

## Common Scenarios to Handle

### Multi-Modal Interaction
```
Citizen starts on web, continues via SMS, completes on phone call
- Maintain context across all channels
- Adapt UI/communication style per channel
- Sync data seamlessly
```

### Language Switching
```
User speaks Spanish, needs form in English
- Translate interface to Spanish
- Provide guidance in Spanish
- Generate form in required language
- Explain each field in user's language
```

### Accessibility Adaptation
```
User with visual impairment + low tech literacy
- Optimize for screen reader
- Simplify language further
- Provide audio descriptions
- Large click targets for any visual elements
```

## Available Documentation
- `idea.md`: Complete feature proposal and architecture
- `prd.md`: Product requirements and specifications
- `design.md`: Technical design details
- `plan.md`: Implementation roadmap
- `README.md`: Project overview

## Key Metrics to Track
- WCAG AAA compliance: 100%
- Translation accuracy: >95%
- Form completion rate: >80%
- User satisfaction: 4.5/5
- Time savings: 50-70% reduction
- Barrier reduction: 70% fewer reported barriers

## What Makes This Project Unique
- **Truly Universal Access**: Not just compliant, but genuinely usable by everyone
- **Cultural Intelligence**: Understanding context, not just translating words
- **Multi-Modal by Design**: Every feature works across voice, text, video
- **Empowerment Focus**: Help citizens confidently interact with government
- **Equity Driven**: Prioritize underserved populations

## When Coding

### Always Consider
- Can this be used with only keyboard?
- Does this work with a screen reader?
- Is the language simple enough for low literacy?
- Does this respect cultural differences?
- Is personal data minimized?

### Never Do
- Mouse-only interactions
- English-only labels or messages
- Complex jargon without explanation
- Assume specific abilities or tech access
- Store unnecessary personal information

## Gemini API Integration
This project uses Gemini API's file search capabilities for RAG:
- Upload government documents and forms
- Enable semantic search across regulations
- Generate plain language explanations
- Provide context-aware form assistance
- See: https://ai.google.dev/gemini-api/docs/file-search

## Questions to Ask
When implementing features, ask:
1. How does this work for someone who is blind?
2. How does this work for someone who doesn't speak English?
3. How does this work for someone with cognitive disabilities?
4. How does this work for someone with limited tech skills?
5. Have we tested this with actual diverse users?

## Success Looks Like
A platform where EVERY citizen, regardless of language, culture, or ability, can:
- Understand what services they're eligible for
- Complete applications successfully on first try
- Get help in their preferred language and format
- Feel confident and empowered in government interactions
