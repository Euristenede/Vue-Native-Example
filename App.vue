<template>
  <app-navigator></app-navigator>
</template>

<script>
import {
  createAppContainer,
  createStackNavigator,
} from "vue-native-router";

import HomeScreen from "./src/HomeScreen.vue";
import SobreScreen from "./src/SobreScreen.vue";
import camera from "./src/camera.vue";
import geolocalizacao from "./src/geolocalizacao.vue";

const StackNavigator = createStackNavigator(
  {
    Home: HomeScreen,
    Sobre: SobreScreen,
    Camera: camera,
    Geo: geolocalizacao
  },
  {
    initialRouteName: 'Geo',
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator },
}
</script>