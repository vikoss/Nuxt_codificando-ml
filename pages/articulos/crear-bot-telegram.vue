<template>
  <main class="text-base text-slate container mx-auto">
    <div class="m-5">
      <i class="italic">20 de Julio de 2021</i>
      <h1 class="text-2xl font-bold my-1">{{ blog.title }}</h1>
      <h2>{{ blog.description }}</h2>
    </div>
    <div>
      <figure>
        <img
          src="~/assets/articles/crear-bot-telegram/telegram.jpg"
          :alt="blog.title"
          class="w-full"
        />
      </figure>
    </div>
    <div class="m-5">
      <h3 class="text-2xl font-bold mb-8 mt-7">Pasos a seguir:</h3>
      <ol class="list-disc ml-5">
        <li>Pensar en un nombre para tu bot</li>
        <li>
          Crear nuestro bot y obtener el
          <i class="opacity-70">authorization token</i>
        </li>
        <li>
          Crear un grupo de
          <a
            href="https://telegram.org/"
            target="_blank"
            class="underline text-pink"
            >Telegram</a
          >
        </li>
        <li>Enviar mensajes al grupo con nuestro bot</li>
        <li>Automatizando el envio de mensajes con nuestro bot</li>
      </ol>
      <h3 class="text-2xl font-bold mb-8 mt-7">Requisitos:</h3>
      <ul class="list-disc ml-5">
        <li>15 minutos de tu tiempo</li>
        <li>
          Tener instalado
          <a
            href="https://telegram.org/"
            target="_blank"
            class="underline text-pink"
            >Telegram</a
          >
          en cualquiera de sus versiones:
          <a
            href="https://desktop.telegram.org/"
            target="_blank"
            class="underline text-pink"
            >Desktop</a
          >,
          <a
            href="https://play.google.com/store/apps/details?id=org.telegram.messenger&hl=es_MX&gl=US"
            target="_blank"
            class="underline text-pink"
            rel="noopener noreferrer"
            >Android</a
          >,
          <a
            href="https://apps.apple.com/es/app/telegram-messenger/id686449807"
            target="_blank"
            class="underline text-pink"
            rel="noopener noreferrer"
            >iPhone y iPad,</a
          >
        </li>
        <li>
          Nociones basicas de
          <a
            href="https://www.postman.com/"
            target="_blank"
            class="text-blue-500"
            rel="noopener noreferrer"
            >Postman</a
          >
        </li>
        <li>Ganas de aprender <strong class="text-2xl">🤓️</strong></li>
      </ul>
      <h2 id="create-bot" class="text-2xl font-bold mb-8 mt-7">
        Pensar un nombre para nuestro bot
      </h2>
      <h2>
        Existen algunas reglas que debemos considerar al elegir el nombre para
        nuestro bot, la primera regla es que no exista pero mas adelante lo
        verificaremos y la segunda es que el nombre termine en
        <i class="opacity-80">bot</i> por ejemplo:
        <i class="opacity-80">VikossBot</i> o
        <i class="opacity-80">vikoss_bot</i>.
      </h2>
      <h2 id="create-bot" class="text-2xl font-bold mb-8 mt-7">
        Crear nuestro bot en telegram
      </h2>
      <p>
        Lo primero que tendremos que hacer es hablar con BotFather asi que los
        presento:
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <h2 class="mb-4">
        BotFather es el bot que gobierna a todos. Entonces le pediremos que nos
        ayude a crear un nuevo bot y que nos genere nuestro
        <i class="opacity-80">authorization token</i>.
      </h2>
      <h2 class="mb-4">
        Puedes abrir telegram y buscar a BotFather o puedes dar click
        <a
          href="https://t.me/BotFather"
          target="_blank"
          class="text-pink underline"
          rel="noopener noreferrer"
          >aqui</a
        >
        para ir directo al chat con el.
      </h2>
      <p>
        Es hora de conversar con BotFather nosotros le enviaremos el primer
        mensaje
        <code class="bg-slate text-slate-light py-px px-1 select-all"
          >/start</code
        >
        .
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-start-bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <h2>
        Ahora le diremos que necesitamos crear un nuevo bot
        <code class="bg-slate text-slate-light py-px px-1 select-all"
          >/newbot</code
        >
      </h2>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-new-bot-bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <h2 class="mt-4">
        Es hora de mandar el nombre de nuestro bot y BotFather revisara que sea
        un nombre valido.
      </h2>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-done-bot.jpeg"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <p>
        Felicidades en este punto ya tienes listo tu bot entonces puedes ir a
        buscarlo en telegram y personalizarlo ya sea agregando una descripcion,
        foto de perfil etc. Y es importante que guardes y no compartas tu
        <i class="opacity-80">authorization token</i>.
      </p>
      <h2 id="create-bot" class="text-2xl font-bold mb-8 mt-7">
        Crear un grupo de telegram
      </h2>
      <h2>
        Vamos a crear un grupo comun y corriente en telegram en el cual
        posteriormente agregaremos a nuestro bot quien mandara mensajes de
        acuerdo a nuestra conveniencia y por supuesto que cualquier otra
        persona.
      </h2>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-done-bot.jpeg"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <h2 class="mt-4">
        Como comentamos antes podemos personalizar en este caso el grupo
        agregando descripcion, algunas fotos, etc
      </h2>
      <h2 id="create-bot" class="text-2xl font-bold mb-8 mt-7">
        Enviar mensajes al grupo con nuestro bot
      </h2>
      <h2 class="mt-4">
        Primero para que alguien pueda mandar mensajes al grupo pues debe estar
        en el grupo 😁. Entonces agregaremos al grupo a nuestro bot, buscamos la
        opcion de agregar miembros y buscamos a nuestro bot por el nombre que le
        dimos comenzando por un <i class="opacity-80">@</i> por ejemplo:
        <i class="opacity-80">@VikossBot</i>.
      </h2>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-done-bot.jpeg"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <h2 class="mt-4">
        Debemos pensar que es un simple grupo de telegram con usuarios normales
        (humanos) y nuestro bot quien sera el que este enviando mensajes
      </h2>
      <p>Utilizaremos la API de Telegram y Postman para poder continuar.</p>
      <h2>
        Todas las solicitudes a la API de Telegram llevan esta estructura:
        <code class="bg-slate text-slate-light py-px px-1 select-all"
          >https://api.telegram.org/bot{token}/METHOD_NAME</code
        >
        donde tendremos que remplazar {token} por nuestro
        <i class="text-gray-700">authorization token</i>
      </h2>
      <h2>
        Realizaremos una peticion tipo GET con nuestro
        <i class="opacity-80">authorization token</i> con el fin de encontart el
        <i class="opacity-80">chat_id</i> de el grupo que hicimos para indicarle
        a nuestro bot que es a ese grupo al que tiene que enviar los mensajes
      </h2>

      <p>
        La solicitud que tenemos que hacer en esta ocacion sera de tipo GET y el
        url sera el siguiente:
        <code class="bg-slate text-slate-light py-px px-1 select-all"
          >https://api.telegram.org/bot{token}/getUpdates</code
        >
        y no se te olvide cambiar el {token} por tu
        <i class="text-gray-700">authorization token</i>
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/postman-get-updates.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <img
        src="~/assets/articles/crear-bot-telegram/result-get-updates.jpeg"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <h2>
        Si en el resultado no encuentras el
        <i class="opacity-80">chat_id</i> entonces debes ir al grupo desde
        Telegram para remover y volver agregar al bot al grupo.
      </h2>
      <h2>el valor que estamos buscando es el <i class="opacity-80">id</i></h2>
      <p>
        una vez que encontremos el <i class="opacity-80">chat_id</i> podremos
        continuar con la siguiente solicitud a la API de telegram Esta vez es de
        tipo POST con la siguiente estructura
        <code class="bg-slate text-slate-light py-px px-1 select-all"
          >https://api.telegram.org/bot{token}/sendMessage</code
        >
        Dentro de Postman en la seccion de body seleccionamos
        <i class="opacity-80">raw</i> y tipo <i class="opacity-80">JSON</i> y
        para el payload agregaremos dos valores: el
        <i class="opacity-80">mensaje</i> que se quiere enviar y el
        <i class="opacity-80">chat_id</i> al que se enviara
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/send-message-from-postman.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <p>
        Si seguiste todos los pasos entonces tendras tu primer mensaje de
        nuestro bot.
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/first-message-bot-from-postman.jpeg"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <p><strong>Vualá!</strong> Tu bot ya envia mensajes al grupo.</p>

      <h2 id="create-bot" class="text-2xl font-bold mb-8 mt-7">
        Automatizando el envio de mensajes con la API de Telegram
      </h2>
      <p>
        Para lograr automatizar el proceso tendriamos que estar ocupando
        cualquier lenguaje de programacion que soporte solicitudes con el
        protocolo HTTP que hoy en dia casi cualquiera por poner algunos
        ejemplos: PHP, Javascript, Python, Java etc.
      </p>
      <p>Dejare un ejemplo(Codigo 😉) de la integracion con Javascript</p>
      <img
        src="~/assets/articles/crear-bot-telegram/code-for-send-message.jpeg"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
    </div>
  </main>
</template>

<script>
import Blogs from '~/articles'

export default {
  components: {},
  computed: {
    blog() {
      return Blogs.find((blog) => blog.slug === 'crear-bot-telegram')
    },
  },
}
</script>
