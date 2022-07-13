<template>
  <body style="background: aliceblue;">
  <h1 id="h1">Gerador de QR-CODE</h1>
  <form action="">
    <input placeholder="DIGITE AQUI" id="input"><br><br>
    <input @click.prevent="gerar" type="submit" id="send" value="Gerar">
  </form>
<span id="message">

</span>

  <div id="img" class="badge-base LI-profile-badge" data-locale="pt_BR" data-size="medium" data-theme="light" data-type="VERTICAL" data-version="v1">

  </div>
  </body>
</template>

<script>
export default {
  name: 'App',
  methods: {
    gerar: () => {
      const btn = document.querySelector("#send");
      btn.addEventListener("click", function(e) {
        e.preventDefault();
        const URL = document.querySelector("#input");
        const valueURL = URL.value
        const url = `https://api.qrserver.com/v1/create-qr-code/?data=${valueURL}&size=250x250`
        const img = document.createElement('img');
        img.src = `${url}`
        const message = document.createElement('h6')
        const container1 = document.querySelector("#message")
        container1.appendChild(message)
        const container = document.querySelector("#img")
        container.appendChild(img);
      })
}
  }
}
</script>

<style>
body {
  text-align: center;
  margin-top: 60px;
}
#img {
  padding: 100px;
}
#linke {
  align-content: center;
  align-items: center;
  display: inline-block;
}
#input {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: aliceblue;

  padding: 6px;
  top: 90px;
  text-align-last: center;
  outline-style: double;
  position: relative;
}
#send {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: aliceblue;

  cursor: pointer;
  position: relative;
  top: 100px;
  padding: 10px;
  text-decoration: overline;
  border: revert;
  border-radius: 100px;
}
#h1 {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: aliceblue;

  position: relative;
  top: 40px;
}
</style>
