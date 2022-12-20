<template>
  <q-page>
    <div class="q-py-lg q-px-md row items-end q-col-gutter-md">
      <div class="col">
        <q-input
          class="new-qweet"
          bottom-slots
          v-model="newQweetContent"
          placeholder="What's happening?"
          counter
          maxlength="280"
          autogrow
        >
          <template v-slot:before>
            <q-avatar size="xl">
              <img src="https://cdn.quasar.dev/img/avatar5.jpg" />
            </q-avatar>
          </template>
        </q-input>
      </div>
      <div class="col col-shrink">
        <q-btn
          class="q-mb-lg"
          unelevated
          rounded
          color="primary"
          label="Qweet"
          no-caps
          :disable="!newQweetContent"
        />
      </div>
    </div>
    <q-separator class="divider" size="10px" color="grey-2" />
    <!-- tweet list -->
    <q-list>
      <q-item>
        <q-item-section avatar top>
          <q-avatar size="xl">
            <img src="https://cdn.quasar.dev/img/avatar5.jpg" />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-subtitle1">
            <strong> Frank Assafuah </strong>
            <span class="text-grey-7">@frank_assafuah</span>
          </q-item-label>
          <q-item-label class="qweet-content text-body1">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vero
            praesentium est commodi consequuntur dignissimos iure aliquid
            nesciunt repellat perferendis veniam recusandae, nulla perspiciatis.
            Ducimus consectetur rerum iste expedita laborum. Unde? Lorem ipsum
            dolor sit amet consectetur adipisicing elit. Cupiditate,alias! Quas
            laudantium exercitationem molestias? Blanditiis aut ab ratione quae
            dignissimos!
          </q-item-label>
          <div class="qweet-icons row justify-between q-mt-sm">
            <q-btn color="grey" size="sm" icon="far fa-comment" flat round>
            </q-btn>
            <q-btn color="grey" size="sm" icon="fas fa-retweet" flat round>
            </q-btn>
            <q-btn color="grey" size="sm" icon="far fa-heart" flat round>
            </q-btn>
            <q-btn color="grey" size="sm" icon="fas fa-trash" flat round>
            </q-btn>
          </div>
        </q-item-section>

        <q-item-section side top> 1 min ago </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
import { ref } from "vue";

export default {
  name: "PageHome",
  setup() {
    const newQweetContent = ref("");

    return {
      newQweetContent,
    };
  },
};
</script>
<style lang="scss" scoped>
.new-qweet {
  text-area {
    font-size: 19px;
    line-height: 1.4 !important;
  }
}
.divider {
  border-top: 1px solid $grey-4;
  border-bottom: 1px solid $grey-4;
}

.qweet-content {
  white-space: pre-line;
}

.qweet-icons {
  margin-left: -5px;
}
</style>
