<script>
  export let toastDetails;
</script>

{#if toastDetails.show}
  <div class=" fixed  bottom-5 right-5 animate-fade">
    <div
      role="alert"
      class="rounded border-l-4 {toastDetails.type === 'error'
        ? 'border-red-500 bg-red-50 '
        : 'border-green-500 bg-green-50 '} p-4"
    >
      <strong
        class="block font-medium {toastDetails.type === 'error'
          ? 'text-red-500 '
          : 'text-green-700'}"
      >
        {toastDetails.type === "error" ? "Error" : "Congratulations"}
      </strong>

      <p
        class="mt-2 text-sm max-w-sm {toastDetails.type === 'error'
          ? 'text-red-500 '
          : 'text-green-700'}"
      >
        {toastDetails.msg}
      </p>
    </div>
  </div>
{/if}

<style>
  @keyframes fade {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
  .animate-fade {
    animation: fade 0.7s forwards;
  }
</style>
