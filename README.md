# 🌍 세계 랜드마크 탐험대

나라나 도시 이름을 검색하면 그곳의 **유명한 랜드마크를 추천**하고, 지도 위에 **빨간 점**으로 위치를 콕! 찍어 주는 **학생용 정보 검색 웹앱**입니다.

- 초등학생도 바로 쓸 수 있는 쉬운 화면
- 33개 나라·도시, 116곳의 랜드마크를 한글 설명과 함께 큐레이션
- 목록에 없는 곳은 실시간 지도 검색(OpenStreetMap)으로 위치를 찾아 줌
- 지도·지도 데이터·라이브러리를 파일 안에 내장 → 인터넷이 없어도 기본 기능 동작

---

## 🧭 학생 사용법

1. 위쪽 칸에 **나라**나 **도시** 이름을 적어요. (예: `프랑스`, `이집트`, `뉴욕`)
2. **🔍 검색**을 누르면 왼쪽에 유명한 곳 목록이 나와요.
3. 지도 위 **빨간 점**이 바로 그곳의 위치예요.
4. 목록 카드나 점을 누르면 지도가 그 자리로 **가까이** 이동해요.
5. 오른쪽 아래 `＋ － 🌐` 버튼으로 확대·축소·전체보기를 할 수 있어요.

---

## 📁 폴더 구조

```
landmark-explorer/
├─ index.html                  ← 이 파일 하나만 열면 실행됩니다
├─ README.md
└─ assets/
   ├─ d3.min.js                ← 지도 그리기 라이브러리 (내장)
   ├─ topojson-client.min.js   ← 지도 데이터 해석기 (내장)
   ├─ countries-110m.json      ← 세계 국경 데이터 (편집용 원본)
   └─ places.json              ← 랜드마크 데이터베이스 (편집용 원본)
```

> `index.html` 안에는 지도 데이터와 랜드마크 목록이 **이미 포함**되어 있어요.
> `assets/*.json`은 나중에 내용을 고치고 싶을 때를 위한 원본 사본입니다.

---

## 💻 내 컴퓨터에서 바로 열기

`index.html`을 더블클릭하면 브라우저에서 바로 열립니다. (별도 설치 불필요)

---

## 🚀 GitHub Pages로 배포하기

1. GitHub에서 새 저장소(repository)를 만듭니다. 예: `landmark-explorer`
2. 이 폴더의 **모든 파일**을 저장소에 업로드합니다. (index.html이 최상위에 오도록)
3. 저장소 **Settings → Pages** 로 이동합니다.
4. **Source**를 `Deploy from a branch`, 브랜치를 `main` / 폴더를 `/ (root)`로 선택하고 저장합니다.
5. 1~2분 뒤 `https://<아이디>.github.io/landmark-explorer/` 주소로 접속하면 끝!

---

## ✏️ 랜드마크 추가·수정하기

`assets/places.json`의 형식은 다음과 같습니다.

```json
{
  "id": "france",
  "names": ["프랑스", "france", "불란서"],
  "emoji": "🇫🇷",
  "landmarks": [
    { "name": "에펠탑", "city": "파리",
      "lat": 48.8584, "lng": 2.2945, "emoji": "🗼",
      "desc": "파리의 상징인 높이 330m의 철탑이에요." }
  ]
}
```

- `names` : 검색어(별칭)들. 한글·영어 모두 넣으면 좋아요.
- `lat`, `lng` : 위도·경도(WGS84). 구글 지도에서 우클릭하면 확인할 수 있어요.
- 수정한 뒤에는 `index.html`에 반영해야 합니다. 어려우면 **“랜드마크 추가해줘”** 라고 요청하시면 다시 만들어 드려요. 🙂

---

## 🛠 사용한 오픈 데이터·라이브러리

- 지도 시각화: [D3.js](https://d3js.org) · [TopoJSON](https://github.com/topojson)
- 세계 국경 데이터: [world-atlas](https://github.com/topojson/world-atlas) (Natural Earth, public domain)
- 장소 검색: [OpenStreetMap Nominatim](https://nominatim.org) · [Wikipedia](https://ko.wikipedia.org) (검색 시에만 사용)
- 글꼴: [Pretendard](https://github.com/orioncactus/pretendard)
- 지도 도법: 등거리 원통(Plate Carrée) — 위경도를 그대로 픽셀에 대응

---

만든이 · **두목쿼카 / 쿼카연구회** · 교실에서 바로 쓰는 AI융합 수업자료
