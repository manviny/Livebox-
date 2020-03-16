// npm init
// npm install --save nightmare
// node index.js


const Nightmare = require('nightmare')
// const nightmare = Nightmare({ show: true, openDevTools: { detach: true } })
const nightmare = Nightmare()


async function asyncCall() {
    try {

      // 1.- Entra en la pantalla principal y logeate
      const first = await nightmare
        .useragent('Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/46.0.2490.80 Safari/537.36')
        .viewport(1200, 950)      
        .goto('http://192.168.1.1/firstlogin.htm')
        .wait(3001)
        .evaluate(function() {
          // pon password en el input y click
          window.frames["mainFrame"].document.querySelector("#mainContent > table > tbody > tr > td:nth-child(2) > ul > li:nth-child(2) > div.readonly > input[type=password]" ).value="************";
          window.frames["mainFrame"].document.querySelector("#bt_save" ).click();
          return ("1 logeado");
        })

      // 2.- Ves a la pantalla de configuracion avanzada
      const second = await nightmare
        .wait(3001)
        .evaluate(function() {
          window.frames["topFrame"].document.querySelector("#hmenu-advconfig" ).click();

          return("2 configuracion avanzada")
        })

      //3.- Ves a la pantalla de firewall
      const third = await nightmare
        .wait(7001)
        .evaluate(function() {
          window.frames["mainFrame"].document.querySelector("[href='advanced_firewall.htm']" ).click();
          return("3 firewall")
        })

      //4.- Ves a la pantalla de LV2(alto) LV1(medio)
      const fourth = await nightmare
        .wait(3001)
        .evaluate(function() {
          window.frames["mainFrame"].document.querySelector("#LV2" ).click();
          return("4 firewall LV2")
        })

      //5.- Ves a la pantalla de LV2(alto) LV1(medio)
      const fifth = await nightmare
        .wait(3001)
        .evaluate(function() {
          window.frames["mainFrame"].document.querySelector("#bt_save" ).click();
          return("5 guardada configuracion")
        })

      //6.- Ves a la pantalla de LV2(alto) LV1(medio)
      const sixth = await nightmare
        .wait(3001)
        .evaluate(function() {
          window.frames["mainFrame"].document.querySelector("#msgbox-button1" ).click();
          return("6 confirmada configuracion")
        })

      //6.- Ves a la pantalla de LV2(alto) LV1(medio)
      const seventh = await nightmare
        .wait(4001)
        .evaluate(function() {
          window.frames["topFrame"].document.querySelector("[href='#']" ).click();
          return("7 salir")
        })

       console.log(first, second, third, fourth, fifth, sixth, seventh);

      await nightmare.end()
    } catch (error) {
      console.log(error);
      throw error;
    }
}

asyncCall();

