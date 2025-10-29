<script setup lang="ts">
// 이미지 URL을 바로 데이터로 사용 (로컬 파일 없음!)
const mainImage = "https://images.unsplash.com/photo-1597839219228-e8c09b0e5d9c?q=80&w=1974&auto=format&fit=crop";

const mainTitle = "가장 밝은 달, 한가위";
const mainSubtitle = "마음까지 넉넉해지는 풍성한 추석. 잊지 못할 전통과 맛의 향연에 여러분을 초대합니다.";

const foods = [
  {
    name: "송편 (松편)",
    description: "한 해의 수확에 감사하며, 둥근 달을 닮아 예쁘게 빚어내는 명절의 아이콘입니다.",
    image: "https://images.unsplash.com/photo-1632778730502-317160de1d52?q=80&w=1964&auto=format&fit=crop"
  },
  {
    name: "전 (부침개)",
    description: "지글지글 기름 냄새와 함께 가족들의 정이 오가는, 명절 분위기 메이커입니다.",
    image: "https://images.unsplash.com/photo-1590448062016-561b3906416a?q=80&w=1974&auto=format&fit=crop"
  },
  {
    name: "갈비찜",
    description: "달콤짭짤한 양념에 푹 재운 부드러운 갈비. 남녀노소 모두가 기다리는 잔치 음식의 왕입니다.",
    image: "https://images.unsplash.com/photo-1630983174240-b605c08f8f2d?q=80&w=2070&auto=format&fit=crop"
  }
];

const plays = [
  {
    name: "윷놀이",
    description: "네 개의 윷가락으로 '모' 아니면 '도'! 온 가족의 승부욕을 자극하는 전통 보드게임입니다.",
    image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Yutnori_MAL.jpg/1280px-Yutnori_MAL.jpg"
  },
  {
    name: "강강술래",
    description: "밝은 보름달 아래, 여성들이 손을 잡고 돌며 풍요를 기원하던 아름다운 화합의 춤입니다.",
    image: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Ganggangsullae_in_Haeundae_01.jpg/1280px-Ganggangsullae_in_Haeundae_01.jpg"
  },
  {
    name: "씨름",
    description: "두 장사가 샅바를 잡고 힘과 기술을 겨루는, 박진감 넘치는 우리의 전통 스포츠입니다.",
    image: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/A_ssireum_match.jpg/1280px-A_ssireum_match.jpg"
  }
];
</script>

<template>
  <div class="container">
    <header class="hero-header">
      <img :src="mainImage" alt="한가위 보름달" class="hero-image">
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <h1>{{ mainTitle }}</h1>
        <p>{{ mainSubtitle }}</p>
      </div>
    </header>

    <main class="content-wrapper">
      <section class="content-section">
        <h2><span class="emoji">😋</span> 한가위, 무엇을 먹을까?</h2>
        <div class="card-grid">
          <div class="card" v-for="food in foods" :key="food.name">
            <img :src="food.image" :alt="food.name" class="card-image">
            <div class="card-content">
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
            <img :src="play.image" :alt="play.name" class="card-image">
            <div class="card-content">
              <h3>{{ play.name }}</h3>
              <p>{{ play.description }}</p>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="site-footer">
      <p>즐겁고 풍요로운 한가위 보내세요! 🌕</p>
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
  overflow: hidden; /* 그림자 잘림 방지 */
}

/* 1. 쌈뽕한 헤더 (히어로 이미지) */
.hero-header {
  position: relative;
  width: 100%;
  height: 60vh; /* 화면 높이의 60% */
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: white;
  margin-bottom: 40px;
}

.hero-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover; /* 이미지가 찌그러지지 않게 */
  z-index: 1;
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5); /* 어둡게 오버레이 */
  z-index: 2;
}

.hero-content {
  position: relative;
  z-index: 3;
  padding: 20px;
  text-shadow: 0 2px 4px rgba(0,0,0,0.5); /* 텍스트 그림자 */
}

.hero-content h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin: 0;
}

.hero-content p {
  font-size: 1.5rem;
  margin-top: 10px;
}

/* 메인 콘텐츠 래퍼 */
.content-wrapper {
  padding: 0 20px;
}

/* 2. 쌈뽕한 콘텐츠 섹션 */
.content-section {
  background-color: #ffffff;
  padding: 30px;
  border-radius: 12px;
  margin-bottom: 30px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.05); /* 입체감 */
}

.content-section h2 {
  font-size: 2.2rem;
  font-weight: 700;
  color: #2c3e50;
  border-bottom: 3px solid #6c5ce7; /* 쌈뽕한 보라색 포인트 */
  padding-bottom: 15px;
  margin-bottom: 25px;
  display: flex;
  align-items: center;
}

.emoji {
  font-size: 2.5rem;
  margin-right: 15px;
}

/* 3. 쌈뽕한 카드 그리드 */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 25px;
}

.card {
  background: #fff;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-out, box-shadow 0.3s ease-out;
}

.card:hover {
  transform: translateY(-8px); /* 쌈뽕한 호버 효과 */
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.card-image {
  width: 100%;
  height: 220px;
  object-fit: cover;
  display: block;
}

.card-content {
  padding: 20px;
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
  background-color: #2c3e50; /* 어두운 배경 */
  color: #f0f2f5;
}

.site-footer p {
  margin: 5px 0;
  font-size: 1rem;
}

.site-footer strong {
  color: #a7c5eb; /* 닉네임 강조 */
}

/* 모바일 반응형 */
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
    grid-template-columns: 1fr; /* 모바일에선 1열로 */
  }
}
</style>