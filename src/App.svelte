<script>
  import { scale } from "svelte/transition";
  import { quintOut } from "svelte/easing";
  import { onMount } from "svelte";

  let ready = false;
  onMount(() => (ready = true));

  const topText = [
    {
      id: 1,
<<<<<<< HEAD
      txt: "Kas sa tahad, et su raha kasvaks stabiilselt, ilma selle jaoks ise suurt tegemata? 💡"},
=======
      txt: "Kas sa tahad, et su raha kasvaks stabiilselt, ilma selle jaoks ise suurt tegemata? 💡",
    },
>>>>>>> parent of e70efc7 (Update App.svelte)
    {
      id: 100,
      txt: "Kas sa otsid konstantset rahavoogu, mis voimaldaks Sulle rahu ja meeldivat keskkonda elamiseks? 🧘🏽‍♂️",
    },
    {
      id: 200,
      txt: "Kas Sa oled kunagi mõelnud, miks Eestis investeerimine nii tabu ja tundlik teema on? Miks ta tekitab sellist emotsiooni? 🤷🏽‍♂️",
    },
    {
      id: 300,
      txt: "Väga lihtsalt põhjusel, sest meie 🇪🇪 riik on alles 31 aastat tagasi taas-iseseisvunud. Inimesed kardavad seda, mida nad ei tea.",
    },
    {
      id: 400,
      txt: "Hirmu saab eemaldada, tuginedes kogukonnale, kel on antud valdkonnas rohkem kogemust. 🔑",
    },
    {
      id: 500,
<<<<<<< HEAD
      txt: "Usas on vanaisad, kes räägivad jõululaua taga, kuidas nende kasutatavad fondid või aktsiad on terve elu üles sõitnud. Palju meil selliseid vanaisasid on? ❌"},
=======
      txt: "Usas on vanaisad, kes räägivad jõululaua taga, kuidas nende kasutatavad fondid või aktsiad on terve elu üles sõitnud. Palju meil selliseid vanaisasid on? ❌",
    },
>>>>>>> parent of e70efc7 (Update App.svelte)
  ];

  const bottomText = [
    {
<<<<<<< HEAD
      id: 100,
      txt: "Kas sa otsid konstantset rahavoogu, mis voimaldaks Sulle rahu ja meeldivat keskkonda elamiseks? 🧘🏽‍♂️",
    },
    {
      id: 200,
      txt: "Kas Sa oled kunagi mõelnud, miks Eestis investeerimine nii tabu ja tundlik teema on? Miks ta tekitab sellist emotsiooni? 🤷🏽‍♂️",
    },
    {
      id: 300,
      txt: "Väga lihtsalt põhjusel, sest meie 🇪🇪 riik on alles 31 aastat tagasi taas-iseseisvunud. Inimesed kardavad seda, mida nad ei tea.",
    },
    {
      id: 400, txt: "Hirmu saab eemaldada, tuginedes kogukonnale, kel on antud valdkonnas rohkem kogemust. 🔑"
    },
    {
      id: 500,
      txt: "Usas on vanaisad, kes räägivad jõululaua taga, kuidas nende kasutatavad fondid või aktsiad on terve elu üles sõitnud. Palju meil selliseid vanaisasid on? ❌",
    },
    {
      id: 400,
      txt: "Tänaseks olen ma juba pea 5 aastat igapäevaselt finantsturgudel osalenud. 👨🏽‍💻",
    },
    {
      id: 500, txt: "Tänaseks olen ma juba pea 5 aastat igapäevaselt finantsturgudel osalenud. 👨🏽‍💻",
    },
    {
      id: 500, txt: "Tänaseks olen ma juba pea 5 aastat igapäevaselt finantsturgudel osalenud. 👨🏽‍💻" },
    {
      id: 500, txt: "Selle ajaga on mul tekkinud 2 kapitali kasvatamise tööriista, mis mulle enim meeldivad. 🧰",
=======
      id: 400,
      txt: "Tänaseks olen ma juba pea 5 aastat igapäevaselt finantsturgudel osalenud. 👨🏽‍💻",
    },
    {
      id: 500,
      txt: "Selle ajaga on mul tekkinud 2 kapitali kasvatamise tööriista, mis mulle enim meeldivad. 🧰",
>>>>>>> parent of e70efc7 (Update App.svelte)
    },
    {
      id: 600,
      txt: "Siin on 5 minutiline video ülevaade kahest täielikult automatiseeritud tööriistast ja selgitus- kuidas ma neid kasutan.",
    },
    {
      id: 700,
      txt: "✅ 1-3h üles seadmine.",
    },
    {
<<<<<<< HEAD
      id: 800, txt: "Oktoobris on vabu kohti veel alles ainult 8, ära maga oma võimalust maha ja liitu täna. 🧨 (7 päeva raha tagasi garantii) ", txt: "✅ Juriidiliselt ja riiklikult (1 nendest) reguleeritud ettevõtted.",
=======
      id: 800,
      txt: "✅ Juriidiliselt ja riiklikult (1 nendest) reguleeritud ettevõtted.",
>>>>>>> parent of e70efc7 (Update App.svelte)
    },
    {
      id: 900,
      txt: "Millal sa ärkad ja mõistad, et internetis ringleb terve kuhi lahendusi? 🔐",
<<<<<<< HEAD
<<<<<<< HEAD
<<<<<<< HEAD
>>>>>>> parent of e70efc7 (Update App.svelte)
=======
>>>>>>> parent of e70efc7 (Update App.svelte)
=======
>>>>>>> parent of e70efc7 (Update App.svelte)
=======
>>>>>>> parent of e70efc7 (Update App.svelte)
    },
  ];
  let name = "";
  let email = "";
  let state = "";
  function submitEmail() {
    let data =
      '{ "email": "' +
      email +
      '", "first_namer": "' +
      name +
      '", "from_where": "ivo-henri"}';
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

{#if ready}
  <section class="ftco-section">
    <div class="container">
      <div class="row justify-content-center">
        <div class="text-center mb-5">
          {#each topText as text (text.id)}
            <h2
              class="heading-section"
              transition:scale={{
                delay: text.id,
                duration: 500,
                easing: quintOut,
              }}
            >
              {text.txt}
            </h2>
          {/each}
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-md-10">
          <div class="wrapper">
            <div class="row no-gutters">
              <div class="col-md-6 d-flex align-items-stretch">
                <div class="info-wrap w-100 p-lg-5 p-4 img">
                  {#each bottomText as text (text.id)}
                    <div
                      class="dbox w-100 d-flex align-items-center"
                      transition:scale={{
                        delay: 300,
                        duration: 800,
                        easing: quintOut,
                      }}
                    >
                      <div
                        class="flex align-items-center justify-content-center"
                      />
                      <div class="text pl-3">
                        <p><span>{text.txt}</span></p>
                      </div>
                    </div>
                  {/each}
                </div>
              </div>
              <div class="col-md-6">
                <div class="contact-wrap w-100 p-lg-5 p-4">
                  <h3 class="mb-4">Sisesta siia enda</h3>
                  <div id="form-message-warning" class="mb-4" />
                  {#if state === "sent"}
                    <div id="form-message-success" class="mb-4" in:scale>
                      Korras! Vaata oma emaili varsti! Kui ka 2-3min pärast ei
                      paista emaili, siis vaata igaks juhuks ka spämmboksi!
                    </div>
                  {:else}
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
                  {/if}
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
{/if}

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
