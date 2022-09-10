<template>
	<div class="backdrop modal1" @click.self="closeModal">
		<div class="modal" :class="{sale: theme === 'sale'}">
         <!-- prop -->
         <!-- <h1>{{ header }}</h1>
         <p>{{ text }}</p>
         <p>{{ theme }}</p> -->

         <!-- slot  -->
         <!-- <slot></slot>
         <div class="action">
            <slot name="links"></slot>
         </div> -->

         <slot></slot>

		</div>
	</div>

</template>

<script>
export default {
   props: ['header', 'text', 'theme'],
   methods: {
      closeModal() {
         this.$emit('close');
      }
   }
}
</script>

<style scope>
   .modal {
      width: 400px;
      padding: 20px;
      margin: 100px auto;
      background: white;
      border-radius: 10px;
   }

   .backdrop {
      top: 0;
      position: fixed;
      background: rgba(0,0,0,0.5);
      width: 100%;
      height: 100%;
   } 

   .modal h1 {
      color: #03cfb4;
      border: none;
      padding: 0;
   }

   .modal.sale {
      background: pink;
   }

   .modal .action {
      text-align: center;
      margin: 30px 0 10px 0;
   }

   .modal .action a {
      color: #333;
      padding: 8px;
      border: 1px solid #aaa;
      border-radius: 4px;
      text-decoration: none;
      margin: 10px;
   }
   
</style>