<script>
  export let segment

  let navbarVisible = false
  let y
  let socialNetworks = [
    {name: 'Facebook', icon: 'fab fa-facebook', url: 'https://www.facebook.com/KelvinHelmut'},
    {name: 'Twitter', icon: 'fab fa-twitter', url: 'https://twitter.com/KelvinHelmut'},
    {name: 'Github', icon: 'fab fa-github', url: 'https://github.com/KelvinHelmut/'},
  ]
  let cellphone = '+51 954 733 536'

  function toggleNavbar() {
	  navbarVisible = !navbarVisible
  }
</script>

<style>
</style>

<!-- <nav>
	<ul>
		<li><a aria-current='{segment === undefined ? "page" : undefined}' href='.'>home</a></li>
		<li><a aria-current='{segment === "about" ? "page" : undefined}' href='about'>about us</a></li>

		<li><a rel=prefetch aria-current='{segment === "blog" ? "page" : undefined}' href='blog'>blog</a></li>
	</ul>
</nav> -->

<svelte:window bind:scrollY={ y }/>

<nav
  class="{ y < 50 ? 'absolute' : 'fixed bg-white shadow-md'} top-0 z-50 w-full flex flex-wrap items-center justify-between
  px-2 py-3 navbar-expand-lg">
  <div
    class="container px-4 mx-auto flex flex-wrap items-center justify-between">
    <div
      class="w-full relative flex justify-between lg:w-auto lg:static lg:block
      lg:justify-start">
      <a
        class="text-sm font-bold leading-relaxed inline-block mr-4 py-2
        whitespace-no-wrap uppercase text-white"
        href=".">
        <span class="text-lg">
          <span class="text-yellow-600">{ ' { ' }</span><span class="text-red-600">Dev</span><span class="text-green-500">it</span><span class="text-blue-600">ai</span><span class="text-yellow-600">{ ' } ' }</span>
        </span>
      </a>
      <button
        class="cursor-pointer text-xl leading-none px-3 py-1 border border-solid
        border-transparent rounded bg-transparent block lg:hidden outline-none
        focus:outline-none"
        type="button"
        on:click={ toggleNavbar }>
        <i class="text-gray-800 fas fa-bars" />
      </button>
    </div>
    <div class="lg:flex flex-grow items-center bg-white lg:bg-transparent lg:shadow-none { navbarVisible ? '' : 'hidden' }">
      <!-- <ul class="flex flex-col lg:flex-row list-none mr-auto">
        <li class="flex items-center">
          <a
            class="lg:text-white lg:hover:text-gray-300 text-gray-800 px-3 py-4
            lg:py-2 flex items-center text-xs uppercase font-bold"
            href="https://www.creative-tim.com/learning-lab/tailwind-starter-kit#/landing">
            <i
              class="lg:text-gray-300 text-gray-500 far fa-file-alt text-lg
              leading-lg mr-2" />
            Docs
          </a>
        </li>
      </ul> -->
      <ul class="flex flex-col lg:flex-row list-none lg:ml-auto">
      {#each socialNetworks as socialNetwork }
        <li class="flex items-center">
          <a aria-label={ socialNetwork.name }
            class="lg:text-white lg:hover:text-gray-300 text-gray-800 px-3 py-4
            lg:py-2 flex items-center text-xs uppercase font-bold"
            target="_blank" rel="noopener noreferrer"
            href={ socialNetwork.url }>
            <i class="{ socialNetwork.icon } lg:text-gray-800 text-gray-500 text-lg leading-lg " />
            <span class="lg:hidden inline-block ml-2">{ socialNetwork.name }</span>
          </a>
        </li>
      {/each}
      </ul>
      <ul class="flex flex-col lg:flex-row list-none">
        <li class="flex items-center">
          <a
            class="bg-green-700 text-white text-xs font-semibold
            uppercase px-4 py-2 rounded shadow hover:shadow-md outline-none
            focus:outline-none lg:mr-1 lg:mb-0 ml-3 mb-3"
            type="button"
			      href="https://wa.me/{ cellphone.match(/[0-9]*/g).join('') }"
			      target="_blank" rel="noopener noreferrer"
            style="transition: all 0.15s ease 0s;">
            <i class="text-md fab fa-whatsapp mr-1" />
            { cellphone }
          </a>
        </li>
      </ul>
    </div>
  </div>
</nav>