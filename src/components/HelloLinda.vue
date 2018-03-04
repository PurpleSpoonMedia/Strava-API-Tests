<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <!--{{ userzones }}<br />
    {{ userstats }}<br/>
    {{ useractivities }}-->
    <ul>
        <li>
            <p><img :src="userdata.profile" class="profile picture" /></p>
            <p>User ID: {{ userdata.id }}</p>
            <p>Name: {{ userdata.firstname }} {{ userdata.lastname }}</p>
            <p>City: {{ userdata.city }}</p>
            <p>Country: {{ userdata.country }}</p>
        </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloLinda',
  data () {
    return {
        //userzones:[],
        //useractivities:[],
        userdata:[],
        //userstats:[],
        msg: 'Welcome Linda'
    }
  },
  mounted: function () {           
    let self = this;
    axios.get(`https://www.strava.com/api/v3/athletes/2029805?access_token=ebc4a113edeb5165254a36aa5ab45c48ff4bf075`)
        .then((response) => {
            self.userdata = response.data;
        })
        .catch(function (error) {
            console.log(error);
        });

    // axios.get(`https://www.strava.com/api/v3/athletes/2029805/stats?access_token=ebc4a113edeb5165254a36aa5ab45c48ff4bf075`)
    //     .then((response) => {
    //         self.userstats = response.data;
    //     })
    //     .catch(function (error) {
    //         console.log(error);
    //     });

    // axios.get(`https://www.strava.com/api/v3/athletes/2029805/activities?access_token=ebc4a113edeb5165254a36aa5ab45c48ff4bf075`)
    //     .then((response) => {
    //         self.useractivities = response.data;
    //     })
    //     .catch(function (error) {
    //         console.log(error);
    //     });

    // axios.get(`https://www.strava.com/api/v3/athlete/zones?access_token=ebc4a113edeb5165254a36aa5ab45c48ff4bf075`)
    //     .then((response) => {
    //         self.userzones = response.data;
    //     })
    //     .catch(function (error) {
    //         console.log(error);
    //     });
     }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.profile {
    &.picture {
        border-radius:50%;
        border:10px solid #333;
    }
}
</style>
