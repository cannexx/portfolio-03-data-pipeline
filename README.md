# 소셜 투표 서비스 데이터 파이프라인

🔗 [Vercel 앱 바로가기](https://ping-v2-lac.vercel.app/) | [파이프라인 다이어그램](https://claude.ai/code/artifact/958167e6-cd4d-4cbd-a452-f6edd772e431) | [데이터 대시보드](https://datastudio.google.com/u/0/reporting/56421d8f-e6cc-4303-8e86-76b5d31cb55c/page/p_bc34jacl6d/edit)

## 개요

* 목표: 사용자 이탈 원인 분석을 위한 데이터 구조 및 파이프라인 구축
* 기간: 2026.07.23 ~ 2026.08.27
* 데이터: 2023.03 ~ 2024.05
* 문제: 가입자의 63.9%가 가입 후 일주일 이내 활동 중단
* 데이터 한계: 투표 데이터가 10개 학교에만 존재하여 이탈 원인 분석에 제약

## 분석 과정

1. 레거시 서비스 데이터 구조 및 이탈 현황 분석
2. Raw → Staging → Mart 데이터 구조 설계
3. Airflow 기반 데이터 적재 및 집계 자동화

## 주요 결과

* 실제·합성 데이터를 동일한 구조로 관리하고 `_source`, `_loaded_at`으로 데이터 구분
* Raw 원천 데이터 적재 → Staging View 10개 → Mart 집계 테이블 8개로 데이터 계층화
* Airflow 2개 DAG으로 Raw 적재부터 Mart 생성까지 자동화

## 사용 기술

* BigQuery, Airflow, Python, PostgreSQL, Supabase, Looker Studio

## 프로젝트 구조

```text
.

├── docs/
│   ├── 0. 프로젝트 일정.pdf
│   ├── 1. 익명 투표 SNS 서비스 운영 데이터 분석 보고서.pdf
│   └── 2. 데이터 파이프라인 설계 및 구축.pdf
├── notebooks/
│   └── 01_v2_eda.ipynb
└── output/
    └── pipeline_diagram_v2.png
```