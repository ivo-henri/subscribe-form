<script>
  import { scale } from "svelte/transition";
  import { quintOut } from "svelte/easing";
  import { onMount } from "svelte";

  let ready = false;
  onMount(() => (ready = true));

  const topText = [
    {
      id: 2,
      txt: "Today, its scientifically proven fact that approximately 90% of people do not know ANY other way of earning income than GOING TO WORK…",
    },
    {
      id: 3,
      txt: "Approximately 80% of ALL these people are absolutely not satisfied with their work, nor are they happy…",
    }
  ];

  const bottomText = [
    {
      id: 100,
      txt: "TODAY, we’re going to speak about:",
    },
    {
      id: 200,
      txt: "✔️ HOW We’ve Earned Big Amounts Of Extra Money",
    },
    {
      id: 300,
      txt: "✔️ Our Step-by-Step Plan How To Buy Real Estate In Europe or Bali",
    },
    {
      id: 400, txt: "✔️ How You Can Do The Same!"
    },
    {
      id: 500,
      txt: "WE WILL SEND YOU THE LINK TO THE WEBINAR! ❌",
    }
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
          <h2
              class="heading-section"
              transition:scale={{
                delay: text.id,
                duration: 500,
                easing: quintOut,
              }}
            >
              <h1 class="main-header">
                 ❌ HARSH REALITY…
              </h1>
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
                  <h3 class="mb-4">Please, enter your…</h3>
                  <div id="form-message-warning" class="mb-4" />
                  {#if state === "sent"}
                    <div id="form-message-success" class="mb-4" in:scale>
                      Done! Check your email inbox soon! If the email isn't there in 2-3min then please check also the spambox and click "Not spam"!
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
                            placeholder="Name"
                          />
                        </div>
                      </div>
                      <div class="form-text">and</div>
                      <div class="col-md-12">
                        <div class="form-group">
                          <input
                            type="email"
                            class="form-control"
                            value={email}
                            on:input={(event) => (email = event.target.value)}
                            placeholder="Email"
                          />
                        </div>
                      </div>
                      <div class="form-text">I'll send you the video URL.</div>
                      <div class="col-md-12">
                        <div class="form-group">
                          <input
                            type="submit"
                            value="SEND!"
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
  .left {
    margin-left: 3.5em;
  }
  .main-header {
    size: 4em;
  }
</style>
