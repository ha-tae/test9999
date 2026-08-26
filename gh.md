# 실행한 GitHub CLI 명령어

## 설치 및 인증 확인

```bash
command -v gh && gh --version
gh auth status
```

## 저장소 목록 조회

```bash
gh repo list ha-tae --limit 100
```

> 위 조회 명령은 일반 실행과 네트워크 권한으로 재시도하여 총 2회 실행했습니다.

## 공개 저장소 생성

```bash
gh repo create test1111 --public --confirm
```

생성된 저장소: `https://github.com/ha-tae/test1111`

## GitHub Actions secret 등록

```bash
gh secret set vvv --repo ha-tae/test1111 --body <SECRET_VALUE>
```

`<SECRET_VALUE>`에는 등록할 실제 secret 값을 넣습니다. 실행 당시에는 사용자가 제공한 값을 사용했습니다.
