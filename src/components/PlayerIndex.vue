/* eslint-disable @typescript-eslint/explicit-module-boundary-types */
<template>
  <v-row class="justify-center">
    <v-col cols="7">
      <svg
        xmlns:dc="http://purl.org/dc/elements/1.1/"
        xmlns:cc="http://creativecommons.org/ns#"
        xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
        xmlns:svg="http://www.w3.org/2000/svg"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
        xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
        version="1.1"
        id="Layer_1"
        x="0px"
        y="0px"
        viewBox="0 0 512 512"
        style="enable-background: new 0 0 512 512"
        xml:space="preserve"
        sodipodi:docname="371952.svg"
        inkscape:version="1.0.1 (3bc2e813f5, 2020-09-07)"
      >
        <metadata id="metadata11">
          <rdf:RDF
            ><cc:Work rdf:about=""
              ><dc:format>image/svg+xml</dc:format
              ><dc:type
                rdf:resource="http://purl.org/dc/dcmitype/StillImage" /></cc:Work
          ></rdf:RDF>
        </metadata>
        <defs id="defs9" />
        <sodipodi:namedview
          pagecolor="#ffffff"
          bordercolor="#666666"
          borderopacity="1"
          objecttolerance="10"
          gridtolerance="10"
          guidetolerance="10"
          inkscape:pageopacity="0"
          inkscape:pageshadow="2"
          inkscape:window-width="1920"
          inkscape:window-height="1001"
          id="namedview7"
          showgrid="false"
          inkscape:zoom="1.6210938"
          inkscape:cx="256"
          inkscape:cy="229.68032"
          inkscape:window-x="-9"
          inkscape:window-y="-9"
          inkscape:window-maximized="1"
          inkscape:current-layer="Layer_1"
        />
        <g id="g24">
          <path
            style="fill: black; stroke: #000000; stroke-width: 0.616867"
            d="m 59.836145,227.40441 c -7.451099,-0.3486 -26.828779,-2.1521 -27.519359,-2.56125 -1.020037,-0.60434 29.560547,-87.46091 30.68662,-87.15773 2.578886,0.69433 24.42135,0.7772 30.147814,0.11439 37.04316,-4.28761 70.32934,-27.77986 87.45038,-61.719499 2.31052,-4.580241 5.02231,-10.894545 6.02619,-14.031787 l 1.82522,-5.704075 48.19605,-0.0019 48.19606,-0.0019 -2.72582,7.86506 C 266.04704,110.58037 244.97863,146.89484 219.00778,172.98749 179.7233,212.45621 126.83105,230.53878 59.836145,227.40441 Z"
            id="path15"
          />
          <path
            style="fill: black; stroke: #000000; stroke-width: 0.616867"
            d="m 165.68155,443.27068 c 1.52144,-4.32578 32.55682,-93.0853 68.9675,-197.24337 L 300.85029,56.648996 350.2902,56.491109 c 27.19196,-0.08684 49.43992,-0.0417 49.43992,0.100301 0,0.142003 -29.53501,84.73931 -65.63335,187.99403 -36.09834,103.25472 -67.10992,191.9691 -68.91462,197.14307 l -3.28127,9.40723 h -49.4928 -49.4928 z"
            id="path17"
          />
          <path
            style="fill: black; stroke: #000000; stroke-width: 0.616867"
            d="m 386.5013,454.45834 c -15.25516,-2.75393 -29.96171,-10.30037 -41.25185,-21.16776 -11.67989,-11.24255 -19.05071,-24.00073 -23.0928,-39.97139 -1.55394,-6.13975 -1.68209,-7.58605 -1.68209,-18.98345 0,-11.39739 0.12815,-12.8437 1.68209,-18.98344 6.05655,-23.92998 21.35967,-43.22028 42.86446,-54.03268 18.07974,-9.09031 41.03174,-10.77764 60.00058,-4.41097 27.28164,9.15676 47.81418,32.36237 54.04424,61.08011 1.43277,6.60442 1.61332,24.56418 0.31317,31.1518 -6.63654,33.62609 -32.76172,59.61464 -65.70269,65.35906 -6.80465,1.18664 -20.4883,1.16585 -27.17511,-0.0413 z"
            id="path19"
          />
        </g>
      </svg>
      <v-input class="mt-8">
        <v-text-field
          max-width="30%"
          label="Type a player's name"
          v-model="searchBar"
          @keydown.enter="searchPlayer()"
        ></v-text-field>

        <v-btn
          depressed
          font-color="black"
          style="font-size: 28px"
          plain
          color="lightgray"
          @click="searchPlayer()"
        >
          <p>G</p>
          <img
            class="football"
            src="@/assets/football_PNG28463.png"
            alt="spinning-football"
            height="28px"
            width="28px"
          />
          <p class="onHover">ALLL!</p>
        </v-btn>
      </v-input>
      <v-snackbar v-model="snackbar">
        {{ text }}

        <template v-slot:action="{ attrs }">
          <v-btn color="pink" text v-bind="attrs" @click="snackbar = false">
            Close
          </v-btn>
        </template>
      </v-snackbar>

      <v-card elevation="5" v-if="showCard" width="300px">
        <v-col class="flex-column pa-0">
          <img :src="foundPlayerExtendedProfile.profile.picture" width="100%" />
          <div class="pa-3">
            <p>Name: {{ foundPlayerExtendedProfile.id }}</p>
            <p>Active: {{ foundPlayer.active }}</p>
            <p>Age: {{ foundPlayerExtendedProfile.profile.age }}</p>
            <p>Role: {{ foundPlayerExtendedProfile.profile.role }}</p>
            <p>Team: {{ foundPlayerExtendedProfile.profile.team }}</p>
          </div>
        </v-col>
      </v-card>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import axios, { AxiosResponse } from "axios";

