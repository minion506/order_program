# 용용이네 & 밧디글라 주문 폼

```
index.html (고객 주문, 모바일 웹)  →  Apps Script doPost  →  구글 시트 "주문"
                                            ├─ 담당자 문자 (즉시)
                                            ├─ 매일 06:00 요약 문자 (주문 없으면 생략)
                                            └─ 시트 '입금확인' 체크 → 고객 문자
```

## 설치 (10분)

1. 구글 시트 새로 만들기 → 확장 프로그램 → Apps Script
2. `apps-script/Code.gs` 내용을 붙여넣고 저장
3. 편집기에서 `setup` 함수 1회 실행 (권한 허용) → 시트 탭 + 트리거 생성
4. 배포 → 새 배포 → 웹 앱 → 실행: **나**, 액세스: **모든 사용자** → 배포 → URL 복사
5. `index.html` 상단 `API_URL`에 붙여넣기, `ACCOUNT`에 계좌 입력
6. `index.html`을 GitHub Pages 등에 올리기 (파일 하나라 어디든 됨)

## 문자 켜기 (나중에)

1. solapi.com 가입 → 발신번호 등록 → API 키 발급 → 충전
2. `Code.gs` 상단 `SOLAPI_KEY / SOLAPI_SECRET / SENDER_PHONE` 입력, `SMS_ENABLED = true`
3. 저장하면 끝 (재배포 불필요)

## 수정할 곳

| 무엇 | 어디 |
|---|---|
| 품목·가격 | `index.html` → `ITEMS` |
| 계좌번호 | `index.html` → `ACCOUNT` |
| 담당자 번호 | `Code.gs` → `MANAGER_PHONE` |
| 문자 문구 | `Code.gs` → `sendSms(...)` 호출부 |
