> "Do. Or Do not. There is no Try." — Yoda
> — added by Andrew Veda (English) | about: This quote increases my desire to just try!

> "Ever tried. Ever failed. No matter. Try again. Fail again. Fail better." — Samuel Beckett
> — added by Andrew Veda | about: This quote has destroyed my fear of failure! 

> "As long as I live, There are infinite chances" — Luffy
> — added by Meenz | about: Life itself gives endless opportunities 

ADD YOUR QUOTES BELOW THIS LINE.
<script>
const QUOTES_URL =
"https://raw.githubusercontent.com/andrewveda/a-quote-a-day/main/QUOTES.md";

fetch(QUOTES_URL)
.then(r => r.text())
.then(text => {

  const quotes = text
    .split("\n")
    .map(q => q.trim())
    .filter(q => q.length > 10);

  const track = document.getElementById("quoteCarouselTrack");
  const dots = document.getElementById("carouselDots");

  if (!track || !quotes.length) return;

  const carouselQuotes = shuffle(quotes).slice(0,6);

  carouselQuotes.forEach((q,i)=>{
    track.innerHTML += `<div class="carousel-item">${q}</div>`;
    dots.innerHTML += `<span class="dot ${i===0?'active':''}"></span>`;
  });

  let index = 0;

  setInterval(()=>{
    index = (index+1) % carouselQuotes.length;
    track.style.transform = `translateX(-${index*100}%)`;

    document.querySelectorAll(".dot").forEach((d,i)=>{
      d.classList.toggle("active", i===index);
    });

  }, 5000);

});

function shuffle(arr){
  return [...arr].sort(()=>Math.random()-0.5);
}
</script>
