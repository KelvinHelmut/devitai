<script>
    let currentYear = new Date().getFullYear()
    let links = [
      // {text: 'Sobre nosotros', url: '/about'},
      {text: 'Blog', url: '/blog'},
      {text: 'Productos gratuitos', url: '/products/free'},
    ]
    let otherLinks = [
      {text: 'Términos y condiciones', url: '/terms'},
      {text: 'Política de privacidad', url: '/privacy'},
      {text: 'Contáctanos', url: '/contact-us'},
    ]
    let socialNetworks = [
      {name: 'Twitter', icon: 'fab fa-twitter', color: 'text-blue-400', url: 'https://twitter.com/KelvinHelmut'},
      {name: 'Facebook', icon: 'fab fa-facebook-square',  color: 'text-blue-600', url: 'https://www.facebook.com/KelvinHelmut'},
      {name: 'Github', icon: 'fab fa-github',  color: 'text-gray-900', url: 'https://github.com/KelvinHelmut/'},
    ]
</script>

<style>
    .bg-footer {
        background: #2b2b2b;
    }
    .svg-footer {
        color: #2b2b2b;
    }
</style>

<footer class="relative bg-footer pt-8 pb-6">
  <div
    class="bottom-auto top-0 left-0 right-0 w-full absolute pointer-events-none
    overflow-hidden -mt-20"
    style="height: 80px; transform: translateZ(0px);">
    <svg
      class="absolute bottom-0 overflow-hidden"
      xmlns="http://www.w3.org/2000/svg"
      preserveAspectRatio="none"
      version="1.1"
      viewBox="0 0 2560 100"
      x="0"
      y="0">
      <polygon
        class="svg-footer fill-current"
        points="2560 0 2560 100 0 100" />
    </svg>
  </div>
  <div class="container mx-auto px-4">
    <div class="flex flex-wrap">
      <div class="w-full lg:w-6/12 px-4">
        <h4 class="text-3xl font-semibold text-white">¡Mantengámonos en contacto!</h4>
        <h5 class="text-lg mt-0 mb-2 text-gray-500">
          Encuéntrenos en cualquiera de estas plataformas, respondemos 1-2 días hábiles.
        </h5>
        <div class="mt-6">
        {#each socialNetworks as socialNetwork }
          <button aria-label={ socialNetwork.name }
            class="{ socialNetwork.color } bg-white shadow-lg font-normal h-10 w-10
            items-center justify-center align-center rounded-full outline-none
            focus:outline-none mr-2"
            on:click={ () => window.open(socialNetwork.url, '_blank') }>
            <i class={ socialNetwork.icon } />
          </button>
        {/each}
        </div>
      </div>
      <div class="w-full lg:w-6/12 px-4">
        <div class="flex flex-wrap items-top mb-6">
          <div class="w-full lg:w-4/12 px-4 ml-auto">
            <span
              class="block uppercase text-gray-600 text-sm font-semibold mb-2">
              Enlaces Útiles
            </span>
            <ul class="list-unstyled">
            {#each links as link }
              <li>
                <a
                  class="text-gray-500 hover:text-gray-100 font-semibold block
                  pb-2 text-sm"
                  href={ link.url }>
                  { link.text }
                </a>
              </li>
            {/each}
            </ul>
          </div>
          <div class="w-full lg:w-4/12 px-4">
            <span
              class="block uppercase text-gray-600 text-sm font-semibold mb-2">
              Otros Recursos
            </span>
            <ul class="list-unstyled">
            {#each otherLinks as link }
              <li>
                <a
                  class="text-gray-500 hover:text-gray-100 font-semibold block
                  pb-2 text-sm"
                  href={ link.url }>
                  { link.text }
                </a>
              </li>
            {/each}
            </ul>
          </div>
        </div>
      </div>
    </div>
    <hr class="my-6 border-gray-800" />
    <div class="flex flex-wrap items-center md:justify-between justify-center">
      <div class="w-full md:w-4/12 px-4 mx-auto text-center">
        <div class="text-xs text-gray-600 font-semibold py-1">
          Copyright © { currentYear }
          <a
            href="."
            class="hover:text-gray-100">
            Devitai
          </a>
        </div>
      </div>
    </div>
  </div>
</footer>
