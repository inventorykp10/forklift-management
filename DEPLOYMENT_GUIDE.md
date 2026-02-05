# GitHub Pages 배포 가이드

## 📚 단계별 배포 방법

### 1단계: GitHub 저장소 생성

1. GitHub에 로그인
2. 새 저장소 생성 (예: `forklift-management-system`)
3. Public 저장소로 설정
4. README 파일 초기화 (선택사항)

### 2단계: 파일 업로드

저장소에 다음 파일들을 업로드하세요:

```
forklift-management-system/
├── index.html              (forklift-system-v6-deployment.html을 index.html로 이름 변경)
└── README.md
```

**중요**: `forklift-system-v6-deployment.html` 파일을 **반드시 `index.html`로 이름을 변경**해야 합니다!

#### 파일 업로드 방법:

**방법 A: 웹 인터페이스 사용**
1. GitHub 저장소 페이지에서 "Add file" → "Upload files" 클릭
2. 파일들을 드래그 앤 드롭
3. Commit changes

**방법 B: Git 명령어 사용**
```bash
git clone https://github.com/YOUR_USERNAME/forklift-management-system.git
cd forklift-management-system
# forklift-system-v6-deployment.html을 index.html로 복사
cp forklift-system-v6-deployment.html index.html
git add .
git commit -m "Initial deployment"
git push origin main
```

### 3단계: GitHub Pages 활성화

1. 저장소의 **Settings** 탭으로 이동
2. 왼쪽 메뉴에서 **Pages** 선택
3. **Source** 섹션에서:
   - Branch: `main` (또는 `master`) 선택
   - Folder: `/ (root)` 선택
4. **Save** 클릭

### 4단계: 배포 확인

- 배포는 보통 1-2분 소요됩니다
- 배포 완료 후 다음 URL로 접근 가능:
  ```
  https://YOUR_USERNAME.github.io/forklift-management-system/
  ```

### 5단계: 테스트

배포된 사이트에서:
- ✅ 로그인 기능 테스트 (admin/admin123)
- ✅ 대시보드 로딩 확인
- ✅ 체크리스트 작성 테스트
- ✅ Excel/PDF 다운로드 테스트
- ✅ 데이터 저장/로드 테스트

## 🔧 문제 해결

### 문제 1: 페이지가 404 오류
**해결**: 파일 이름이 `index.html`인지 확인하세요

### 문제 2: 이미지가 표시되지 않음
**해결**: 이미 Base64로 임베드되어 있어 별도 이미지 파일 불필요

### 문제 3: 기능이 작동하지 않음
**해결**: 브라우저 콘솔(F12)에서 오류 확인

### 문제 4: 배포가 진행되지 않음
**해결**: GitHub Actions 탭에서 배포 상태 확인

## 🎯 추가 최적화

### 커스텀 도메인 설정 (선택사항)

1. Settings → Pages → Custom domain
2. 도메인 입력 (예: forklift.yourcompany.com)
3. DNS 설정에서 CNAME 레코드 추가:
   ```
   CNAME  forklift  YOUR_USERNAME.github.io
   ```

### HTTPS 강제 활성화

1. Settings → Pages
2. "Enforce HTTPS" 체크박스 선택

## 📊 배포 후 모니터링

GitHub Pages는 기본적으로:
- ✅ 자동 HTTPS 제공
- ✅ CDN을 통한 글로벌 배포
- ✅ 무료 호스팅 (Public 저장소)

## 🔐 보안 권고사항

프로덕션 환경 배포 시:

1. **로그인 정보 변경**
   - 기본 admin/admin123을 변경하세요
   - HTML 파일의 credentials 객체 수정

2. **데이터 보안**
   - LocalStorage는 클라이언트 측 저장소입니다
   - 민감한 데이터는 서버 측 데이터베이스 사용 권장

3. **접근 제어**
   - 필요시 IP 화이트리스트 구현
   - OAuth 인증 추가 고려

## 📱 모바일 접근

이 시스템은 반응형으로 설계되어 모바일에서도 완벽하게 작동합니다:
- 📱 스마트폰
- 📱 태블릿
- 💻 데스크톱

## 🆘 지원

문제가 발생하면:
1. GitHub Issues에 문제 보고
2. 브라우저 콘솔 로그 첨부
3. 재현 단계 설명

---

**배포 성공을 기원합니다! 🚀**
