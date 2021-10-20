<template>
  <div class="about">
    <hr />
    <h2>About this Single-Page App</h2>
    <div>This app is design to interact with Websocket-Server (An Akka Http streams based implementation)</div>
    <p>* Use the provided <strong>text-field</strong> to type in your message & press <strong>enter</strong> to disptach it over the Websocket</p>
    <p>* On dispatching <strong>"ping"</strong> as a message, the response is bound to be <strong>"pong"</strong></p>

    <hr />
    <div>
      <p><strong>Following technologies were used:</strong></p>
      <div class="text-center" style="width:100%">
        <!--table class="table" style="width: 453px; height: 108px;"-->
        <table style="border: 1rem;margin-left: auto;margin-right: auto;">
          <thead>
          <tr style="height: 36px;">
          <td style="width: 203px; height: 36px; text-align: center;"><strong>Client-side</strong></td>
          <td style="width: 234px; height: 36px; text-align: center;"><strong>Server-side</strong></td>
          </tr>
          <tr style="height: 18px;">
          <td style="width: 203px; height: 18px;">NodeJS</td>
          <td style="width: 234px; height: 18px;">Java</td>
          </tr>
          <tr>
          <td style="width: 203px;">Vue (version 2) SPA framework</td>
          <td style="width: 234px;">Gradle project</td>
          </tr>
          <tr style="height: 18px;">
          <td style="width: 203px; height: 18px;">Vue CLI</td>
          <td style="width: 234px; height: 18px;">Akka Http Server</td>
          </tr>
          <tr style="height: 18px;">
          <td style="width: 203px; height: 18px;">Vuetify UI</td>
          <td style="width: 234px; height: 18px;">Akka Streams</td>
          </tr>
          <tr style="height: 18px;">
          <td style="width: 203px; height: 18px;">Visual Studio Code</td>
          <td style="width: 234px; height: 18px;">Intellij community edition</td>
          </tr>
          <tr>
          <td style="width: 203px;">&nbsp;</td>
          <td style="width: 234px;">Postman Web-client</td>
          </tr>
          </thead>
        </table>
      </div>
      </div>
  </div>

</template>

<style>
#body {
  text-align: center;
}
</style>