<template>
	<div>
      <div class="main">
          <button @click="addEvent()">Begin Events</button>
          <hr />
      </div>

      <center>

        <div v-for="i in activeEvents" :key=i.activeEvents>
          <p>{{ i.title }}</p>
          <hr />
        </div>

      </center>
  </div>
</template>

<script>
export default {
    name: 'App',
    data: function() {
        return {
        events: [
                    {
                    "title":"The Holidays Are Approaching and Consumer Spending is Going up",
                    "effects":[{
                        "positiveIndustries":["gaments", "tech", "entertainment", "finance", "restaurant", "energy","mining", "agriculture", "transport"],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"As work days increase in length, working parents opt to go out to eat more",
                    "effects":[{
                        "positiveIndustries":["restaurant"],
                        "negativeIndustries":["entertainment"]
                    }]
                    },

                    {
                    "title":"Leaked military documents cause public outcry, culminating in mounting political pressure to withdraw from armed conflicts around the world",
                    "effects":[{
                        "positiveIndustries":["legal"],
                        "negativeIndustries":["defense"]
                    }]
                    },

                    {
                    "title":"Financial regulation just passed in the house, capping the interest payday lenders can charge to clients",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["finance"]
                    }]
                    },

                    {
                    "title":"OnlyFriends releases a new service that optimizes the way a content creator can target ads to their fan base",
                    "effects":[{
                        "positiveIndustries":["tech","entertainment"],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"Farmers report good harvest season",
                    "effects":[{
                        "positiveIndustries":["restaurant"],
                        "negativeIndustries":["agriculture"]
                    }]
                    },

                    {
                    "title":"Bangladeshi authorities are cracking down on underage workers in garment factories",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["garments"]
                    }]
                    }, 

                    {
                    "title":"A disease infecting livestock living on CAFOs is decimating meat production",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["restaurant", "agriculture"]
                    }]
                    },

                    {
                    "title":"ExOnMobile powered by BigBrother Recon makes stalking easier than it's ever been, for a price of course!",
                    "effects":[{
                        "positiveIndustries":["defense", "tech"],
                        "negativeIndustries":[]
                    }]
                    },  

                    {
                    "title":"CrackedRockShale starts drilling on indigenous burial grounds, regulators aren’t intervening",
                    "effects":[{
                        "positiveIndustries":["legal", "energy", "construction","chemicals"],
                        "negativeIndustries":[]
                    }] 
                    },

                    {
                    "title":"Feds lower interest rate, average per capita debt goes up 12%",
                    "effects":[{
                        "positiveIndustries":["finance","restaurant","entertainment","construction","transport", "gaments"],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"Landslides caused by hap hazard developers looking to save money resulted in the deaths of 15 construction workers. Workers looking to unionize",
                    "effects":[{
                        "positiveIndustries":["legal"],
                        "negativeIndustries":["construction", "insurance"]
                    }]
                    },

                    {
                    "title":"Sitting is the new smoking: Doctors report increased health concerns with the modern sedentary lifestyle",
                    "effects":[{
                        "positiveIndustries":["healthcare", "pharma"],
                        "negativeIndustries":["insurance"]
                    }]
                    },

                    {
                    "title":"Its fashion season, MothBite garments are on sale!",
                    "effects":[{
                        "positiveIndustries":["gaments"],
                        "negativeIndustries":["entertainment","defense"]
                    }]
                    },

                    {
                    "title":"Antibiotic resistance causes real concern as medical industry left blind sighted",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["pharma","insurance","agriculture"]
                    }]
                    },

                    {
                    "title":"Government incentives lead to increased number of homes retrofitted with solar panels",
                    "effects":[{
                        "positiveIndustries":["insurance", "finance","mining"],
                        "negativeIndustries":["energy", "healthcare","defense"]
                    }]
                    },

                    {
                    "title":"Big cities make big investments in rail, metro systems",
                    "effects":[{
                        "positiveIndustries":["construction","finance","mining","insurance"],
                        "negativeIndustries":["transport","energy","defense"]
                    }]
                    },

                    {
                    "title":"Pink slime? Gross! Fast food industry facing backlash after former employee exposes the ingredients behind the ‘food’ being served",
                    "effects":[{
                        "positiveIndustries":["insurance"],
                        "negativeIndustries":["restaurant","healthcare"]
                    }]
                    },

                    {
                    "title":"Gaming or Gambling? Same thing according to the FTC!",
                    "effects":[{
                        "positiveIndustries":["entertainment", "construction"],
                        "negativeIndustries":["garments", "legal"]
                    }]
                    },

                    {
                    "title":"Executive order just signed allows multi national corporations to seize land they want to develop using eminent domain",
                    "effects":[{
                        "positiveIndustries":["energy", "construction", "finance", "mining"],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"Government begins setting quota for affordable housing",
                    "effects":[{
                        "positiveIndustries":["gaments","energy"],
                        "negativeIndustries":["construction", "legal"]
                    }]
                    },

                    {
                    "title":"Breakthrough in Genetically modified foods. Doubles harvest of corn",
                    "effects":[{
                        "positiveIndustries":["agriculture", "restaurant"],
                        "negativeIndustries":["chemicals"]
                    }]
                    },

                    {
                    "title":"Oil refinery spills huge quantities of oil, ecologists reporting flammable watersheds",
                    "effects":[{
                        "positiveIndustries":["legal","healthcare","pharma","chemicals"],
                        "negativeIndustries":["energy","agriculture"]
                    }]
                    },

                    {
                    "title":"Hospitals going out of pocket to pay for larger beds to accommodate obese patients",
                    "effects":[{
                        "positiveIndustries":["pharma","restaurant","construction"],
                        "negativeIndustries":["healthcare","insurance"]
                    }]
                    },

                    {
                    "title":"Cyber attack brings critical infrastructure to a halt",
                    "effects":[{
                        "positiveIndustries":["legal","defense"],
                        "negativeIndustries":["insurance","energy","construction","tech"]
                    }]
                    },

                    {
                    "title":"Industry Boom! Multi Level marketing on the rise, targeting those that wish to live the American dream",
                    "effects":[{
                        "positiveIndustries":["garments","pharma"],
                        "negativeIndustries":["entertainment","finance"]
                    }]
                    },

                    {
                    "title":"Markets hit all time lows, retirement funds wiped out",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["finance","tech","entertainment","legal","insurance","transport","mining","garments","construction"]
                    }]
                    },

                    {
                    "title":"Public concerned with privacy as ExOnMobile & OnlyFriends update user agreement",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["tech"]
                    }]
                    },

                    {
                    "title":"MSM reports terrorism on the rise, national security raised to public agenda #1",
                    "effects":[{
                        "positiveIndustries":["defense", ""],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"CryptoCurrency surges, financial institutions caught off guard",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"Trade war has sparked between US and China, worst in history",
                    "effects":[{
                        "positiveIndustries":["defense"],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"Conspiracy Uncovered: Auto manufacturers working with insurance industry to make drivers more likely to die in crashes because 'it's easier to dispute premiums with the dead'",
                    "effects":[{
                        "positiveIndustries":["legal"],
                        "negativeIndustries":["insurance","transport"]
                    }]
                    },

                    {
                    "title":"Racial Justice Activists: 'A Racial Reckoning is Coming'",
                    "effects":[{
                        "positiveIndustries":["defense","tech"],
                        "negativeIndustries":["insurance","legal","finance"]
                    }]
                    },

                    {
                    "title":"University Endowments Grow as Student Debt Continues to Rise",
                    "effects":[{
                        "positiveIndustries":["finance"],
                        "negativeIndustries":["entertainment","garments","restaurant","insurance"]
                    }]
                    },

                    {
                    "title":"Teachers Union Begins Strike Demanding Higher Wages, Schools Across The Country No Longer In Session",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["construction"]
                    }]
                    },

                    {
                    "title":"Power Outages Rock The Grid Revealing Instability in Core Infrastructure",
                    "effects":[{
                        "positiveIndustries":[],
                        "negativeIndustries":["entertainment","finance","construction","energy"]
                    }]
                    },

                    {
                    "title":"Winter is Here: Frozen Pipes Hit Residential Areas Hardest",
                    "effects":[{
                        "positiveIndustries":["restaurant","construction","chemicals"],
                        "negativeIndustries":["insurance","energy","transport"]
                    }]
                    },

                    {
                    "title":"Vamos A La Plastic- Environmental Surveys Finds Record Amount of Plastics Washed Up On Beaches",
                    "effects":[{
                        "positiveIndustries":["tech"],
                        "negativeIndustries":["chemicals","restaurant","garments"]
                    }]
                    },

                    {
                    "title":"DoubleArches CEO Michael Greenbrook Just Got Served… With Divorce Papers",
                    "effects":[{
                        "positiveIndustries":["entertainment"],
                        "negativeIndustries":[]
                    }]
                    },

                    {
                    "title":"Prohibition 2.0? Moms Declare War On Alcohol!",
                    "effects":[{
                        "positiveIndustries":["insurance"],
                        "negativeIndustries":["restaurant"]
                    }]
                    }
                ], // in build we will have json imported from assets and iterate data using v-loop
        activeEvents: [],
        i: 0,
        eventDelay: .1, // in seconds
        run: true,

            }
    },
    methods: {
        
        addEvent() {
          let currentEvent = this.events[this.i]
          this.activeEvents.splice(0, 0, currentEvent)
          this.i++
          this.computeEffects(currentEvent)
          setTimeout(this.addEvent, this.eventDelay*1000)
        },
        computeEffects(ev) {
          
          console.log(ev.effects[0].positiveIndustries[0])
          console.log(this.i)
          // for (let i = 0; i < ev.effects.length; i++) {

          // }
            
        },
    }
}
</script>
    
<style>

.main {
    position: sticky;
    top: 0; 
    background-color: white;
}                       

</style>

