# GitHub Pages 배포 가이드

## 1단계: GitHub에서 저장소 생성

1. GitHub.com에 로그인
2. 우측 상단의 "+" 버튼 클릭 → "New repository" 선택
3. 저장소 이름 입력 (예: `hello-world-website`)
4. **Public** 선택 (GitHub Pages 무료 버전은 Public 저장소만 지원)
5. "Initialize this repository with a README" 체크 해제
6. "Create repository" 클릭

## 2단계: 로컬에서 Git 초기화 및 업로드

VS Code 터미널에서 다음 명령어를 실행하세요:

```bash
# Git 저장소 초기화
git init

# 파일 추가
git add index.html README.md

# 첫 커밋
git commit -m "Initial commit: Hello World website"

# GitHub 저장소 연결 (YOUR_USERNAME과 YOUR_REPO_NAME을 실제 값으로 변경)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# 브랜치 이름을 main으로 설정
git branch -M main

# GitHub에 푸시
git push -u origin main
```

## 3단계: GitHub Pages 활성화

1. GitHub 저장소 페이지로 이동
2. 상단 메뉴에서 **Settings** 클릭
3. 왼쪽 사이드바에서 **Pages** 클릭
4. "Source" 섹션에서:
   - Branch: `main` 선택
   - Folder: `/ (root)` 선택
5. **Save** 클릭

## 4단계: 웹사이트 확인

몇 분 후 다음 URL로 웹사이트에 접속할 수 있습니다:
```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

예: `https://john.github.io/hello-world-website/`

---

**참고**: GitHub Pages가 활성화되기까지 몇 분이 걸릴 수 있습니다. 처음에는 404가 나올 수 있으니 잠시 기다려보세요.
