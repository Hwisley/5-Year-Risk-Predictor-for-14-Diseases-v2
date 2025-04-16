FROM python:3.9-slim

# 시스템 패키지 설치
RUN apt-get update && apt-get install -y \
    wget \
    gnupg \
    unzip \
    cron \
    && rm -rf /var/lib/apt/lists/*

# Google Chrome 설치
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
    && echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list \
    && apt-get update \
    && apt-get install -y google-chrome-stable \
    && rm -rf /var/lib/apt/lists/*

# 작업 디렉토리 생성
WORKDIR /app

# 필요한 디렉토리 생성
RUN mkdir -p /home/autocare/Autocare_Outputs/PDFs \
    && mkdir -p /home/autocare/resources/src

# Python 패키지 설치
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# 소스 코드 복사
COPY src/ /app/src/

# 실행 권한 설정
COPY entrypoint.sh /app/
RUN chmod +x /app/entrypoint.sh

# cron 작업 설정
RUN echo "0 1 * * * python /app/src/main_AutoUpdater.py >> /var/log/cron.log 2>&1" > /etc/cron.d/autoupdater
RUN chmod 0644 /etc/cron.d/autoupdater

# 환경 변수 설정
ENV PYTHONPATH=/app

# 진입점 설정
ENTRYPOINT ["/app/entrypoint.sh"] 
