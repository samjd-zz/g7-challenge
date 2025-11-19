# CLAUDE.md - Predictive Resource Allocator

## Project Context
You are working on the **Predictive Government Resource Allocation Platform**, an AI system that helps governments anticipate future needs and optimize resource allocation for infrastructure, personnel, and funding.

## Project Goals
- **G7 GovAI Challenge**: Statement 3 - Future Needs and Resource Allocation
- **Mission**: Enable proactive resource planning through accurate predictions and optimization
- **Timeline**: 2-week MVP for competition (Nov 17 - Dec 1, 2025)
- **Target Impact**: 15-25% reduction in resource waste, 30-40% faster emergency response

## Key Architecture Components

### 1. Multi-Source Data Integration Hub
- Federal, state/provincial, municipal, and commercial data sources
- Real-time sensors and IoT devices
- Weather, traffic, shipping, scheduling data
- Historical records and trend analysis
- Standardized data formats across jurisdictions

### 2. Predictive Analytics Engine
- Infrastructure deterioration prediction models
- Population growth and migration forecasting
- Environmental impact assessment
- Demand forecasting for services
- Emergency probability modeling

### 3. Resource Optimization System
- Multi-objective optimization (cost, urgency, impact)
- Constraint satisfaction (budget, capacity, regulations)
- Scenario planning and what-if analysis
- Risk assessment and mitigation strategies
- Dynamic reallocation based on conditions

### 4. Decision Support Dashboard
- Executive strategic planning interface
- Operational manager consoles
- Field coordinator mobile apps
- Public transparency portal
- Real-time alerts for critical situations

### 5. Emergency Response Module
- Real-time disaster monitoring
- Supply chain resilience tracking
- Automated resource mobilization
- Cross-agency coordination
- Adaptive routing and logistics

## Technology Stack
- **Frontend**: React/Next.js dashboards, React Native mobile
- **Backend**: Python FastAPI (ML), Node.js (APIs)
- **ML**: PyTorch/TensorFlow, scikit-learn, Prophet, LSTM
- **Optimization**: Python OR-Tools, CVXPY, Gurobi
- **Data**: PostgreSQL, TimescaleDB (time-series), MongoDB, Redis
- **Integration**: Apache Kafka for streaming, REST/GraphQL APIs

## Critical Requirements

### Prediction Accuracy
- >70% accuracy on held-out test data
- Confidence intervals for all predictions
- Backtesting against historical outcomes
- Regular model retraining (monthly/quarterly)
- Performance monitoring and drift detection

### Data Quality
- Validation rules for all data sources
- Anomaly detection and flagging
- Missing data imputation strategies
- Conflict resolution for contradictory sources
- Data lineage tracking

### Fairness & Ethics
- No systematic bias toward affluent areas
- Equitable resource distribution
- Transparency in allocation decisions
- Community impact assessments
- Regular fairness audits

### Performance
- Real-time updates (<5 minutes for critical events)
- Sub-second query response for dashboards
- Handle millions of data points daily
- Support 1000+ concurrent users
- 99.9% system availability

## Development Approach

### AI-TDD Process
1. Define prediction metrics and baselines
2. Split data temporally (train/validation/test)
3. Implement and validate models against baseline
4. Backtest allocation strategies
5. Continuous monitoring in production

### Prediction Pipeline
```
Data Ingestion → Validation → Feature Engineering → 
Model Inference → Uncertainty Quantification → 
Optimization → Recommendation → Human Review → Action
```

### Testing Strategy
- Historical backtesting (predict past, compare to actual)
- Cross-validation with temporal splits
- Stress testing with extreme scenarios
- A/B testing of allocation strategies
- User acceptance testing with planners

## Common Scenarios to Handle

### Infrastructure Prediction
```
Input: Bridge inspection history, age, traffic, weather exposure
- Extract features from maintenance records
- Apply deterioration model
- Predict failure probability over time
- Generate maintenance recommendations
- Optimize budget allocation across bridges
```

### Emergency Response
```
Input: Hurricane warning, population density, infrastructure vulnerability
- Predict impact areas and severity
- Forecast resource needs (personnel, supplies, shelters)
- Optimize pre-positioning of resources
- Generate evacuation and supply routes
- Coordinate across agencies
```

### Multi-Objective Optimization
```
Objectives: Minimize cost, maximize coverage, minimize response time
Constraints: Budget limits, personnel capacity, regulatory requirements
- Model as multi-objective optimization problem
- Generate Pareto optimal solutions
- Present trade-offs to decision makers
- Support scenario comparison
```

## Available Documentation
- `idea.md`: Complete feature proposal and architecture
- `prd.md`: Product requirements and specifications
- `design.md`: Technical design details
- `plan.md`: Implementation roadmap
- `README.md`: Project overview

## Key Metrics to Track
- Prediction accuracy (RMSE, MAE, R²)
- Forecast bias (over/under-estimation)
- Optimization quality (vs. greedy baseline)
- Cost savings (demonstrated value)
- Response time improvements
- Resource utilization rates
- User satisfaction scores
- Fairness metrics (Gini coefficient, equity ratios)

## What Makes This Project Unique
- **Proactive vs. Reactive**: Prevent problems before they occur
- **Multi-Jurisdiction**: Integrate data across government levels
- **Real-Time Adaptive**: Respond to changing conditions dynamically
- **Evidence-Based**: Replace intuition with data-driven decisions
- **Fairness-Aware**: Explicitly optimize for equitable outcomes

## When Coding

### Always Consider
- What's the prediction confidence/uncertainty?
- How accurate is this on historical data?
- Is this fair to all communities?
- Can decision makers understand why?
- What happens if data is missing?
- Are we handling real-time updates?

### Never Do
- Deploy predictions without backtesting
- Ignore confidence intervals/uncertainty
- Optimize without fairness constraints
- Make automated decisions without human oversight
- Skip explainability for recommendations
- Ignore data quality issues
- Hard-code thresholds without validation

## Gemini API Integration
This project can use Gemini API for analyzing historical reports and trends:
- Upload historical infrastructure reports
- Extract patterns and insights
- Generate summaries of past incidents
- Inform predictive models with qualitative data
- See: https://ai.google.dev/gemini-api/docs/file-search

## Model Selection Guidelines
- **Time Series**: Prophet for seasonal patterns, LSTM for complex dependencies
- **Regression**: XGBoost for tabular data, Random Forests for interpretability
- **Classification**: Logistic regression for simple, Neural nets for complex
- **Optimization**: Linear programming for simple, Mixed-integer for complex
- **Ensemble**: Combine multiple models for robustness

## Prediction Best Practices
1. **Temporal Splits**: Never train on future data
2. **Feature Engineering**: Domain knowledge > raw data
3. **Regularization**: Prevent overfitting to historical patterns
4. **Ensemble Methods**: Multiple models more robust than single
5. **Uncertainty Quantification**: Always provide confidence intervals
6. **Continuous Learning**: Regular retraining with new data

## Questions to Ask
When implementing features, ask:
1. How accurate is this on historical data?
2. What's the confidence interval for this prediction?
3. Is this fair across different communities?
4. Can planners understand the reasoning?
5. How does this perform in extreme scenarios?
6. What happens when key data is missing?
7. How quickly can this adapt to new information?

## Success Looks Like
A system where government planners can:
- Predict infrastructure needs years in advance
- Optimize resource allocation for maximum impact
- Respond to emergencies 30-40% faster
- Reduce resource waste by 15-25%
- Make data-driven budget decisions
- Ensure fair distribution across communities
- Adapt quickly to changing conditions
- Demonstrate clear ROI on investments
