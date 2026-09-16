# 풀빌라 다이어리 — 배포 가이드

코딩닌자 ♥ 코딩끼끼의 풀빌라 다이어리 사이트. `index.html` 하나로 동작하는 정적 사이트야.

목표: **GitHub Pages(무료 호스팅) + is-a.dev(무료 서브도메인)** 조합으로
`https://ourvacationplan.is-a.dev` 에서 열리게 만들기.

---

## 1. GitHub에 코드 올리기

1. GitHub에서 새 저장소(Repository)를 만든다. (Public, README 없이 생성)
   - 이름 예시: `2026-vacation-plan`
2. 이 폴더를 압축 해제한 뒤, 터미널에서:

   ```bash
   cd poolvilla-site
   git remote add origin https://github.com/Cho-SeoYeon/2026-vacation-plan.git
   git branch -M main
   git push -u origin main
   ```

## 2. GitHub Pages 켜기

1. 방금 만든 저장소 → **Settings → Pages**
2. **Source**: `Deploy from a branch` 선택
3. **Branch**: `main` / `/ (root)` 선택 → Save
4. 몇 분 뒤 `https://Cho-SeoYeon.github.io/2026-vacation-plan/` 에서 사이트가 열려 있으면 성공.

이 단계까지만 해도 이미 무료 링크로 여자친구한테 공유 가능해.

## 3. is-a.dev로 예쁜 주소 받기 (선택)

`https://ourvacationplan.is-a.dev` 처럼 짧은 주소를 원하면:

1. 이 저장소에 포함된 `CNAME` 파일 내용이 `ourvacationplan.is-a.dev`로 되어 있는지 확인
   (다른 이름을 쓰고 싶으면 이 파일 내용을 원하는 이름으로 수정 후 다시 push)
2. GitHub 저장소 **Settings → Pages → Custom domain** 칸에 같은 주소(`ourvacationplan.is-a.dev`)를 입력하고 저장
3. GitHub 계정으로 **[is-a-dev/register](https://github.com/is-a-dev/register)** 저장소를 Fork
4. `domains/ourvacationplan.json` 파일을 새로 만든다. 이 프로젝트의 `domains-example/ourvacationplan.json.example` 파일을
   참고용 예시로 넣어뒀으니, 내용을 **본인이 직접 확인/수정**해서 옮겨 담기
   (is-a.dev 쪽에서 AI가 그대로 생성한 요청은 반려한다고 명시하고 있어서,
   제출 전에 반드시 `https://docs.is-a.dev` 최신 형식과 맞는지 스스로 확인해야 해)
5. Pull Request를 연다 → 리뷰 통과 후 머지되면 몇 분 내로 `ourvacationplan.is-a.dev` 활성화

---

### 참고
- 도메인 이름(`ourvacationplan`)은 원하는 걸로 자유롭게 바꿔도 돼 — `CNAME` 파일과
  is-a.dev PR의 파일명(`domains/이름.json`) 두 곳을 같은 이름으로 맞추면 됨.
- GitHub Pages, is-a.dev 둘 다 결제/카드 등록 없이 무료로 사용 가능.
