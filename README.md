# 팝업 노드

NFC 팝업에서 사람마다 문장 세 개를 받는 웹이다. 찾고 있는 것(SEEK), 내놓을 수 있는 것(OFFER), 같이 그리고 싶은 것(IMAGINE). 겹치는 결만 별자리의 줄로 보여 준다.

라이브는 [node.cyp3.xyz](https://node.cyp3.xyz).

## 로컬에서 실행

```bash
npm install
npm run dev
```

브라우저에서 http://localhost:3000

환경 변수 없이도 켜진다. 로컬 저장은 `data/store.json`에 생기고, 그 파일은 깃에 올라가지 않는다.

## 환경 변수

값은 이 저장소에 없다. 이름은 `.env.example`에만 있다. 쓸 때는 `.env.local`에 넣는다.

| 이름 | 없을 때 |
|---|---|
| `DATABASE_URL` | 로컬 json. 없으면 `POSTGRES_URL`, 그다음 `POSTGRES_PRISMA_URL`. |
| `OPENAI_API_KEY` | 로컬 말뭉치로 겹침을 가른다. |
| `OPENAI_EMBEDDING_MODEL` | `text-embedding-3-small` |
| `VAPID_PUBLIC_KEY` / `VAPID_PRIVATE_KEY` / `VAPID_SUBJECT` | 로컬은 `data/vapid.json`을 자동으로 만든다. |
| `TELEGRAM_BOT_TOKEN` / `TELEGRAM_BOT_USERNAME` / `TELEGRAM_WEBHOOK_SECRET` | 텔레그램 알림만 꺼진다. |
| `ENABLE_TEST_AGENTS` | 로컬은 테스트 입구가 켜지고, 배포는 꺼진다. |

`npx web-push generate-vapid-keys`로 푸시 키를 만든다. `VAPID_SUBJECT`는 `mailto:`로 시작한다.

## 화면

- `/` 입장
- `/join` 노드 만들기
- `/usershow` 그로브
- `/my-node` 내 별과 겹친 사람
- `/devshow` 전시 화면

## 이 저장소에 없는 것

API 키, 데이터베이스 주소, 푸시 비밀키, 참가자가 적은 문장, 이메일은 올리지 않는다. 배포에서는 환경 변수로만 둔다.
