<template>
  <div class="container">
    <div class="banner">
      <h2></h2>
    </div>
    <div class="py-32 space-y-6 text-center flex flex-col items-center max-w-4xl mx-auto">
      <h2 v-if="!connectedAccountId">Get ready for take off</h2>
      <p v-if="!connectedAccountId">Merchello is the world's leading air travel platform: join our team of pilots to help people travel faster.</p>
      <h2 v-if="connectedAccountId">Add information to start accepting money</h2>
      <p v-if="connectedAccountId">Merchello partners with Stripe to help you receive payments while keeping your personal and bank details secure.</p>
      <div v-if="!accountCreatePending && !connectedAccountId">
        <button class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-2.5 px-3.5 py-2.5 shadow-sm text-white dark:text-gray-900 bg-gray-900 hover:bg-gray-800 disabled:bg-gray-900 dark:bg-white dark:hover:bg-gray-100 dark:disabled:bg-white focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 w-full flex justify-center items-center" @click="createAccount">Sign up</button>
      </div>
      <div v-if="connectedAccountId && !accountLinkCreatePending && !connectedAccountUpdated">
        <button @click="createAccountLink">Add information</button>
      </div>
      <p v-if="error" class="error">Something went wrong!</p>
      <div v-if="connectedAccountId || accountCreatePending || accountLinkCreatePending" class="dev-callout">
        <p v-if="connectedAccountId">Your connected account ID is: <code class="bold">{{ connectedAccountId }}</code></p>
        <p v-if="accountCreatePending">Creating a connected account...</p>
        <p v-if="accountLinkCreatePending">Creating a new Account Link...</p>
      </div>
      <div class="info-callout">
        <p>
          This is a sample app for Stripe-hosted Connect onboarding. <a href="https://docs.stripe.com/connect/onboarding/quickstart?connect-onboarding-surface=hosted" target="_blank" rel="noopener noreferrer">View docs</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script>

</script>
