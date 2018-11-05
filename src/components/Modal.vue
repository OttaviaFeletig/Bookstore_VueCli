<template>
      <div class="modal fade" id="modalBooks" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
            <div class="modal-dialog" role="document">
                <div class="modal-content">
                  <div class="modal-header">
                      <div>
                          <button class="btn" id="moveBack">Back</button>
                          <button class="btn" id="moveForward">Forward</button>
                      </div>
                  </div>
                   
                </div>
            </div>
        </div>
</template>

<script>

export default {
    name: 'modal',
    props: ['modal']
}
</script>

<style>

</style>
