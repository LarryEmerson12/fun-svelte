<script>
    let myYear = 2024;
    let currentYear = new Date().getFullYear();
    let time = currentYear - myYear;
    let likely = "like";

    if ( time > 2 ) {
        likely = "was";
    }
</script>

<h1>About this website</h1>
<p>This website was built for beginners <span id="zoom">( {likely} me )</span> to explore svelte.</p>
<p>It was built in {myYear}.</p>
<p>It has been {time} years since it was built.</p>
<p>If you are a beginner and want to use this, you can go to my Github profile to see the source code.</p>

<br>

<div>
    <h1 id="primary">Other pages</h1>
    <a href="/" id="button">Home</a>
    <a href="/fun" id="button">Fun</a>
  </div>