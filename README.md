# koc-ig-assets

KOREA ON CUE 인스타 캐러셀 카드·릴스 호스팅용. 저장소(`korea-on-cue`) 밖에 둔다.

**왜 저장소 밖이고, 왜 GitHub인가** — 인스타 발행 API는 공개 `image_url`만 받고 메타가
그 주소에서 파일을 직접 가져간다. GitHub raw 호스팅은 **글로우메오에서 이미 운영 중인
현행 방식**이다(Owner 확인 2026-09-05). 임시 우회가 아니므로 KOC도 처음부터 이 방식이다.

배경은 korea-on-cue 저장소 `drafts/reading-the-street-when-signs-disagree/insta/CARD-PLAN-v01.md`
「호스팅」 절에 있다.

```
raw base   https://raw.githubusercontent.com/nakojin/koc-ig-assets/main   (저장소 생성 뒤 확정)
구조       <슬러그>/card-1.jpg … card-N.jpg   (1080×1350 · 베이스라인 JPEG · 프로그레시브 금지)
           <슬러그>/reel.mp4 · <슬러그>/reel-src/   (릴스가 생기면)
```

글로우메오와 같은 구조다. 발행 스크립트가 `.env`의 `IG_ASSETS_DIR`·`IG_ASSETS_RAW_BASE`를 읽는다.

- 파일은 **발행 스크립트가 넣는다.** 손으로 고치지 않는다.
- 프로그레시브 JPEG는 인스타가 거부한다. 업로드 직전 검사를 스크립트에 넣는다
  (글로우메오 `instagram-publish-carousel.mjs`가 그렇게 한다).
- 🔴 **공개 저장소가 되면 카드가 인스타 발행 전에 먼저 공개된다.** 발행 직전에만 푸시한다.

## 상태 (2026-09-05)

⚠️ **이 폴더는 아직 클론이 아니다.** README만 있는 일반 폴더다. 발행 스크립트는 `.git`이
없으면 시작조차 하지 않는다. 공개 저장소 `nakojin/koc-ig-assets`가 만들어지면 **클론으로
다시 받고 이 폴더는 버린다.**

공개 저장소는 계정·메타 앱과 함께 Owner가 만든다(팀장이 묶어 보고).
