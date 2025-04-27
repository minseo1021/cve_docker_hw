# 취약한(CVE) Docker 환경 구성 과제
작성자: WHS 3기 16반 박민서

## 1. 개요
- 취약점 명: CVE-2012-2122
- MySQL과 MariaDB의 특정 버전에서 발견된 인증 우회 취약점
- 목표: MySQL 서비스에서 취약점을 이용해 비밀번호를 찾고 root 계정으로 로그인 성공

## 2. 환경 구축
- 사용한 리포지터리: [gunh0/kr-vulhub](https://github.com/gunh0/kr-vulhub)
- Fork한 리포지터리: [minseo1021](https://github.com/minseo1021/kr-vulhub.git)

## 3. 환경 구축 및 실행
- 1. Docker를 통해 취약한 MySQL 서버 환경(CVE-2012-2122)을 구축
     - docker compose up -d 실행
     ![Image](https://github.com/user-attachments/assets/cf953218-704c-40a3-9a40-07f5f1a29fb7)

     - pip install pymysql 실행
     ![Image](https://github.com/user-attachments/assets/47337c86-0594-41b5-b530-7ab1637729b3)

     - python3 poc.py 실행
       
     ![Image](https://github.com/user-attachments/assets/c424f465-6c53-4af3-a8c8-b4d1bf96e725)

- 2. 비밀번호 찾기
     - 로그인 반복 시행
     ![Image](https://github.com/user-attachments/assets/041932f0-1d96-4334-934e-207e0b26006e)
     - 올바른 비밀번호를 찾아냄
       
     ![Image](https://github.com/user-attachments/assets/a6f0a2f5-fdf5-427a-adb0-98a1d7921d96)

- 3. 찾아낸 비밀번호를 이용해 root 계정으로 데이터베이스 접속 성공
     - SELECT user() 쿼리를 실행하여 실제 로그인된 계정을 확인
     ![Image](https://github.com/user-attachments/assets/e6bad82f-58d7-4818-8f5d-d6ac437c5394)

## 4. 결과 및 분석
- root 계정의 비밀번호를 획득하고, 인증 우회에 성공
- 취약점을 이용해 인증 우회에 성공했다는 것
- 취약점이 시스템 보안에 미치는 심각성을 직접적으로 검증할 수 있었다.

## 5. 작업 기록
