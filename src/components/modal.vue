
 <template>
  <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">

          <div class="modal-header">
            <slot name="header">
              default header
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              default body
            </slot>
          </div>    

          <div class="modal-footer">
            <slot name="footer">
              <button class="btn btn-primary modal-default-button" @click="$emit('close')">
                OK
              </button>
            </slot>
          </div>
        </div>
      </div>
    </div>
 </template>
 <script>
 export default {
  name:'modal',
  data: function() {
    return { show: false };
  },
  methods: {
    open: function() {
      this.show = true;
    },
    close: function() {
      this.show = false;
    }
  }
 }
  </script>