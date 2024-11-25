# Elasticsearch 설정 가이드

## 필수 조건
- Docker
- Docker Compose

## 설치 및 실행 방법

1. 저장소 클론
```bash
git clone https://github.com/three-ping/SyncDay_Docker.git
cd SyncDay_Docker
```
2. 실행
# Linux/Mac
```bash
# 스크립트 실행 권한 부여
chmod +x scripts/*.sh

# 설정 스크립트 실행
./scripts/setup.sh
```
# Windows
```bash
# Docker Desktop이 실행 중인지 확인

# 도커 컨테이너 실행
docker-compose up -d

# 약 30초 대기 후 인덱스 생성
# Git Bash 사용 시
curl -X PUT "localhost:9200/user_search" -H "Content-Type: application/json" -d @config/elasticsearch/nori-analyzer.json

# PowerShell 사용 시
Invoke-RestMethod -Method Put -Uri "http://localhost:9200/user_search" -Headers @{"Content-Type"="application/json"} -InFile "config/elasticsearch/nori-analyzer.json"
```
3. 확인
```bash
Elasticsearch: http://localhost:9200
Kibana: http://localhost:5601
```
4. 시작
```bash
docker-compose up -d
```
5. 중지
```bash
docker-compose down
```
