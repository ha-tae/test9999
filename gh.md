# GitHub CLI 설정 및 실행 기록

## 세션 1. `gh` 설치 (선행 작업)

Ubuntu/Debian 환경에서 GitHub CLI를 설치합니다. 이미 설치되어 있다면 이 단계는 건너뜁니다.

```bash
sudo apt update
sudo apt install -y gh
```

설치 여부와 버전을 확인합니다.

```bash
command -v gh && gh --version
```

## 세션 2. GitHub 로그인 및 인증 (선행 작업)

웹 브라우저 인증 방식으로 GitHub 계정에 로그인합니다.

```bash
gh auth login -h github.com --web
```

인증 상태를 확인합니다.

```bash
gh auth status
```

기존 토큰이 만료되었거나 유효하지 않은 경우에도 위 `gh auth login` 명령으로 다시 인증할 수 있습니다.

## 세션 3. 내 저장소 목록 조회

```bash
gh repo list ha-tae --limit 100
```

이 세션에서는 네트워크 권한으로 재시도하여 목록 조회를 완료했습니다.

## 세션 4. 공개 저장소 생성

```bash
gh repo create test1111 --public --confirm
```

생성된 저장소: `https://github.com/ha-tae/test1111`

## 세션 5. GitHub Actions secret 등록

```bash
gh secret set vvv --repo ha-tae/test1111 --body <SECRET_VALUE>
```

`<SECRET_VALUE>`에는 등록할 실제 secret 값을 넣습니다. secret 값을 명령 기록이나 저장소 파일에 남기지 않는 것을 권장합니다.
