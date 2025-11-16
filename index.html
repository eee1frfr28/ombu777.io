// 랜덤 돌 생성 함수 (미니멀 + 불규칙 윤곽)
function createStone() {
  return {
    x: random(width) - width / 2,
    y: random(40, 120),   // 바닥 근처
    z: random(1, 5),      // 깊이
    r: random(14, 40),    // 돌 크기
    seed: random(1000),   // noise 시드
    steps: int(random(14, 28)), // 윤곽 정점 개수
    wobble: random(0.2, 0.8),   // 일그러짐 정도
  };
}

const StonePath = {
  stones: [],

  init() {
    for (let i = 0; i < 26; i++) {   // 돌 개수 줄임
      this.stones.push(createStone());
    }
  },

  update() {
    for (const s of this.stones) {
      // 카메라 패닝 효과
      s.x -= (mouseX - width / 2) * 0.03;

      // 화면 좌우 루프
      if (s.x > width / 2) s.x = -width / 2;
      if (s.x < -width / 2) s.x = width / 2;

      // 깊이 업데이트
      const my = constrain(mouseY, 0, height);
      s.z -= log(1 + my) / 200;

      if (s.z < 1) s.z = 5;
    }

    // 가까운 돌 먼저 그리기
    this.stones.sort((a, b) => b.z - a.z);
  },

  draw() {
    stroke(0);
    noFill();

    for (const s of this.stones) {
      push();

      // 원근 변환
      const px = s.x / s.z;
      const py = (200 + s.y) / s.z;
      const rr = s.r / s.z;

      translate(px, py);

      // 미니멀한 불규칙 윤곽 돌 그리기
      beginShape();
      for (let i = 0; i < s.steps; i++) {
        const a = map(i, 0, s.steps, 0, TWO_PI);

        let n = noise(
          s.seed + cos(a) * s.wobble,
          s.seed + sin(a) * s.wobble,
          frameCount * 0.002
        );

        const rad = rr * (0.6 + n * 0.9);
        const vx = cos(a) * rad;
        const vy = sin(a) * rad * 0.7;

        vertex(vx, vy);
      }
      endShape(CLOSE);

      pop();
    }
  },
};

function setup() {
  createCanvas(900, 600);
  StonePath.init();
}

function draw() {
  background(255);

  // 화면 중앙 아래 기준
  translate(width / 2, height / 2 + 80);

  StonePath.update();
  StonePath.draw();
}
