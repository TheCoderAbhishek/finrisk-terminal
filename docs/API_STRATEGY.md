# FinRisk Terminal — API Strategy

## API Providers

| Provider | Purpose | Key Required |
|---|---|---|
| SEC EDGAR | Company filings and facts | No |
| World Bank | Macro indicators | No |
| NASA POWER | Climate variables | No |
| NASA EONET | Natural events | No |
| Open-Meteo | Weather and climate data | No |
| FRED | Economic indicators | Optional |
| OpenAQ | Air quality | Optional |

## API Design Rules

- All HTTP calls go through the centralized Axios instance.
- All errors are normalized into a common error model.
- All public API responses are mapped into app-specific models.
- Components must not directly call API clients.
- Repositories are responsible for cache-aware data access.
- Facades orchestrate multiple repositories.
- API keys must not be hardcoded.
- Optional API keys are entered by the user and stored locally only.

## Required Axios Interceptors

1. Correlation ID interceptor
2. Timing interceptor
3. Retry interceptor
4. Error normalization interceptor
5. Rate-limit awareness interceptor
6. Cache interceptor
7. Mock session interceptor