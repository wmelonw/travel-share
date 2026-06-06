# travel-share

여행 패키지 검색 에이전트(OpenClaw)의 **카카오톡 공유용 정적 페이지**.

텔레그램 메시지 하단의 "📤 카톡으로 공유" 인라인 버튼 → 이 페이지가 열림 →
URL 해시(base64url JSON `{t: 마크다운본문, img: 비교표PNG URL}`)를 디코드 →
마크다운 링크를 생(生) URL로 변환 + 비교표 이미지를 `navigator.share({ text, files })`
(Web Share Level 2)로 카카오톡에 공유.

- `index.html` — 공유 페이지(정적, 배포 1회 후 거의 불변)
- `latest.png` — 최신 검색의 상위 5개 비교표(매 검색 시 덮어쓰기 푸시, 캐시버스터 `?v=` 사용)
