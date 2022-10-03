<script>
  let name = "";
  let email = "";
  let state = "";
  function submitEmail() {
    let data = '{ "email": "' + email + '", "first_namer": "' + name + '", "from_where": "ivo-henri"}';
    fetch("https://apps.crewnew.com/api/rest/subscribe2", {
      method: "POST",
      body: data,
      headers: {
        "Content-type": "application/json; charset=UTF-8",
        "x-hasura-admin-secret": "Yd3L3tExefP5AUyP",
      },
    })
      .then((res) => {
        if (!res.ok) {
          throw new Error("An error occurred, please try again!");
        }
        return res.json();
      })
      .then((data) => {
        console.log(data);
        state = "sent";
      })
      .catch((err) => {
        console.log(err);
      });
  }
</script>

<section class="ftco-section">
  <div class="container">
    <div class="row justify-content-center">
      <div class="text-center mb-5">
        <h2 class="heading-section">
          Kas sa tahad, et su raha kasvaks stabiilselt, ilma selle jaoks ise
          suurt tegemata? 💡
        </h2>
        <h2 class="heading-section">
          Kas sa otsid konstantset rahavoogu, mis voimaldaks Sulle rahu ja
          meeldivat keskkonda elamiseks? 🧘🏽‍♂️
        </h2>
        <h2 class="heading-section">
          Kas Sa oled kunagi mõelnud, miks Eestis investeerimine nii tabu ja
          tundlik teema on? Miks ta tekitab sellist emotsiooni? 🤷🏽‍♂️
        </h2>
        <h2 class="heading-section">
          Väga lihtsalt põhjusel, sest meie 🇪🇪 riik on alles 31 aastat tagasi
          taas-iseseisvunud. Inimesed kardavad seda, mida nad ei tea.
        </h2>
        <h2 class="heading-section">
          Hirmu saab eemaldada, tuginedes kogukonnale, kel on antud valdkonnas
          rohkem kogemust. 🔑
        </h2>
        <h2 class="heading-section">
          Usas on vanaisad, kes räägivad jõululaua taga, kuidas nende
          kasutatavad fondid või aktsiad on terve elu üles sõitnud. Palju meil
          selliseid vanaisasid on? ❌
        </h2>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="col-md-10">
        <div class="wrapper">
          <div class="row no-gutters">
            <div class="col-md-6">
              <div class="contact-wrap w-100 p-lg-5 p-4">
                <h3 class="mb-4">Sisesta siia enda</h3>
                <div id="form-message-warning" class="mb-4" />
                {#if state === "sent"}
                <div id="form-message-success" class="mb-4">
                  Korras! Vaata oma emaili varsti!
                </div>
                {/if}
               
                  <div class="row">
                    <div class="col-md-12">
                      <div class="form-group">
                        <input
                          type="text"
                          class="form-control"
                          value={name}
                          on:input={(event) => (name = event.target.value)}
                          placeholder="Nimi"
                        />
                      </div>
                    </div>
                    <div class="form-text">ja</div>
                    <div class="col-md-12">
                      <div class="form-group">
                        <input
                          type="email"
                          class="form-control"
                          value={email}
                          on:input={(event) => (email = event.target.value)}
                          placeholder="E-mail"
                        />
                      </div>
                    </div>
                    <div class="form-text">Saadan Sulle video lingi.</div>
                    <div class="col-md-12">
                      <div class="form-group">
                        <input
                          type="submit"
                          value="SAADA!"
                          class="btn btn-primary"
                          on:click={submitEmail}
                        />
                        <div class="submitting" />
                      </div>
                    </div>
                  </div>
   
              </div>
            </div>
            <div class="col-md-6 d-flex align-items-stretch">
              <div class="info-wrap w-100 p-lg-5 p-4 img">
                <div class="dbox w-100 d-flex align-items-start">
                  <div
                    class="d-flex align-items-center justify-content-center"
                  />
                  <div class="text pl-3">
                    <p>
                      <span
                        >Tänaseks olen ma juba pea 5 aastat igapäevaselt
                        finantsturgudel osalenud. 👨🏽‍💻
                      </span>
                    </p>
                  </div>
                </div>
                <div class="dbox w-100 d-flex align-items-start">
                  <div
                    class="d-flex align-items-center justify-content-center"
                  />
                  <div class="text pl-3">
                    <p>
                      <span
                        >Selle ajaga on mul tekkinud 2 kapitali kasvatamise
                        tööriista, mis mulle enim meeldivad. 🧰
                      </span>
                    </p>
                  </div>
                </div>
                <div class="dbox w-100 d-flex align-items-start">
                  <div
                    class="d-flex align-items-center justify-content-center"
                  />
                  <div class="text pl-3">
                    <p>
                      <span
                        >Siin on 5 minutiline video ülevaade kahest täielikult
                        automatiseeritud tööriistast ja selgitus- kuidas ma neid
                        kasutan.
                      </span>
                    </p>
                  </div>
                </div>
                <div class="dbox w-100 d-flex align-items-center">
                  <div class="flex align-items-center justify-content-center" />
                  <div class="text pl-3">
                    <p><span>✅ 1-3h üles seadmine. </span></p>
                  </div>
                </div>
                <div class="dbox w-100 d-flex align-items-center">
                  <div
                    class="d-flex align-items-center justify-content-center"
                  />
                  <div class="text pl-3">
                    <p>
                      <span
                        >✅ Juriidiliselt ja riiklikult (1 nendest) reguleeritud
                        ettevõtted.
                      </span>
                    </p>
                  </div>
                </div>
                <div class="dbox w-100 d-flex align-items-center">
                  <div
                    class="d-flex align-items-center justify-content-center"
                  />
                  <div class="text pl-3">
                    <p>
                      <span
                        >Millal sa ärkad ja mõistad, et internetis ringleb terve
                        kuhi lahendusi? 🔐</span
                      >
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="crewnew">
    <a href="https://crewnew.com">Developed by CrewNew.com</a>
  </div>
</section>

<style>
  .form-text {
    color: white;
    font-size: x-large;
    margin: 0.5em;
  }
  .crewnew {
    text-align: center;
  }
</style>
