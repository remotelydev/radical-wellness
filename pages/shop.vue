<template>
  <main class="min-h-screen flex justify-center items-center p-4">
    <div class="max-w-md">
      <h1>Shop</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus, animi
        rem! Aut est cumque nulla delectus perferendis quidem officiis ad quo!
        Vitae itaque quos corporis, ipsum quis praesentium aut sit.
      </p>
      <form class="mt-4" data-netlify="true">
        <input
          id="email"
          name="email"
          class="p-2 rounded border-2 border-black"
          type="email"
        />
        <button
          class="px-4 py-2 mt-2 bg-black text-white rounded"
          type="submit"
        >
          Pre order
        </button>
        <div data-netlify-recaptcha="true"></div>
      </form>
    </div>
  </main>
</template>
