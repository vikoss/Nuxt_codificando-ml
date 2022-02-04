<template>
  <main class="text-base container mx-auto">
    <div class="m-5">
      <i class="text-gray-700">20 de Julio de 2021</i>
      <subtitle class="my-1" :label="blog.title" />
      <paragraph :label="blog.description" />
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
      <ol class="list-decimal ml-5">
        <li>
          Obtener nuestro <i class="text-gray-700">authorization token</i>.
        </li>
        <li>Ver que podemos hacer con nuestro bot.</li>
        <li>Enviar mensajes con nuestro bot.</li>
        <li>
          Integrar con
          <a href="https://laravel.com/" target="_blank" class="text-blue-500"
            >Laravel</a
          >.
        </li>
      </ol>
      <h3 class="text-2xl font-bold mb-8 mt-7">Requisitos:</h3>
      <ul class="list-disc ml-5">
        <li>
          Tener instalado
          <a href="https://telegram.org/" target="_blank" class="text-blue-500"
            >Telegram</a
          >
          en cualquiera de sus versiones:

          <ul class="list-disc ml-5">
            <li>
              <a
                href="https://desktop.telegram.org/"
                target="_blank"
                class="text-blue-500"
                >Desktop Apps</a
              >
            </li>
            <li>
              <a
                href="https://apps.apple.com/es/app/telegram-messenger/id686449807"
                target="_blank"
                class="text-blue-500"
                rel="noopener noreferrer"
                >iPhone y iPad</a
              >
            </li>
            <li>
              <a
                href="https://play.google.com/store/apps/details?id=org.telegram.messenger&hl=es_MX&gl=US"
                target="_blank"
                class="text-blue-500"
                rel="noopener noreferrer"
                >Android</a
              >
            </li>
          </ul>
        </li>
        <li>
          Conocimientos basicos de envio de solicitudes con el metodo
          <a
            href="https://developer.mozilla.org/es/docs/Web/HTTP"
            target="_blank"
            class="text-blue-500"
            rel="noopener noreferrer"
            >HTTP</a
          >
          (usaremos
          <a
            href="https://www.postman.com/"
            target="_blank"
            class="text-blue-500"
            rel="noopener noreferrer"
            >Postman</a
          >).
        </li>
        <li>
          Conceptos basicos de algun lenguaje de programacion de Back-End (para
          la integracion del SDK de la API de Telegram Bot).
        </li>
        <li>Ganas de aprender <strong class="text-2xl">🤓️</strong></li>
      </ul>
      <h2 class="text-2xl font-bold mb-8 mt-7">
        Obtener nuestro <i class="text-gray-700">authorization token</i>
      </h2>
      <p>
        Lo primero que tenemos que hacer es hablar con BotFather y antes que
        nada te lo presento:
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <p>
        le diremos que necesitamos un bot y tambien que nos ayude a generarnos
        nuestro <i class="text-gray-700">authorization token</i> puedes abrir
        telegram y buscar a BotFather o puedes dar click
        <a
          href="https://t.me/BotFather"
          target="_blank"
          class="text-blue-500"
          rel="noopener noreferrer"
          >aqui</a
        >
        para ir directo
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-found-bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <p>
        es hora de inciar a conversar con el BotFather asi que nosotros tendrmos
        que enviarle el primer mensaje
        <code class="bg-gray-700 text-gray-200 py-px px-1">/start</code> de
        inmedianto nos contestara poniendose a nuestra disposicion
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-start-bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      ahora le diremos que necesitamos crear un nuevo bot
      <code class="bg-gray-700 text-gray-200 py-px px-1">/newbot</code>
      <img
        src="~/assets/articles/crear-bot-telegram/chat-new-bot-bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      bien ahora nos pide que eligamos un nombre de usuario para nuestro bot y
      que debe terminar en `bot` por ejemplo: CodificandoBot o codificando_bot.
      <img
        src="~/assets/articles/crear-bot-telegram/chat-new-bot-bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      en cuanto te decidas por tu nombre de usuario para tu bot hacelo saber a
      BotFather
      <img
        src="~/assets/articles/crear-bot-telegram/chat-done-bot-father.png"
        alt="El BotFather"
        class="my-8 w-full"
      />
      <p>
        felicidades en este punto tu bot ya esta listo puedes ir a buscarlo en
        telegram y personalizarlo agregando una descripcion o foto de perfil
        tambien es importante que guardes y no compartas tu
        <i class="text-gray-700">authorization token</i>
        que te genero BotFather
      </p>
      <h2 class="text-2xl font-bold mb-8 mt-7">
        Ver que podemos enseñarle hacer a nuestro bot
      </h2>
      <p>
        Adicionalmente podemos continuar hablando con BotFather para decirle que
        nos cambie el nombre de nuestro bot
        <code class="bg-gray-700 text-gray-200 py-px px-1">/setname</code> ,
        agregarle una descripcion
        <code class="bg-gray-700 text-gray-200 py-px px-1"
          >/setdescription</code
        >
        etc.
      </p>
      <p>
        Tenemos una infinidad de cosas que podemos hacer con un bot por
        mencionar algunas:
      </p>
      <ul class="list-disc ml-5">
        <li>Recibir notificaciones o alguna noticia personalizada</li>
        <li>Aceptar pagos de los usuarios de Telegram</li>
        <li>Recibir alertas de cualquier tipo</li>
      </ul>
      <h2 class="text-2xl font-bold mb-8 mt-7">
        Enviando mensajes a nuestro bot
      </h2>
      <p>
        Es hora de ver el poder de los bots en accion en esta ocacion
        utilizaremos nuestro bot para mandar logs de algun sistema que tengamos
        a un grupo en telegram El siguiente paso sera crear un grupo en el cual
        estaran todas las personas que les sea relevante ver estos logs Abrimos
        telegram y damos click en agregar nuevo grupo y asignamos el nombre de
        nuestro grupo en este caso sera Codificando Group
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/new-group.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      Despues tenemos que agregar un miembro especial a nuestro grupo y si
      adivinaste es nuestro bot aqui debes pensar que es un simple grupo de
      telegram con usuarios normales(humanos) y nuestro bot quien sera el que
      este enviando esos logs Damos en agregar miembros y buscamos a nuestro bot
      por ejemplo @CodificandoBot
      <img
        src="~/assets/articles/crear-bot-telegram/add-members.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      Por el momento solo estaran tu y el bot en el grupo entonces le damos en
      agregar.
      <img
        src="~/assets/articles/crear-bot-telegram/added-bot-to-group.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      Nos dirigimos al grupo y enviamos nuestro primer mensaje esto con el fin
      de que lleguen actualizaciones a la API de telegram
      <img
        src="~/assets/articles/crear-bot-telegram/first-message-to-group.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />

      <p>
        Es hora de utilizar Postman con el objetivo de encontart el chat_id de
        el grupo que hicimos para indicarle a nuestro bot que es a ese grupo al
        que tiene que enviar los logs que le indiquemos
      </p>
      <p>
        Todas las solicitudes a la API de Telegram deben ser HTTPS y seran de
        esta forma:
        <code class="bg-gray-700 text-gray-200 py-px px-1"
          >https://api.telegram.org/bot{token}/METHOD_NAME</code
        >
        donde tendremos que remplazar {token} por nuestro
        <i class="text-gray-700">authorization token</i>
        que obtuvimos en los pasos anteriores por ejemplo:
        <code class="bg-gray-700 text-gray-200 py-px px-1"
          >https://api.telegram.org/bot123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11/getMe</code
        >
      </p>
      <p>
        La solicitud que tenemos que hacer en esta ocacion sera de tipo GET y el
        url sera el siguiente:
        <code class="bg-gray-700 text-gray-200 py-px px-1"
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
      <p>La respuesta sera en formato JSON asi como la siguiente:</p>
      <img
        src="~/assets/articles/crear-bot-telegram/result-get-updates.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      el valor que estamos buscando es el que tiene el `id` y que empieza con un
      `-`
      <p>
        una vez que encontremos el chat_id podremos continuar con la siguiente
        solicitud a la API de telegram bot que es la que le indica a nuestro bot
        que envie el mensaje al grupo entonces creamos una nueva solicitud esta
        vez sera de tipo POST y el url sera
        <code class="bg-gray-700 text-gray-200 py-px px-1"
          >https://api.telegram.org/bot{token}/sendMessage</code
        >
        y en la seccion de body seleccionamos raw y de tipo JSON agregamos el
        body el cual llerava dos valores el mensaje que se quiere enviar y el
        chat_id al que se enviara
      </p>
      <p>recuerda cambiar el chat_id por el tuyo</p>
      <img
        src="~/assets/articles/crear-bot-telegram/send-message-from-postman.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <p>
        Si as seguido todos los pasos y as realizado todo al pie de la letra
        entonces tendras tu primer mensaje de nuestro bot
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/first-message-bot-from-postman.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <p>
        <strong>Vualá!</strong> Tu bot ya envia mensajes al grupo ya realizaste
        lo mas laborioso.
        <br />
        Si no tienes mucha ezperiencia o no entiendes que pasos serian los
        sigueintes ya que podrias pensar que no es practico ni efectivo estar
        abiendo postman cada vez que necesites que tu bot envie un mensja al
        chat para registar algun log o simplemente algun tipo de alarma entonces
        continua con el siguiente capitulo que llevare acabo la conexion de
        nuestro bot con algun sistema que tengas ya sea una Landing Page,
        tienda, plataforma de streaming o cualquier tipo de back-end y con
        cualquier lenguaje de programacion que soporte solicitudes con el
        protocolo HTTP.
      </p>
      <h2 class="text-2xl font-bold mb-8 mt-7">
        Conectando nuestro bot con Laravel
      </h2>
      <p>
        Para este caso tomaremos como ejemplo un sistema de registro de recargas
        de gasolina en el cual se requiere que cada vez que algun coche realize
        una recarga de gasolina llegue una notificacion. Para resolver esta
        situacion podriamos enviar un email o sms a quien se esta requiriendo
        que le llegaran las notificaciones pero no es muy eficaz estar abiendo
        un email o sms por cada notificacion ademas de el costo que este implica
        entonces es aqui donde podemos resolver esta situacion con un bot.
        <br />
        <strong>El flujo sera el siguiente:</strong>
      </p>
      <ul class="list-decimal ml-5">
        <li>
          El coche llega al establecimiento y realiza una recarga de gasolina.
        </li>
        <li>
          La aplicacion(Front-End) se comunica con el sistema(Back-End) para que
          guarde la recarga.
        </li>
        <li>El sistema(Back-End) realiza el registro en la base de datos.</li>
        <li>Utiliza la API de Telegram Bot para enviar el mensaje.</li>
        <li>El mensaje llega a nuesto grupo de Telegram.</li>
        <li>Nuestro Jefe es feliz vigilando las recargas que se hacen.</li>
      </ul>
      <p>
        Aqui te dejo la<a
          href="https://core.telegram.org/bots/samples"
          target="_blank"
          class="text-blue-500"
          rel="noopener noreferrer"
        >
          documentacion </a
        >para que veas los ejemplos y puedas seguirlos incluso si no realizaras
        la integracion con
        <a href="https://laravel.com/" target="_blank" class="text-blue-500"
          >Laravel</a
        >
        ya que encontraras ejemplos tambien para <strong>NodeJs</strong>,
        <strong>Python</strong>, <strong>Rush</strong>, <strong>Ruby</strong>,
        <strong>Go</strong>, etc.
        <br />
        Te dejo una probadita de como quedaria implementado dentro de tu
        controlador de Laravel
      </p>
      <img
        src="~/assets/articles/crear-bot-telegram/controller.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <p>
        Sii, asi de bello ️<strong class="text-2xl">😍</strong>
        <br />
        Cuando registren la recarga de gasolina desde la app de inmediento
        llegara el mensaje al grupo
      </p>

      <img
        src="~/assets/articles/crear-bot-telegram/first-message-from-laravel.png"
        alt="Chat con BotFather, felicidades tu bot ah sido creado."
        class="my-8 w-full"
      />
      <p>
        Listo para ir a produccion<strong class="text-2xl">👌🏽</strong> no es
        cierto jaja primero tiene que pasar por QA.
        <br />
        <br />
        Eso ah sido todo espero de corazon que les guste, les sirva y lo
        implementen hasta la proxima <strong class="text-2xl">👋🏽</strong>.
      </p>
    </div>
  </main>
</template>

<script>
import Subtitle from '~/components/Typography/Subtitle.vue'
import Paragraph from '~/components/Typography/Paragraph.vue'
import Blogs from '~/articles'

export default {
  components: {
    Subtitle,
    Paragraph,
  },
  computed: {
    blog() {
      return Blogs.find((blog) => blog.name === 'crear-bot-telegram')
    },
  },
}
</script>
