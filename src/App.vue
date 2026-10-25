<template>
  <header>
    <div class="wrap">
      <img src="/logo.png" alt="VFT Partner">
      <a class="btn" href="mailto:">문의하기</a>
    </div>
  </header>

  <main class="wrap">
    <section class="hero">
      <p>고객과의 끊임없는 소통으로<br>새로운 가치를 창조합니다.</p>
      <small><span class="todo">브이에프티파트너(주)</span></small>
    </section>

    <section>
      <h2>운영 서비스</h2>
      <div class="cards">
        <div class="card">
          <h3>BODA</h3>
          <p>보험설계사 영업 지원 · 지점 사원 관리</p>
          <a class="btn" href="https://bodiary.com" target="_blank" rel="noopener">바로가기 →</a>
        </div>
        <div class="card">
          <h3>AMA</h3>
          <p>내 활동을 기록하고 분석하는 다이어리</p>
          <span class="btn off">준비 중</span>
        </div>
      </div>
    </section>

    <section class="history">
      <h2>걸어온 길</h2>
      <ul>
        <li><b>2022</b>S-Diary v1.0 출시</li>
        <li><b class="todo">----</b>잇다</li>
        <li><b>2026</b>BODA · AMA</li>
      </ul>
    </section>

    <section class="contact">
      <h2>연락</h2>
      <p>대전광역시 서구 관저로 25, 4층 401호
        <a class="btn" href="https://map.kakao.com/?q=%EB%8C%80%EC%A0%84%20%EC%84%9C%EA%B5%AC%20%EA%B4%80%EC%A0%80%EB%A1%9C%2025" target="_blank" rel="noopener">지도</a></p>
      <p><span class="todo">042-710-0712</span></p>
      <p><span class="todo">이메일</span> <a class="btn" href="mailto:">메일 보내기</a></p>
    </section>
  </main>

  <footer>
    <div class="wrap">
      <span class="todo">상호</span> · 대표 김주헌 · 사업자등록번호 <span class="todo">000-00-00000</span><br>
      © VFT Partner
    </div>
  </footer>
</template>

<style>
:root { --brand: #004b8b; --ink: #1a1a1a; --sub: #666; --line: #e5e5e5; --bg: #fff; }
* { box-sizing: border-box; margin: 0; }
body { font-family: -apple-system, "Apple SD Gothic Neo", "Malgun Gothic", sans-serif; color: var(--ink); background: var(--bg); line-height: 1.6; }
.wrap { max-width: 880px; margin: 0 auto; padding: 0 16px; }
section { padding: 48px 0; border-top: 1px solid var(--line); }
h2 { font-size: 14px; color: var(--sub); font-weight: 600; margin-bottom: 20px; }
a { color: var(--brand); }
.btn { display: inline-block; padding: 8px 16px; border: 1px solid var(--brand); border-radius: 8px; text-decoration: none; font-size: 14px; }
.todo { background: #fff3a0; padding: 0 4px; }

header .wrap { display: flex; justify-content: space-between; align-items: center; height: 72px; }
header img { height: 32px; }

.hero { padding: 80px 0; border-top: 0; }
.hero p { font-size: 32px; font-weight: 700; line-height: 1.4; }
.hero small { display: block; margin-top: 16px; color: var(--sub); font-size: 16px; }

.cards { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.card { border: 1px solid var(--line); border-radius: 12px; padding: 24px; }
.card h3 { font-size: 22px; color: var(--brand); }
.card p { color: var(--sub); margin: 8px 0 20px; }
.card .off { border-color: var(--line); color: var(--sub); }

.history ul { padding: 0; }
.history li { list-style: none; display: flex; gap: 24px; padding: 6px 0; }
.history b { width: 48px; }

.contact p { margin-bottom: 8px; }
.contact .btn { margin-left: 8px; padding: 2px 10px; font-size: 13px; }

footer { padding: 24px 0 40px; border-top: 1px solid var(--line); color: var(--sub); font-size: 13px; }

@media (max-width: 600px) {
  .hero p { font-size: 24px; }
  .cards { grid-template-columns: 1fr; }
}
</style>
