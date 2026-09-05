# koc-ig-assets

KOREA ON CUE 인스타 캐러셀 카드·릴스 호스팅용. 저장소(`korea-on-cue`) 밖에 둔다.

**왜 저장소 밖이고, 왜 GitHub인가** — 인스타 발행 API는 공개 `image_url`만 받고 메타가
그 주소에서 파일을 직접 가져간다. GitHub raw 호스팅은 **글로우메오에서 이미 운영 중인
현행 방식**이다(Owner 확인 2026-09-05). 임시 우회가 아니므로 KOC도 처음부터 이 방식이다.

배경은 korea-on-cue 저장소 `drafts/reading-the-street-when-signs-disagree/insta/CARD-PLAN-v01.md`
「호스팅」 절에 있다.

```
raw base   https://raw.githubusercontent.com/nakojin/koc-ig-assets/main   (2026-09-05 확인: HTTP 200)
구조       <슬러그>/card-1.jpg … card-N.jpg   (1080×1350 · 베이스라인 JPEG · 프로그레시브 금지)
           <슬러그>/reel.mp4 · <슬러그>/reel-src/   (릴스가 생기면)
```

글로우메오와 같은 구조다. 발행 스크립트가 `.env`의 `IG_ASSETS_DIR`·`IG_ASSETS_RAW_BASE`를 읽는다.

- 파일은 **발행 스크립트가 넣는다.** 손으로 고치지 않는다.
- 프로그레시브 JPEG는 인스타가 거부한다. 업로드 직전 검사를 스크립트에 넣는다
  (글로우메오 `instagram-publish-carousel.mjs`가 그렇게 한다).
- 🔴 **공개 저장소가 되면 카드가 인스타 발행 전에 먼저 공개된다.** 발행 직전에만 푸시한다.

## 상태 (2026-09-05)

✅ 저장소 생성 완료(Owner) · 로컬 클론 전환 완료(팀장) · raw 주소 HTTP 200 확인(과장).
발행 스크립트의 `.git` 검사를 통과한다.

**아직 카드는 없다.** 남은 것은 인스타 계정·메타 앱·토큰이고 셋 다 Owner 화면 몫이다.
첫 편(`reading-the-street-when-signs-disagree`) 카드 9장은 korea-on-cue 저장소의
`drafts/<슬러그>/insta/cards.html`에 완성돼 있고, 렌더 스크립트가 이식되면 PNG가 나온다.

🔴 **이 저장소는 공개다.** 푸시하는 순간 카드가 인스타보다 먼저 공개된다 —
**발행 직전에만 푸시한다.**
