# 경로 변경 후 GitHub 재연결 가이드

## 상황 설명
프로젝트 폴더 경로를 변경한 후 GitHub 저장소와 다시 연결하는 방법입니다.

## 방법 1: 기존 저장소와 연결 (GitHub 저장소가 이미 있는 경우)

### 1단계: 새 경로에서 Git 초기화

터미널을 열고 새 경로로 이동한 후:

```bash
# 현재 디렉토리 확인
cd D:\YJH\project\test

# Git 저장소 초기화
git init

# 기존 원격 저장소 연결 (YOUR_USERNAME과 YOUR_REPO_NAME을 실제 값으로 변경)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# 원격 저장소 정보 확인
git remote -v

# GitHub에서 코드 가져오기
git pull origin main --allow-unrelated-histories

# 또는 master 브랜치인 경우
# git pull origin master --allow-unrelated-histories
```

### 2단계: 파일 추가 및 커밋

```bash
# 모든 파일 추가
git add .

# 커밋
git commit -m "프로젝트 경로 변경 후 재연결"

# GitHub에 푸시
git push -u origin main
```

---

## 방법 2: 새로운 저장소로 시작 (완전히 새로 시작하는 경우)

### 1단계: Git 초기화 및 파일 추가

```bash
# 현재 디렉토리 확인
cd D:\YJH\project\test

# Git 저장소 초기화
git init

# 파일 추가
git add .

# 첫 커밋
git commit -m "Initial commit"
```

### 2단계: GitHub에서 새 저장소 생성

1. GitHub.com에 로그인
2. 우측 상단 "+" 버튼 클릭 → "New repository" 선택
3. 저장소 이름 입력
4. **Public** 또는 **Private** 선택
5. "Initialize this repository with a README" 체크 해제
6. "Create repository" 클릭

### 3단계: 로컬 저장소와 GitHub 연결

```bash
# GitHub 저장소 연결 (YOUR_USERNAME과 YOUR_REPO_NAME을 실제 값으로 변경)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# 브랜치 이름을 main으로 설정
git branch -M main

# GitHub에 푸시
git push -u origin main
```

---

## 방법 3: 기존 원격 저장소 변경 (원격 저장소 URL을 바꾸고 싶은 경우)

```bash
# 기존 원격 저장소 제거
git remote remove origin

# 새로운 원격 저장소 추가
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# 확인
git remote -v

# 푸시
git push -u origin main
```

---

## 유용한 명령어

### 원격 저장소 확인
```bash
git remote -v
```

### 원격 저장소 URL 변경
```bash
git remote set-url origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
```

### 브랜치 확인 및 변경
```bash
# 현재 브랜치 확인
git branch

# 브랜치 이름 변경
git branch -M main
```

### 상태 확인
```bash
git status
```

---

## 문제 해결

### "fatal: not a git repository" 오류
→ `git init` 명령어를 먼저 실행하세요.

### "remote origin already exists" 오류
→ 기존 원격 저장소를 제거하고 다시 추가:
```bash
git remote remove origin
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
```

### 인증 오류
→ GitHub Personal Access Token을 사용하거나 SSH 키를 설정하세요.
- HTTPS: 토큰 사용 (Settings → Developer settings → Personal access tokens)
- SSH: SSH 키 설정 후 `git@github.com:USERNAME/REPO.git` 형식 사용

---

## Git 설치 확인

Windows에서 Git이 설치되어 있는지 확인:
```powershell
git --version
```

설치되어 있지 않다면:
- https://git-scm.com/download/win 에서 다운로드
- 설치 후 터미널 재시작
