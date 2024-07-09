# next-yarn-standard

#### ✅ 첫 Clone 시에는 yarn or yarn install 실행

#### ❌ yarn dev Error 시

- 버전을 맞춘다.
- yarn install을 한다

## ✔ 세팅 버전 ( Version )

#### ✔ **Node** : 20.12.1

#### ✔ **Yarn berry** : 4.3.1

#### ✔ **React** : 18.2.0

#### ✔ **Next** : 14.2.4

## 📖 특징 ( Features )

- ⚛️ Create Next App
- 0️⃣ Zero-install
- 💢 ESLint & Prettier
- 🎨 Emotion

## 1️⃣ 초기설치 ( Setup )

### 0. Node Version 확인

```bash
node -v  // 20.12.1
```

### ❌ Node 버전 틀린 경우

```bash
// 터미널 열기 (관리자권한)

(1)
nvm list
nvm use 20.12.1

(2)
# node v 20.12.1 없을경우 ❌
# nvm 버전 설치
# 리스트에 다운로드 여부 확인 ✔

nvm install 20.12.1
nvm list
nvm use 20.12.1
```

### 1. Yarn 설치

```bash
npm install -g yarn
```

### 2. Next 프로젝트 생성

```bash
# NextJS 프로젝트
yarn create next-app [프로젝트명]
```

### 3. Yarn berry 활성화

```bash
# 최신버전으로 다운로드
yarn set version berry

# 특정 버전 다운
yarn set version [version]

이후

yarn or yarn install
```

### 4. pnp 설정

1. .yarnrc.yml 폴더에서 nodeLinker 수정
   ![alt text](image.png)
2. $ yarn install
3. Yarn berry 와 IDE 통합 - **ZipFs Plugin 익스텐션설치**

```bash
yarn dlx @yarnpkg/sdks vscode

- allow 를 누르고 사용한다
# 누르지 못할경우 타입스크립트 파일에서
# ctrl + shift + p > Select TypeScript Version 클릭 > use Workspace version 클릭
```

### 5. .gitignore 설정 ( zero-install )

```bash
#.gitignore 에 추가

# yarn zero install
.yarn/*
!.yarn/cache
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions
```

### 6. GIT REMOTE

```bash
git remote add origin [레포주소]
git branch -M main
git push -u origin main

이후

git add . // 전체 저장
git commit 'test : remote test'
git push origin main
```

### 7. GIT remote test 커밋 삭제 이후 초기 commit 에 상태 반영

```bash
1.
git reset --soft [커밋주소]
- soft : 현재 변경사항을 유지한상태로 특정 커밋 주소로 되돌림
- hard : 로컬 저장소의 상태를 특정 커밋 주소 상태로 완전히 되돌림

2.
git status
- new file 은 test : remote test 에 있던것
- modified 는 현재에서 수정하고 있던것
- 초록색 : 스테이징올란간것
- 빨간색 : 변경중인것

3.
git commit -m 'feat : [내용]'
- 커밋 메시지의 첫번째 줄은 Title 두번째 줄은 description 마지막에 ' 붙여준다

Error 충돌
git push origin main 을 할경우 이전 커밋주소로인해 충돌이난다.
- 결론 : git push origin +main 으로 강제 푸시해줘야한다.
```
