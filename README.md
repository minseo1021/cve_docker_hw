# 취약한(CVE) Docker 환경 구성 과제
작성자: WHS 3기 16반 박민서

## 1. 개요
- 취약점 명: CVE-2012-2122
- MySQL과 MariaDB의 특정 버전에서 발견된 인증 우회 취약점

## 2. 환경 구축
- 사용한 리포지터리: [gunh0/kr-vulhub](https://github.com/gunh0/kr-vulhub)
- Fork한 리포지터리: [minseo1021](https://github.com/minseo1021/kr-vulhub.git)

## 3. 환경 구축
- 1. docker compose up -d
![Image](https://github.com/user-attachments/assets/cf953218-704c-40a3-9a40-07f5f1a29fb7)

- 2. pip install pymysql
![Image](https://github.com/user-attachments/assets/47337c86-0594-41b5-b530-7ab1637729b3)

- 3. python3 poc.py
![Image](https://github.com/user-attachments/assets/c424f465-6c53-4af3-a8c8-b4d1bf96e725)

- 4. 로그인 반복 시행
![Image](https://github.com/user-attachments/assets/041932f0-1d96-4334-934e-207e0b26006e)
![Image](https://github.com/user-attachments/assets/a6f0a2f5-fdf5-427a-adb0-98a1d7921d96)

- 5. 로그인 성공
![Image](https://github.com/user-attachments/assets/e6bad82f-58d7-4818-8f5d-d6ac437c5394)
