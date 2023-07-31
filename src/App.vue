<template>
  <div
    id="app"
    class="row d-flex justify-content-center"
  >
    <div class="col-md-6 mt-3">
      <div class="card">
        <div class="card-header">Newsletter</div>
        <div class="card-body">
          <form @submit.prevent="submit">
            <!-- Name -->
            <div class="mb-2">
              <input
                type="text"
                class="form-control"
                placeholder="Name"
                :value="newsletterName"
                @input="
                  newsletterName =
                    $event.target.value
                "
              />
            </div>

            <!-- E-mail -->
            <div class="mb-2">
              <email-input
                v-model:email="newsletterEmail"
              />
              <!-- <email-input
                :modelValue="newsletterEmail"
                @update:modelValue="
                  newsletterEmail = $event
                "
              /> -->
            </div>

            <!-- Emoji -->
            <div class="mb-2">
              <EmojiInput
                v-model="emoji"
                :options="{ position: 'bottom' }"
              />
            </div>
            <button
              type="submit"
              class="btn btn-primary"
            >
              Submit
            </button>
          </form>
        </div>
      </div>
    </div>

    <hr />

    <div class="mt-2 ml-2">
      <button
        type="button"
        class="btn btn-primary"
        @click="open = true"
      >
        Open
      </button>
    </div>
    <!-- <app-modal
      :show="open"
      @hide="open = false"
      :scrollable="true"
    /> -->
    <app-modal
      :show="open"
      @hide="open = false"
    />

    <hr />

    <app-action />

    <hr />
    <p>
      Lorem ipsum dolor sit amet, consectetur
      adipiscing elit. Suspendisse feugiat
      consectetur ipsum, elementum porttitor justo
      volutpat vitae. Integer id pulvinar nibh.
      Aliquam erat volutpat. Pellentesque eget ex
      eu tortor cursus porttitor. Vivamus finibus
      suscipit hendrerit. Etiam nec imperdiet
      diam. Vestibulum fringilla, ex ac vestibulum
      egestas, augue nunc ornare velit, at
      malesuada mauris erat vel felis. Vivamus
      mollis, metus in imperdiet tristique, nisl
      odio accumsan nunc, sit amet scelerisque
      neque diam quis justo. Aenean tincidunt
      vehicula est, ac facilisis dui. Vivamus a
      justo ut odio suscipit aliquet. Morbi
      viverra posuere elementum. Pellentesque
      habitant morbi tristique senectus et netus
      et malesuada fames ac turpis egestas. Proin
      quam ex, porttitor quis libero vel, volutpat
      pulvinar metus.
    </p>
    <p>
      Sed hendrerit quam id sapien maximus
      condimentum. Morbi pretium rhoncus
      porttitor. Proin lacinia placerat nibh, id
      luctus justo sollicitudin in. Nunc eleifend
      vehicula quam et dictum. Aliquam ultrices mi
      at finibus congue. Etiam aliquam mauris id
      nulla rutrum tempus. Donec a pulvinar
      mauris. Phasellus sed est non felis accumsan
      molestie eget eget dolor. Nam facilisis,
      nisi in convallis pellentesque, urna ligula
      eleifend arcu, at eleifend odio purus vitae
      metus. Sed sit amet ipsum eros. Cras varius,
      urna et feugiat egestas, diam ante aliquet
      quam, at malesuada velit enim non ante.
      Integer tempus tortor turpis, ut commodo
      urna egestas in.
    </p>
    <p>
      Vivamus a nulla a elit laoreet convallis.
      Morbi dapibus urna id mi tincidunt, nec
      vulputate justo placerat. Praesent viverra
      risus ut mollis aliquet. Quisque ut velit
      libero. Vivamus pulvinar, mi at lacinia
      eleifend, dui tellus sodales diam, id
      elementum felis enim non ex. Nunc semper
      lectus ut ante rutrum faucibus. Curabitur
      suscipit est egestas ante pharetra lobortis
      ut sed orci.
    </p>
    <p>
      Ut sit amet dui posuere eros aliquet blandit
      in non nunc. Proin vehicula sapien nec erat
      aliquet convallis. Duis in lacus vel mi
      imperdiet sollicitudin. Duis in condimentum
      risus, a cursus nunc. Nullam id sapien
      aliquet, elementum metus in, cursus augue.
      Sed fringilla mauris magna, a sollicitudin
      nisl varius in. Nullam a varius eros, et
      dictum diam. Cras et purus non risus
      consectetur maximus nec sit amet tortor.
      Vestibulum commodo nibh vel nibh cursus
      convallis. Duis eleifend felis eu ipsum
      rhoncus vulputate.
    </p>
    <p>
      Quisque sollicitudin enim nibh, eu fringilla
      enim semper et. Aenean at nulla sed ante
      lacinia convallis. Aenean non malesuada ex.
      Nulla facilisi. Proin accumsan ligula et
      metus dapibus pellentesque. Integer rutrum
      dapibus cursus. Nulla lobortis eros vel eros
      auctor pulvinar. Proin tincidunt luctus
      semper. Aliquam finibus dapibus tellus eu
      maximus. Phasellus convallis eget enim a
      pretium.
    </p>
  </div>

  <!-- <div id="app" class="row d-flex justify-content-center">
    <div class="col-md-5 mt-3">
      <div class="card">
        <div class="card-header">Emoji Selector</div>
        <div class="card-body">
          <form @submit.prevent="submit">
            <div class="mb-3">
              <EmojiInput v-model="emoji" :options="{ position: 'bottom' }" />
            </div>
            <button type="submit" class="btn btn-primary">Submit</button>
          </form>
        </div>
      </div>
    </div>
  </div> -->
</template>

<script>
import EmailInput from '@/components/EmailInput.vue';
import EmojiInput from '@/components/EmojiInput.vue';
import AppModal from '@/components/Modal.vue';
import AppAction from '@/components/Action.vue';

export default {
  name: 'App',
  components: {
    EmailInput,
    EmojiInput,
    AppModal,
    AppAction,
  },
  data() {
    return {
      newsletterName: '',
      newsletterEmail: '',
      emoji: '',
      open: false,
      // open: true,
    };
  },
  methods: {
    submit() {
      console.log('Newsletter Submitted', {
        name: this.newsletterName,
        email: this.newsletterEmail,
      });
      console.log('Emoji: ', this.emoji);
    },
  },
};
</script>

<style
  src="bootstrap/dist/css/bootstrap.css"
></style>
