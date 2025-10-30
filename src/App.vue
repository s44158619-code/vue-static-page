<script setup lang="ts">
const mainTitle = "가장 밝은 달, 한가위";
const mainSubtitle = "마음까지 넉넉해지는 풍성한 추석. 잊지 못할 전통과 맛의 향연에 여러분을 초대합니다.";
const mainEmoji = "🌕"; // 둥근 달 이모티콘

const foods = [
  {
    name: "송편",
    description: "한 해의 수확에 감사하며, 둥근 달을 닮아 예쁘게 빚어내는 명절의 아이콘입니다.",
    emoji: "🍡" // 송편/경단 이모티콘
  },
  {
    name: "전 (부침개)",
    description: "지글지글 기름 냄새와 함께 가족들의 정이 오가는, 명절 분위기 메이커입니다.",
    emoji: "🍳" // 프라이팬/요리 이모티콘
  },
  {
    name: "갈비찜",
    description: "달콤짭짤한 양념에 푹 재운 부드러운 갈비. 남녀노소 모두가 기다리는 잔치 음식의 왕입니다.",
    emoji: "🍖" // 고기 이모티콘
  }
];

const plays = [
  {
    name: "윷놀이",
    description: "네 개의 윷가락으로 '모' 아니면 '도'! 온 가족의 승부욕을 자극하는 전통 보드게임입니다.",
    emoji: "🎲" // 주사위 이모티콘
  },
  {
    name: "강강술래",
    description: "밝은 보름달 아래, 여성들이 손을 잡고 돌며 풍요를 기원하던 아름다운 화합의 춤입니다.",
    emoji: "💃" // 춤추는 이모티콘
  },
  {
    name: "씨름",
    description: "두 장사가 샅바를 잡고 힘과 기술을 겨루는, 박진감 넘치는 우리의 전통 스포츠입니다.",
    emoji: "🤼" // 씨름/레슬링 이모티콘
  }
];
</script>

<template>
  <div class="container">

    <header class="hero-header">
      <div class="hero-content">
        <span class="hero-emoji">{{ mainEmoji }}</span>
        <h1>{{ mainTitle }}</h1>
        <p>{{ mainSubtitle }}</p>
      </div>
    </header>

    <main class="content-wrapper">
      <section class="content-section">
        <h2><span class="emoji">😋</span> 한가위, 무엇을 먹을까?</h2>
        <div class="card-grid">
          <div class="card" v-for="food in foods" :key="food.name">
            <div class="card-content">
              <span class="card-emoji">{{ food.emoji }}</span>
              <h3>{{ food.name }}</h3>
              <p>{{ food.description }}</p>
            </div>
          </div>
        </div>
      </section>

      <section class="content-section">
        <h2><span class="emoji">🤹</span> 한가위, 무엇을 하고 놀까?</h2>
        <div class="card-grid">
          <div class="card" v-for="play in plays" :key="play.name">
            <div class="card-content">
              <span class="card-emoji">{{ play.emoji }}</span>
              <h3>{{ play.name }}</h3>
              <p>{{ play.description }}</p>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="site-footer">
      <p>즐겁고 풍요로운 한가위 보내세요! 🎑</p>
      <p>Made by <strong>s44158619-code</strong></p>
    </footer>
  </div>
</template>

<style>
/* 쌈뽕한 폰트 적용 (Google Fonts) */
@import url('https://fonts.googleapis.com/css2?family=Nanum+Gothic:wght@400;700&display=swap');

/* 기본 스타일 초기화 및 설정 */
body {
  font-family: 'Nanum Gothic', 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f0f2f5; /* 더 세련된 배경색 */
  color: #333;
}

.container {
  max-width: 1100px;
  margin: 0 auto;
  overflow: hidden;
}

/* 1. 쌈뽕한 헤더 (이모티콘 Ver.) */
.hero-header {
  /* 쌈뽕한 그라데이션 배경 */
  background-image: linear-gradient(135deg, #6c5ce7 0%, #4a4eee 100%);
  color: white;
  padding: 60px 20px;
  text-align: center;
  border-radius: 0 0 20px 20px;
  margin-bottom: 40px;
  box-shadow: 0 10px 20px rgba(0,0,0,0.1);
}

.hero-emoji {
  font-size: 6rem; /* 이모티콘 크기 왕창 키움 */
  line-height: 1;
  display: block;
  margin-bottom: 20px;
  text-shadow: 0 4px 10px rgba(0,0,0,0.2);
}

.hero-content h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin: 0;
  text-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.hero-content p {
  font-size: 1.5rem;
  margin-top: 10px;
  opacity: 0.9;
}

/* 2. 쌈뽕한 콘텐츠 섹션 */
.content-wrapper {
  padding: 0 20px;
}
.content-section {
  background-color: #ffffff;
  padding: 30px;
  border-radius: 12px;
  margin-bottom: 30px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.05);
}
.content-section h2 {
  font-size: 2.2rem;
  font-weight: 700;
  color: #2c3e50;
  border-bottom: 3px solid #6c5ce7;
  padding-bottom: 15px;
  margin-bottom: 25px;
  display: flex;
  align-items: center;
}
.emoji {
  font-size: 2.5rem;
  margin-right: 15px;
}

/* 3. 쌈뽕한 카드 (이모티콘 Ver.) */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 25px;
}
.card {
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-out, box-shadow 0.3s ease-out;
  padding: 20px; /* 카드 안쪽 여백 */
}
.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

/* .card-image 클래스 삭제됨 */

.card-content {
  padding: 0; /* 내부 패딩은 card가 담당 */
  text-align: center; /* 모든걸 가운데 정렬 */
}

.card-emoji {
  font-size: 4rem; /* 카드 이모티콘 크기 키움 */
  line-height: 1;
  display: block;
  margin-bottom: 20px;
}

.card h3 {
  font-size: 1.6rem;
  font-weight: 700;
  color: #333;
  margin: 0 0 10px 0;
}
.card p {
  font-size: 1rem;
  color: #555;
  line-height: 1.6;
}

/* 4. 쌈뽕한 푸터 */
.site-footer {
  text-align: center;
  margin-top: 40px;
  padding: 30px 20px;
  background-color: #2c3e50;
  color: #f0f2f5;
}
.site-footer p {
  margin: 5px 0;
  font-size: 1rem;
}
.site-footer strong {
  color: #a7c5eb;
}

/* 모바일 반응형 (동일) */
@media (max-width: 768px) {
  .hero-content h1 {
    font-size: 2.5rem;
  }
  .hero-content p {
    font-size: 1.2rem;
  }
  .content-section h2 {
    font-size: 1.8rem;
  }
  .card-grid {
    grid-template-columns: 1fr;
  }
}
</style>