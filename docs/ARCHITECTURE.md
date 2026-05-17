# FinRisk Terminal — Frontend Architecture

## Architecture Style

The application follows a modular, feature-based frontend architecture.

## Layers

```text
Page Component
  ↓
Feature Facade
  ↓
Repository
  ↓
API Client
  ↓
Axios Instance
  ↓
Public API