# 베이스 이미지 선택
FROM python:3.10-slim

# 작업 디렉토리 설정
WORKDIR /app

# 로컬 파일을 컨테이너에 복사
COPY . /app

# 필요한 패키지 설치
RUN pip install --no-cache-dir -r requirements.txt

# 컨테이너가 실행할 명령
CMD ["python", "main_APIServer.py"]

