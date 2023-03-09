<script>

export default{
    data(){
        return {
            climate: 'clear',
        }
    },
    methods:{
        getClassByClimate(){
            var classes = {
                'clear': 'Clear',
                'raining': 'Raining',
                'thunders': 'Thunders'
            }
            return classes[this.climate];
        }
    }
}
</script>

<template>
    <h1>Weather Widget</h1>
    <label for="climate">Climate:</label>
    <select name="climate" id="climate" v-model="climate">
        <option value="clear">Clear</option>
        <option value="raining">Raining</option>
        <option value="thunders">Thunders</option>
    </select>

    <hr>

    <div id="WeatherWidget">
        <div id="WeatherIndicator" :class="['Day', getClassByClimate()]">
            <div class="TopBar">
                <div class="left">Day</div>
                <div class="center"><i class="fa-solid fa-ellipsis"></i></div>
                <div class="right"><i class="far fa-heart"></i></div>
            </div>
            <div class="Icon"></div>
            <div class="Temperature">32°</div>
            <div class="Location">Bento Gonçalves</div>
            <div class="Details">
                <div>
                    <div class="Label">Wind</div>
                    <div class="Value">15<span class="Symbol">km</span></div>
                </div>

                <div>
                    <div class="Label">Humidity</div>
                    <div class="Value">32<span class="Symbol">%</span></div>
                </div>

                <div>
                    <div class="Label">Precipitation</div>
                    <div class="Value">87<span class="Symbol">%</span></div>
                </div>
            </div>
        </div>

        <div id="WeatherIndicator" :class="['Night', getClassByClimate()]">
        </div>
    </div>
</template>

<style scoped>
#WeatherWidget{
    display: flex;
    flex-direction: column;
    background-color: #3A3E4A;
    padding: 20px;
    height: auto;
    width: 300px;
    border-radius: 40px;
}

#WeatherIndicator{
    display: flex;
    flex-direction: column;
    padding: 16px 20px;
    border-radius: 40px;
    color: white;
    height: auto;

}
.Day{
    background-color: blue;
    margin-bottom: 20px;
}

.Night{
    background-color: #23262E;
    height: 50px;
}

.Day.Clear{
    background-color: #46A7FA;
}

.Day.Raining{
    background-color: #1674BB;
}

.Day.Thunders{
    background-color: #175A8D;
}

#WeatherIndicator .TopBar{
    display: flex;
    flex-direction: row;
}

#WeatherIndicator .TopBar .left{
    flex: 1;
    text-align: left;
}
#WeatherIndicator .TopBar .center{
    flex: 1;
    text-align: center;
}
#WeatherIndicator .TopBar .right{
    flex: 1;
    text-align: right;
}

#WeatherIndicator .Temperature{
    text-align: center;
    font-weight: bold;
    font-size: 50px;
}

#WeatherIndicator .Location{
    text-align: center;
    font-size: 20px;
}


#WeatherIndicator .Details{
    display: flex;
    text-align: center;
    flex-direction: row;
    margin-top: 30px;
}

#WeatherIndicator .Details div{
    flex: 1;
    text-align: center;
}

#WeatherIndicator .Details .Label{
    font-size: 14px;
}

#WeatherIndicator .Details .Value{
    font-size: 30px;
    font-weight: bold;
}

#WeatherIndicator .Details .Symbol{
    font-size: 16px;
    font-weight: normal;
}
/*#Night.Sun{
    background-color: #46A7FA;
}

#Night.Raining{
    background-color: #1674BB;
}

#Night.Thunders{
    background-color: #175A8D;
}*/
</style>