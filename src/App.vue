<script setup>
import { onMounted } from 'vue'

// 스크롤해서 화면에 들어온 블록을 아래에서 떠오르게
onMounted(() => {
  const io = new IntersectionObserver((es) => es.forEach((e) => {
    if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target) }
  }), { threshold: 0.2 })
  document.querySelectorAll('.up').forEach((el) => io.observe(el))
})
</script>

<template>
  <header>
    <div class="wrap">
      <a href="#top"><img src="/logo.png" alt="VFT Partner"></a>
      <nav>
        <a href="#boda">서비스</a>
        <a href="#history">회사</a>
        <a href="#contact">연락</a>
        <a class="btn" href="mailto:">문의하기</a>
      </nav>
    </div>
  </header>

  <main>
    <section id="top" class="hero gray">
      <div class="wrap up">
        <h1>고객과의 끊임없는 소통으로<br>새로운 가치를 만들어요</h1>
        <p>BODA · AMA를 만드는 <span class="todo">브이에프티파트너</span></p>
      </div>
    </section>

    <section id="boda">
      <div class="wrap split">
        <div class="up">
          <h2>설계사의 하루를<br>한 화면에</h2>
          <p>고객 연락·보장분석·청구를<br>한곳에서 챙겨요</p>
          <a class="btn main" href="https://bodiary.com" target="_blank" rel="noopener">BODA 바로가기 →</a>
        </div>
        <div class="shot up"></div>
      </div>
    </section>

    <section class="gray">
      <div class="wrap split flip">
        <div class="up">
          <h2>내가 한 일이<br>나를 보여줘요</h2>
          <p>활동을 기록하고 분석해요</p>
          <span class="btn">준비 중</span>
        </div>
        <div class="shot up"><img src="/ama.jpg" alt="AMA 캐릭터"></div>
      </div>
    </section>

    <section id="history" class="center">
      <div class="wrap">
        <h2 class="up">걸어온 길</h2>
        <ol class="line up">
          <li><b>2022</b>S-Diary 출시</li>
          <li><b class="todo">----</b>잇다</li>
          <li><b>2026</b>BODA · AMA</li>
        </ol>
      </div>
    </section>

    <section id="contact" class="gray center">
      <div class="wrap up">
        <h2>VFT파트너와<br>이야기해요</h2>
        <div class="row">
          <a class="btn main" href="mailto:">메일 보내기</a>
          <a class="btn" href="https://map.kakao.com/?q=%EB%8C%80%EC%A0%84%20%EC%84%9C%EA%B5%AC%20%EA%B4%80%EC%A0%80%EB%A1%9C%2025" target="_blank" rel="noopener">지도 보기</a>
        </div>
        <p>대전광역시 서구 관저로 25, 4층 401호 · <span class="todo">042-710-0712</span></p>
      </div>
    </section>
  </main>

  <footer>
    <div class="wrap">
      <span><span class="todo">상호</span> · 대표 김주헌 · 사업자등록번호 <span class="todo">000-00-00000</span></span>
      <span>© VFT Partner</span>
    </div>
  </footer>
</template>

<style>
:root { --brand: #004b8b; --ink: #191f28; --sub: #4e5968; --gray: #f2f4f6; --soft: rgba(7, 25, 76, 0.05); }
* { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body { font-family: "Pretendard Variable", Pretendard, -apple-system, "Apple SD Gothic Neo", "Malgun Gothic", sans-serif; color: var(--ink); background: #fff; letter-spacing: -0.02em; }
a { color: inherit; text-decoration: none; }
.wrap { max-width: 1040px; margin: 0 auto; padding: 0 24px; }
.todo { background: #fff3a0; }

.btn { display: inline-block; padding: 12px 18px; border-radius: 12px; background: var(--soft); color: #333d4b; font-size: 16px; font-weight: 600; }
.btn.main { background: var(--brand); color: #fff; }

header { position: fixed; inset: 0 0 auto; z-index: 10; background: rgba(255, 255, 255, 0.85); backdrop-filter: blur(12px); }
header .wrap { display: flex; justify-content: space-between; align-items: center; height: 64px; }
header img { height: 26px; display: block; }
nav { display: flex; align-items: center; gap: 28px; font-size: 15px; color: var(--sub); }
nav .btn { padding: 8px 14px; font-size: 15px; }

section { min-height: 100vh; display: flex; align-items: center; padding: 120px 0; }
section > .wrap { width: 100%; }
.gray { background: var(--gray); }
.center { text-align: center; }

h1 { font-size: 56px; line-height: 1.3; font-weight: 700; }
h2 { font-size: 44px; line-height: 1.35; font-weight: 700; }
section p { margin-top: 20px; font-size: 19px; line-height: 1.6; color: var(--sub); }
section .btn { margin-top: 32px; }
.hero { text-align: center; }

.split { display: grid; grid-template-columns: 1fr 1fr; gap: 64px; align-items: center; }
.split.flip > :first-child { order: 2; }
.shot { aspect-ratio: 4 / 3; border-radius: 24px; background: #e5e8eb; }
.gray .shot { background: #fff; }
.shot { overflow: hidden; display: flex; align-items: flex-end; justify-content: center; }
.shot img { width: 80%; display: block; }

.line { list-style: none; display: flex; justify-content: space-between; margin-top: 64px; position: relative; }
.line::before { content: ""; position: absolute; top: 18px; left: 10%; right: 10%; height: 2px; background: #e5e8eb; }
.line li { position: relative; flex: 1; font-size: 18px; color: var(--sub); }
.line b { display: block; width: fit-content; margin: 0 auto 12px; padding: 0 12px; background: #fff; font-size: 30px; color: var(--ink); }
.line b.todo { background: #fff3a0; }
.row { display: flex; justify-content: center; gap: 12px; }
#contact p { margin-top: 32px; font-size: 16px; }
#contact p span { white-space: nowrap; }

footer { padding: 32px 0 48px; font-size: 13px; color: #8b95a1; }
footer .wrap { display: flex; justify-content: space-between; gap: 16px; flex-wrap: wrap; }

.up { opacity: 0; transform: translateY(40px); transition: opacity 0.8s ease, transform 0.8s ease; }
.up.in { opacity: 1; transform: none; }
@media (prefers-reduced-motion: reduce) { .up { opacity: 1; transform: none; transition: none; } }

@media (max-width: 768px) {
  nav a:not(.btn) { display: none; }
  section { min-height: auto; padding: 96px 0; }
  .hero { min-height: 100vh; }
  h1 { font-size: 32px; }
  h2 { font-size: 28px; }
  section p { font-size: 16px; }
  .split { grid-template-columns: 1fr; gap: 40px; }
  .split.flip > :first-child { order: 0; }
  .line { flex-direction: column; gap: 32px; }
  .line::before { display: none; }
}
</style>
