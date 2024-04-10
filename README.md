<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>미니인턴 클론 페이지</title>
<style>
    /* 슬라이드 컨테이너 스타일 */
    .slider-container {
        width: 80%;
        margin: auto;
        position: relative;
        overflow: hidden;
        border: 1px solid #ddd;
    }

    /* 슬라이드 이미지 스타일 */
    .slide {
        display: none;
        width: 100%;
    }

    /* 활성화된 슬라이드 스타일 */
    .active {
        display: block;
    }

    /* 네비게이션 스타일 */
    .navigation {
        position: absolute;
        bottom: 10px;
        left: 50%;
        transform: translateX(-50%);
        z-index: 100;
    }

    /* 화살표 스타일 */
    .navigation button {
        background: transparent;
        border: none;
        cursor: pointer;
        font-size: 24px;
        margin: 0 10px;
    }
</style>
</head>
<body>

<div class="slider-container">
    <div class="slide active">
        <h2>첫 번째 슬라이드</h2>
        <p>이곳에 첫 번째 슬라이드 내용을 추가하세요.</p>
    </div>
    <div class="slide">
        <h2>두 번째 슬라이드</h2>
        <p>이곳에 두 번째 슬라이드 내용을 추가하세요.</p>
    </div>
    <div class="slide">
        <h2>세 번째 슬라이드</h2>
        <p>이곳에 세 번째 슬라이드 내용을 추가하세요.</p>
    </div>

    <div class="navigation">
        <button onclick="prevSlide()">&#10094;</button>
        <button onclick="nextSlide()">&#10095;</button>
    </div>
</div>

<script>
    let slideIndex = 0;
    const slides = document.querySelectorAll('.slide');

    function showSlide(n) {
        if (n >= slides.length) {
            slideIndex = 0;
        }
        if (n < 0) {
            slideIndex = slides.length - 1;
        }

        slides.forEach(slide => slide.classList.remove('active'));
        slides[slideIndex].classList.add('active');
    }

    function nextSlide() {
        slideIndex++;
        showSlide(slideIndex);
    }

    function prevSlide() {
        slideIndex--;
        showSlide(slideIndex);
    }

    // 자동 슬라이드 기능 추가 (선택사항)
    setInterval(() => {
        nextSlide();
    }, 5000);
</script>

</body>
</html>
