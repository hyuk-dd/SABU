
## 클러스터링 API
기능 분류 | 기능 설명 | HTTP Method | Endpoint | PID | Request 예시 | Response 예시
-- | -- | -- | -- | -- | -- | --
종목 검색 | Ticker로 종목 검색 | GET | /search/ticker | CLU-001 | json { "query": "AAPL" } | json { "results": [ { "ticker": "AAPL", "name": "Apple Inc." } ] }
종목 검색 | 클러스터 번호로 종목 검색 | GET | /search/cluster | CLU-001 | json { "clusterId": 3 } | json { "results": [ { "ticker": "TSLA", "name": "Tesla Inc." } ] }
ETF 상세 | 특정 Ticker의 ETF 정보 조회 | GET | /etf/{ticker} | CLU-002 | 없음 (URL Path 사용) | json { "ticker": "SPY", "holdings": [...], "financials": {...} }
클러스터링 | 사용자가 담은 종목의 클러스터링 결과 조회 | POST | /cluster/analyze | CLU-004 | json { "tickers": ["AAPL", "GOOG", "TSLA"] } | json { "clusters": { "0": ["AAPL", "GOOG"], "1": ["TSLA"] } }
클러스터링 | 담은 종목 기반 유사 종목 추천 | POST | /cluster/recommend | CLU-006 | json { "tickers": ["AAPL", "TSLA"] } | json { "recommendations": ["NVDA", "MSFT"] }

## 백테스팅 API
기능 분류 | 기능 설명 | HTTP Method | Endpoint | PID | Request 예시 | Response 예시
-- | -- | -- | -- | -- | -- | --
백테스트 | 백테스트 실행 | POST | /backtest/run | BTE-001 | json { "etfs": ["SPY", "QQQ"], "start_date": "2020-01-01", "end_date": "2023-01-01", "initial_capital": 100000, "fee_rate": 0.001 } | json { "message": "Backtest started", "backtest_id": "abc123" }
백테스트 | 백테스트 결과 조회 | GET | /backtest/results?backtest_id={id} | BTE-002 | 없음 (QueryString 사용) | json { "returns": [...], "metrics": {...} }