export interface FoundPlayer {
  active: string;
  id: string;
  ["profile-id"]: string;
}

export interface FoundPlayerExtendedProfile {
  id: string;
  profile: {
    age: string;
    picture: string;
    role: string;
    team: string;
  };
  stats: {
    blocks: number;
    totalTackles: number;
    interceptions: number;
    tacklesWon: number;
    yellowCards: number;
    passingAccuracy: number;
    clearances: number;
    totalCrosses: number;
    aerialDuelsWon: number;
    minutesPlayed: number;
    minutesPerGoal: number;
    headedGoals: number;
    foulsConceded: number;
    totalPasses: number;
    totalShots: number;
    otherGoals: number;
    duelsWon: number;
    shotsOnTarget: number;
    leftFootGoals: number;
    rightFootGoals: number;
    starts: number;
    goalsFromInsideBox: number;
    substitutionOff: number;
    foulsWon: number;
    assists: number;
    gamesPlayed: number;
    substitutionOn: number;
    redCards: number;
    goals: number;
    successfulCrosses: number;
    goalsFromOutsideBox: number;
  };
}
@Component
export default class PlayerIndex extends Vue {
  public foundPlayer: FoundPlayer | undefined;
  public foundPlayerExtendedProfile: FoundPlayerExtendedProfile | undefined;
  public searchBar = "";
  public showCard = false;
  public snackbar = false;
  public text = "";

  public async searchPlayer(): Promise<void> {
    this.showCard = false;
    try {
      await axios
        .get(
          "https://web-sandbox.onefootball.com/assignments/player/data/" +
            this.searchBar.toLowerCase() +
            ".json"
        )
        .then((res: AxiosResponse<FoundPlayer>) => {
          this.foundPlayer = res.data;
          this.extendedSearch(this.foundPlayer);
        });
    } catch (error) {
      console.log(error);
      this.text = "Sorry! player not found";
      this.snackbar = true;
    }
  }

  private async extendedSearch(foundPlayer: FoundPlayer): Promise<void> {
    if (foundPlayer.active === "false") {
      //todo ask about types
      this.text = "Player is inactive. Sorry!";
      this.snackbar = true;
    } else {
      try {
        await axios
          .get(
            "https://web-sandbox.onefootball.com/assignments/player/profile/" +
              foundPlayer["profile-id"]
          )
          .then((res: AxiosResponse<FoundPlayerExtendedProfile>) => {
            this.foundPlayerExtendedProfile = res.data;
            this.showCard = true;
          });
      } catch (error) {
        console.log(error);
      }
    }
  }
}
</script>

<style scopes>
/* .v-btn__content {
    color: black !important;
    font-size: 28px;
    opacity: 100% !important;
} */

.onHover {
  opacity: 0;
}

.v-btn:hover .onHover {
  opacity: 100%;
}
/* .v-btn__content:hover {
    opacity: 100%;
} */
.v-btn:hover .football {
  animation: spinVertical 5s linear infinite;
}

@keyframes spinVertical {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
img {
  margin-left: 0px;
  margin-bottom: 10px;
}
.v-card {
  display: block;
  margin: auto;
}
svg {
  width: 30%;
  display: block;
  margin: auto;
  left: 30%;
  animation: fadeIn 2s;
}
#path15 {
  transition: 1s ease-in-out;
  animation: slideDown 3s;
}
#path19 {
  transition: 1s ease-in-out;
  animation: slideUp 3s;
}

@keyframes slideUp {
  0% {
    transform: translatey(30%);
    opacity: 0%;
  }
  100% {
    transform: translateX(0);
    opacity: 100%;
  }
}

@keyframes slideDown {
  0% {
    transform: translatey(-30%);
    opacity: 0%;
  }
  100% {
    transform: translateX(0);
    opacity: 100%;
  }
}
</style>
