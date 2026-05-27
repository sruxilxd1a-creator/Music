# GitHub Pages 배포 안내

## 폴더 구조
이 zip을 풀면 다음 구조입니다. **이 구조 그대로** 레포지토리에 올려야 합니다.

```
index.html          ← 메인 (32KB, 가벼움)
tracks/
  track1.mp3 ~ track6.mp3   ← 음원 6곡 (각 2~4MB)
```

index.html 은 `tracks/track1.mp3` 같은 상대 경로로 음원을 불러옵니다.
폴더 이름(tracks)과 파일 이름을 바꾸지 마세요.

## 올리는 방법

### 방법 A — 웹에서 드래그 업로드 (간단)
1. GitHub 레포지토리 페이지에서 **Add file → Upload files**
2. `index.html` 과 `tracks` 폴더를 통째로 드래그
   (폴더 드래그가 안 되면 tracks 안의 mp3 6개를 먼저 올리고,
    경로가 `tracks/track1.mp3` 가 되도록 커밋 메시지 칸 위에서 경로 확인)
3. **Commit changes**

mp3 파일당 크기는 모두 25MB 미만이라 웹 업로드 제한에 걸리지 않습니다.

### 방법 B — git 명령어
```
git add index.html tracks/
git commit -m "buds gesture prototype"
git push
```

## GitHub Pages 켜기
1. 레포지토리 **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / 폴더: `/ (root)` → **Save**
4. 1~2분 뒤 같은 화면 위쪽에 URL이 표시됨
   `https://<사용자명>.github.io/<레포이름>/`

index.html 이라는 이름이므로, 위 URL만으로 바로 열립니다.

## 확인
- 폰 Chrome에서 그 https URL 접속
- 화면 왼쪽 위 디버그 패널의 "보안컨텍스트"가 초록 `OK (https:)` 인지 확인
- "센서이벤트" 숫자가 올라가면 센서 정상

## 음원을 바꾸고 싶을 때
tracks 폴더의 mp3를 같은 이름(track1~6.mp3)으로 교체하면 됩니다.
곡 제목·아티스트 표시는 index.html 상단의 TRACK_DATA 배열에서 수정.
