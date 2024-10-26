<script lang="ts">
  let name = "^_^";
  function changeName() {
    name = (document.getElementById("name") as HTMLInputElement).value;
    if (name === "") {
      name = "*_*";
    }
    document.getElementById("primary")!.innerText = name;
  }

  function dum() {
    document.getElementById("dumbometer")!.innerText = "I am dum";
  }

  function smart() {
    document.getElementById("dumbometer")!.innerText = "I am smart";
  }

  let age = 0;

  function addAge() {
    age++;
  }

  let ms = 0;

  setInterval(() => {
    ms++;
  }, 1);

  let birth = 0;

  function calculate() {
    let year = new Date().getFullYear();
    birth = parseInt(
      (document.getElementById("birth") as HTMLInputElement).value
    );
    age = year - birth;
  }

  let item = "yoyo";

  function getItem() {
    item = (document.getElementById("item") as HTMLInputElement).value;
    if (item === "") {
      item = "yoyo";
    }
  }

  let number = 0;

  function getNumber() {
    number = parseInt(
      (document.getElementById("number") as HTMLInputElement).value
    );
    if (isNaN(number)) {
      number = 0;
    }
  }

  let progressValue = 0;

  function changeProgressValue() {
    progressValue = 0;
    setInterval(() => {
      progressValue++;
      if (progressValue > 100) {
        progressValue = 100;
      }
    }, 10);
  }

  let pwdMessage = "You have not set a password.";

  function submitPwd() {
    let pwd = (document.getElementById("pwd") as HTMLInputElement).value;
    if (pwd === "") {
      pwdMessage = "You have not set a password.";
    } else {
      pwdMessage = "Your password is: " + pwd;
    }
  }
</script>

<div>
  <h1>Hello, <span id="primary">{name}</span>!</h1>
  <input id="name" placeholder="Enter your name" />
  <button on:click={changeName}>Change Name</button>
</div>

<br />

<div>
  <h1 id="dumbometer">Are you dum?</h1>
  <button on:click={dum}>Yes</button>
  <button on:click={smart}>No</button>
</div>

<br />

<div>
  <h1>Age: {age}</h1>
  <button on:click={addAge}>Change Age</button>
</div>

<br />

<div>
  <h1>
    Stopwatch: {ms} millisecond{#if ms > 1}s{/if}
  </h1>
</div>

<br />

<div>
  <h1>You are {age} years old now.</h1>
  <input id="birth" placeholder="Enter your birth year" />
  <button on:click={calculate}>Calculate</button>
  <span id="primary">
    {#if age >= 18}
      You are an adult.
    {:else if age <= 18 && age > 0}
      You are a child.
    {:else if age < 0}
      You are not born yet.
    {:else}
      You are a baby.
    {/if}
  </span>
</div>

<br />

<div>
  <h1>What is your favourite item?</h1>
  <input id="item" placeholder="Enter favourite item" />
  <button on:click={getItem}>Let's see...</button>
  <span id="primary">Your favourite item is your {item}.</span>
</div>

<br />

<div>
  <h1>What is your favourite number?</h1>
  <input id="number" placeholder="Enter favourite number" />
  <button on:click={getNumber}>Let's see...</button>
  <span id="primary">Your favourite number is {number}.</span>
</div>

<br />

<div>
  <h1>Choose a phone</h1>
  <span>I like</span>
  <select>
    <option value="iphone">iPhone</option>
    <option value="samsung">Samsung</option>
    <option value="nokia">Nokia</option>
  </select>
</div>

<br />

<div>
  <h1>Do you want to load this?</h1>
  <button on:click={changeProgressValue}>Yes ( and never no? )</button>
  <progress value={progressValue} max="100"></progress>
</div>

<br />

<div>
  <h1>What password would you choose for your computer?</h1>
  <input id="pwd" type="password" placeholder="Enter password" />
  <button on:click={submitPwd}>Submit</button>
  <span id="primary">{pwdMessage}</span>
</div>

<br>

<div>
  <h1 id="primary">Other pages</h1>
  <a href="/" id="button">Home</a>
  <a href="/about" id="button">About</a>
</div>