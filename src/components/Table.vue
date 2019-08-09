<template>
<body>



   
    <b-container fluid>
        <b-row>
   
  
  <h3 class="text-center" > </h3>
 
<div>
   
    <b-modal v-model="modalShow" cancel-disabled  v-bind:title="elementName " ok-only :bg-variant="primary" size="lg">
     <b-badge variant="dark">Number:</b-badge> {{ number }}  
     <b-badge variant="dark">Period:</b-badge> {{ period }}  
     <b-badge variant="dark">Appearance:</b-badge> {{ appearance }} 
     <b-badge variant="dark">Category:</b-badge> {{category}}  <hr> 
     <b-badge variant="dark">Atomic Mass:</b-badge> {{atomicMass}}  
     <b-badge variant="dark">Density:</b-badge> {{density}} 
     <b-badge variant="dark">Symbol:</b-badge> {{symbols}}  
     <b-badge variant="dark">Phase:</b-badge> {{phase}}<hr>
      <b-badge variant="dark">Discovered By:</b-badge> {{discovered_by}} 
      <b-badge variant="dark" >Named By:</b-badge> {{namer}} <hr>

       <b-badge variant="dark">Shells:</b-badge> {{shells}} <hr>
        <b-badge variant="dark">Summary:</b-badge> {{summary}}<hr>
        <b-badge variant="dark">Source:</b-badge>  <a v-bind:href="source" target="blank"> {{source}}</a>
        

    </b-modal>
  </div>

<div>
   
    <b-modal v-model="modalShowBelow"  v-bind:title="lanthanideInfo.name"  ok-only :bg-variant="primary" size="lg">
     <b-badge variant="dark">{{ lanthanideInfo.name }}</b-badge><hr>
     <b-badge variant="dark">{{ lanthanideInfo.number }}</b-badge><hr>
     <b-badge variant="dark">See the series below</b-badge>
     
    </b-modal>
  </div>

<div>
   
    <b-modal v-model="modalShowBelow2"  v-bind:title="actinideInfo.name"  ok-only :bg-variant="primary" size="lg">
     <b-badge variant="dark">{{ actinideInfo.name }}</b-badge><hr>
     <b-badge variant="dark">{{ actinideInfo.number }}</b-badge><hr>
     <b-badge variant="dark">See the series below</b-badge>
     
    </b-modal>
  </div>




<!-- modal-popover.vue -->


<b-col cols="12">
 <section id="periodic_table">
        <div>
            <div>
                <div v-for="element in elements" v-if="element.shells.slice(-1)[0] === 1 && element.category === 'alkali metal' || element.name === 'Hydrogen' " v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary" class="alkali ">
                    <small>{{element.number}}</small>
                  <span class="elsymbol"> {{element.symbol}} </span> 

                 <br> <small> {{element.name}} </small> 
                

                </div> 
               
            </div>
            <div >
                <div v-for="element in elements" v-if="element.shells.slice(-1)[0] === 2 && element.category === 'alkaline earth metal'" v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary"  class="alkali-earth">
                    <small>{{element.number}}</small> 
                 <span class="elsymbol"> {{element.symbol}} </span>
                 <br> <small> {{element.name}} </small> 
                
                </div>
            </div>
            <div>


              


                <div  class="transition"  v-on:click="showInfo(20), modalShow = !modalShow"  v-bind:title=" elements[20].summary"><small> {{elements[20].number}} </small>  <span class="elsymbol">{{elements[20].symbol}}</span> <br>
                  <small> {{elements[20].name}} </small>
              </div> 
                <div  class="transition" v-on:click="showInfo(38), modalShow = !modalShow"  v-bind:title=" elements[38].summary"><small> {{elements[38].number}}</small>  <span class="elsymbol">{{elements[38].symbol}} </span>
                <br>
                  <small> {{elements[38].name}} </small>
              </div> 
                <div class="lanthanide" v-on:click="modalShowBelow = !modalShowBelow">
                <br> <span class="togo elsymbol ">*</span>
                  </div> 
                <div class="actionide" v-on:click="modalShowBelow2 = !modalShowBelow2">
                <br> <span class="togo elsymbol ">**</span>
                  </div> 
            </div>
            <div>



             


                <div class="transition" v-on:click="showInfo(21), modalShow = !modalShow"  v-bind:title=" elements[21].summary"><small> {{elements[21].number}}</small>  <span class="elsymbol">{{elements[21].symbol}} </span>
                <br>
                  <small> {{elements[21].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(39), modalShow = !modalShow"  v-bind:title=" elements[39].summary"><small> {{elements[39].number}}</small>  <span class="elsymbol">{{elements[39].symbol}}</span>
                <br>
                  <small> {{elements[39].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(71), modalShow = !modalShow"  v-bind:title=" elements[71].summary"><small> {{elements[71].number}}</small>  <span class="elsymbol">{{elements[71].symbol}}</span>
                <br>
                  <small> {{elements[71].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(103), modalShow = !modalShow"  v-bind:title=" elements[103].summary"><small> {{elements[103].number}}</small>  <span class="elsymbol">{{elements[103].symbol}}</span>
                <br>
                  <small> {{elements[103].name}} </small>
              </div> 
            </div>
            <div>
             
                <div class="transition" v-on:click="showInfo(22), modalShow = !modalShow"  v-bind:title=" elements[22].summary"><small> {{elements[22].number}}</small>  <span class="elsymbol">{{elements[22].symbol}}</span>
                <br>
                  <small> {{elements[22].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(40), modalShow = !modalShow"  v-bind:title=" elements[40].summary"><small> {{elements[40].number}}</small>  <span class="elsymbol">{{elements[40].symbol}} </span>
                <br>
                  <small> {{elements[40].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(72), modalShow = !modalShow"  v-bind:title=" elements[72].summary"><small> {{elements[72].number}}</small>  <span class="elsymbol">{{elements[72].symbol}} </span>
                <br>
                  <small> {{elements[72].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(104), modalShow = !modalShow"  v-bind:title=" elements[104].summary"><small> {{elements[104].number}}</small>  <span class="elsymbol">{{elements[104].symbol}} </span>
                <br>
                  <small> {{elements[104].name}} </small>
              </div> 
            </div>
            <div>

              


               <div class="transition" v-on:click="showInfo(23), modalShow = !modalShow"  v-bind:title=" elements[23].summary"><small> {{elements[23].number}}</small>  <span class="elsymbol">{{elements[23].symbol}} </span>
               <br>
                  <small> {{elements[23].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(41), modalShow = !modalShow"  v-bind:title=" elements[41].summary"><small> {{elements[41].number}}</small>  <span class="elsymbol">{{elements[41].symbol}} </span>
                <br>
                  <small> {{elements[41].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(73), modalShow = !modalShow"  v-bind:title=" elements[73].summary"><small> {{elements[73].number}}</small>  <span class="elsymbol">{{elements[73].symbol}} </span>
                <br>
                  <small> {{elements[73].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(105), modalShow = !modalShow"  v-bind:title=" elements[105].summary"><small> {{elements[105].number}}</small>  <span class="elsymbol">{{elements[105].symbol}} </span>
                <br>
                  <small> {{elements[105].name}} </small>
              </div> 
            </div>
            <div>


             

                <div class="transition" v-on:click="showInfo(24), modalShow = !modalShow"  v-bind:title=" elements[24].summary"><small> {{elements[24].number}}</small>  <span class="elsymbol">{{elements[24].symbol}} </span>
                <br>
                  <small> {{elements[24].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(42), modalShow = !modalShow"  v-bind:title=" elements[42].summary"><small> {{elements[42].number}}</small>  <span class="elsymbol">{{elements[42].symbol}}</span>
                <br>
                  <small> {{elements[42].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(74), modalShow = !modalShow"  v-bind:title=" elements[74].summary"><small> {{elements[74].number}}</small>  <span class="elsymbol">{{elements[74].symbol}} </span>
                <br>
                  <small> {{elements[74].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(106), modalShow = !modalShow"  v-bind:title=" elements[106].summary"><small> {{elements[106].number}}</small>  <span class="elsymbol">{{elements[106].symbol}} </span>
                <br>
                  <small> {{elements[106].name}} </small>
              </div>
            </div>
            <div>


             

                <div class="transition" v-on:click="showInfo(25), modalShow = !modalShow"  v-bind:title=" elements[25].summary"><small> {{elements[25].number}}</small>  <span class="elsymbol">{{elements[25].symbol}} </span>
                <br>
                  <small> {{elements[25].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(43), modalShow = !modalShow"  v-bind:title=" elements[43].summary"><small> {{elements[43].number}}</small>  <span class="elsymbol">{{elements[43].symbol}} </span>
                <br>
                  <small> {{elements[43].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(75), modalShow = !modalShow"  v-bind:title=" elements[75].summary"><small> {{elements[75].number}}</small>  <span class="elsymbol">{{elements[75].symbol}} </span>
                <br>
                  <small> {{elements[75].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(107), modalShow = !modalShow"  v-bind:title=" elements[107].summary"><small> {{elements[107].number}}</small>  <span class="elsymbol">{{elements[107].symbol}} </span>
                <br>
                  <small> {{elements[107].name}} </small>
              </div>
            </div>
            <div>

               

                <div class="transition" v-on:click="showInfo(26), modalShow = !modalShow"  v-bind:title=" elements[26].summary"><small> {{elements[26].number}}</small>  <span class="elsymbol">{{elements[26].symbol}} </span>
                <br>
                  <small> {{elements[26].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(44), modalShow = !modalShow"  v-bind:title=" elements[44].summary"><small> {{elements[44].number}}</small>  <span class="elsymbol">{{elements[44].symbol}} </span>
                <br>
                  <small> {{elements[44].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(76), modalShow = !modalShow"  v-bind:title=" elements[76].summary"><small> {{elements[76].number}}</small>  <span class="elsymbol">{{elements[76].symbol}} </span>
                <br>
                  <small> {{elements[76].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(108), modalShow = !modalShow"  v-bind:title=" elements[108].summary"><small> {{elements[108].number}}</small>  <span class="elsymbol">{{elements[108].symbol}} </span>
                <br>
                  <small> {{elements[108].name}} </small>
              </div>
            </div>
            <div>


              

                <div class="transition" v-on:click="showInfo(27), modalShow = !modalShow"  v-bind:title=" elements[27].summary"><small> {{elements[27].number}}</small>  <span class="elsymbol">{{elements[27].symbol}} </span>
                <br>
                  <small> {{elements[27].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(45), modalShow = !modalShow"  v-bind:title=" elements[45].summary"><small> {{elements[45].number}}</small>  <span class="elsymbol">{{elements[45].symbol}}</span>
                <br>
                  <small> {{elements[45].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(77), modalShow = !modalShow"  v-bind:title=" elements[77].summary"><small> {{elements[77].number}}</small>  <span class="elsymbol">{{elements[77].symbol}}</span>
                <br>
                  <small> {{elements[77].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(109), modalShow = !modalShow"  v-bind:title=" elements[109].summary"><small> {{elements[109].number}}</small>  <span class="elsymbol">{{elements[109].symbol}}</span>
                <br>
                  <small> {{elements[109].name}} </small>
              </div>
            </div>
            <div>


               

                <div  class="transition" v-on:click="showInfo(28), modalShow = !modalShow"  v-bind:title=" elements[28].summary"><small> {{elements[28].number}}</small>  <span class="elsymbol">{{elements[28].symbol}} </span>
                <br>
                  <small> {{elements[28].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(46), modalShow = !modalShow"  v-bind:title=" elements[46].summary"><small> {{elements[46].number}}</small>  <span class="elsymbol">{{elements[46].symbol}}</span>
                <br>
                  <small> {{elements[46].name}} </small>
              </div> 
                <div  class="transition" v-on:click="showInfo(78), modalShow = !modalShow"  v-bind:title=" elements[78].summary"><small> {{elements[78].number}}</small>  <span class="elsymbol">{{elements[78].symbol}}</span>
                <br>
                  <small> {{elements[78].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(110), modalShow = !modalShow"  v-bind:title=" elements[110].summary"><small> {{elements[110].number}}</small>  <span class="elsymbol">{{elements[110].symbol}}</span>
                <br>
                  <small> {{elements[110].name}} </small>
              </div>
            </div>
            <div>

              

                <div class="transition" v-on:click="showInfo(29), modalShow = !modalShow"  v-bind:title=" elements[29].summary"><small> {{elements[29].number}}</small>  <span class="elsymbol">{{elements[29].symbol}}</span>
                <br>
                  <small> {{elements[29].name}} </small>
              </div> 
                <div  class="transition" v-on:click="showInfo(47), modalShow = !modalShow"  v-bind:title=" elements[47].summary"><small> {{elements[47].number}}</small>  <span class="elsymbol">{{elements[47].symbol}}</span>
                <br>
                  <small> {{elements[47].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(79), modalShow = !modalShow"  v-bind:title=" elements[79].summary"><small> {{elements[79].number}}</small>  <span class="elsymbol">{{elements[79].symbol}}</span>
                <br>
                  <small> {{elements[79].name}} </small>
              </div> 
                <div class="transition" v-on:click="showInfo(111), modalShow = !modalShow"  v-bind:title=" elements[111].summary"><small> {{elements[111].number}}</small>  <span class="elsymbol">{{elements[111].symbol}}</span>
                <br>
                  <small> {{elements[111].name}} </small>
              </div>
            </div>

          <div>
            <div class="metalloids" v-on:click="showInfo(4), modalShow = !modalShow"  v-bind:title=" elements[4].summary"><small> {{elements[4].number}}</small>  <span class="elsymbol">{{elements[4].symbol}}</span>
                <br>
                  <small> {{elements[4].name}} </small>
              </div>

                <div v-for="element in elements" v-if="element.shells.slice(-1)[0] === 3 && element.name !== 'Lawrencium' && element.name !== 'Boron'  " v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary" class="post-transition">
                    <small> {{element.number}}</small> 
                  <span class="elsymbol"> {{element.symbol}} </span> <br>
                  <small> {{element.name}} </small> 
                  

                </div>  

                
          </div>


            <div>
                

                <div v-for="element in elements" class="metalloids" v-if="element.shells.slice(-1)[0] === 4 && element.name !== 'Tin' && element.name !== 'Lead' && element.name !== 'Flerovium'" v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary"  >
                    <small>{{element.number}}</small>
                  <span class="elsymbol"> {{element.symbol}} </span> 
                  <br>
                  <small> {{element.name}} </small>
                  

                </div> 
                 <div class="post-transition" v-on:click="showInfo(49), modalShow = !modalShow"  v-bind:title=" elements[49].summary"><small> {{elements[49].number}}</small>  <span class="elsymbol">{{elements[49].symbol}}</span>
                <br>
                  <small> {{elements[49].name}} </small>
              </div>
               <div  class="post-transition" v-on:click="showInfo(81), modalShow = !modalShow"  v-bind:title=" elements[81].summary"><small> {{elements[81].number}}</small>  <span class="elsymbol">{{elements[81].symbol}}</span>
                <br>
                  <small> {{elements[81].name}} </small>
              </div>
               <div  class="post-transition" v-on:click="showInfo(113), modalShow = !modalShow"  v-bind:title=" elements[113].summary"><small> {{elements[113].number}}</small>  <span class="elsymbol">{{elements[113].symbol}}</span>
                <br>
                  <small> {{elements[113].name}} </small>
              </div>
                
          </div>
            

            <div>
                <div v-for="element in elements" v-if="element.shells.slice(-1)[0] === 5 && element.name !== 'Arsenic' && element.name !== 'Antimony' && element.name !== 'Bismuth' && element.name !== 'Moscovium'" v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary"  class="non-metals">
                    <small>{{element.number}}</small>
                  <span class="elsymbol"> {{element.symbol}} </span>
                  <br>
                  <small> {{element.name}} </small>
                  

                </div> 
                 <div class="metalloids" v-on:click="showInfo(32), modalShow = !modalShow"  v-bind:title=" elements[32].summary"><small> {{elements[32].number}}</small>  <span class="elsymbol">{{elements[32].symbol}}</span>
                <br>
                  <small> {{elements[32].name}} </small>
              </div>
               <div class="metalloids" v-on:click="showInfo(50), modalShow = !modalShow"  v-bind:title=" elements[50].summary"><small> {{elements[50].number}}</small>  <span class="elsymbol">{{elements[50].symbol}}</span>
                <br>
                  <small> {{elements[50].name}} </small>
              </div>
              <div class="post-transition" v-on:click="showInfo(82), modalShow = !modalShow"  v-bind:title=" elements[82].summary"><small> {{elements[82].number}}</small>  <span class="elsymbol">{{elements[82].symbol}}</span>
                <br>
                  <small> {{elements[82].name}} </small>
              </div>
              <div class="post-transition" v-on:click="showInfo(114), modalShow = !modalShow"  v-bind:title=" elements[114].summary"><small> {{elements[114].number}}</small>  <span class="elsymbol">{{elements[114].symbol}}</span>
                <br>
                  <small> {{elements[114].name}} </small>
              </div>
                
          </div>
            
            
             <div>
                <div v-for="element in elements" v-if="element.shells.slice(-1)[0] === 6 && element.name !== 'Tellurium' && element.name !== 'Polonium' && element.name !== 'Livermorium' " v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary" class="non-metals">
                    <small>{{element.number}}</small>
                  <span class="elsymbol"> {{element.symbol}} </span> 
                  <br>
                  <small> {{element.name}} </small>

                </div> 

                 <div class="metalloids" v-on:click="showInfo(51), modalShow = !modalShow"  v-bind:title=" elements[51].summary"><small> {{elements[51].number}}</small>  <span class="elsymbol">{{elements[51].symbol}}</span>
                <br>
                  <small> {{elements[51].name}} </small>
              </div>
               <div class="metalloids" v-on:click="showInfo(83), modalShow = !modalShow"  v-bind:title=" elements[83].summary"><small> {{elements[83].number}}</small>  <span class="elsymbol">{{elements[83].symbol}}</span>
                <br>
                  <small> {{elements[83].name}} </small>
              </div>
               <div class="post-transition" v-on:click="showInfo(115), modalShow = !modalShow"  v-bind:title=" elements[115].summary"><small> {{elements[115].number}}</small>  <span class="elsymbol">{{elements[115].symbol}}</span>
                <br>
                  <small> {{elements[115].name}} </small>
              </div>
                
          </div>
            <div>
                <div v-for="element in elements" v-if="element.shells.slice(-1)[0] === 7  " v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary"  class="halogen">
                    <small>{{element.number}}</small>
                  <span class="elsymbol"> {{element.symbol}} </span>
                  <br>
                  <small> {{element.name}} </small>

                </div> 
                
          </div>
            <div>
                <div v-for="element in elements" v-if="element.shells.slice(-1)[0] === 8 || element.name === 'Helium'  " v-on:click="showInfo(element.number-1), modalShow = !modalShow" v-bind:v-b-tooltip.hover="element.name" v-bind:title=" element.summary"  class="noble">
                    <small>{{element.number}}</small>
                  <span class="elsymbol"> {{element.symbol}} </span> 
                  <br>
                  <small> {{element.name}} </small>

                </div> 
                
          </div>
        </div>
        <div>

             <div>

                <div class="lanthanide"   >
                   <span class="elsymbol">  *  </span>
                    <br>
                  <small> Lanthanides </small>
              </div> 
                <div class="actionide" >
                    <span class="elsymbol"> **</span> <br>
                  <small> Actinides </small>
              </div> 

             


            </div>



            <div>

                <div class="lanthanide" v-on:click="showInfo(56), modalShow = !modalShow"  v-bind:title=" elements[56].summary" ><small> {{elements[56].number}}</small> 
                     <span class="elsymbol">{{elements[56].symbol}}</span>  
                    <br>
                  <small> {{elements[56].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(88), modalShow = !modalShow" v-bind:title=" elements[88].summary"><small> {{elements[88].number}}</small> 
                     <span class="elsymbol">{{elements[88].symbol}}</span> <br>
                  <small> {{elements[88].name}} </small>
              </div> 


            </div>




            <div>
                <div class="lanthanide"  v-on:click="showInfo(57), modalShow = !modalShow" v-bind:title=" elements[57].summary"><small> {{elements[57].number}}</small>  <span class="elsymbol">{{elements[57].symbol}}</span>  <br>
                  <small> {{elements[57].name}} </small></div> 
                <div class="actionide" v-on:click="showInfo(89), modalShow = !modalShow" v-bind:title=" elements[89].summary"><small> {{elements[89].number}}</small>  <span class="elsymbol">{{elements[89].symbol}}</span> <br>
                  <small> {{elements[89].name}} </small></div> 

               
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(58), modalShow = !modalShow" v-bind:title=" elements[58].summary"><small> {{elements[58].number}}</small>  <span class="elsymbol">{{elements[58].symbol}}</span> <br>
                  <small> {{elements[58].name}} </small></div> 
                <div class="actionide" v-on:click="showInfo(90), modalShow = !modalShow" v-bind:title=" elements[90].summary"><small> {{elements[90].number}}</small>  <span class="elsymbol">{{elements[90].symbol}}</span> <br>
                  <small> {{elements[90].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(59), modalShow = !modalShow" v-bind:title=" elements[59].summary"> <span class="elsymbol">{{elements[59].symbol}}</span>
                <br>
                  <small> {{elements[59].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(91), modalShow = !modalShow" v-bind:title=" elements[91].summary"> <span class="elsymbol">{{elements[91].symbol}}</span>
                <br>
                  <small> {{elements[91].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(60), modalShow = !modalShow" v-bind:title=" elements[60].summary"><small> {{elements[60].number}}</small>  <span class="elsymbol">{{elements[60].symbol}} </span>
                <br>
                  <small> {{elements[60].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(92), modalShow = !modalShow" v-bind:title=" elements[92].summary"><small> {{elements[92].number}}</small>  <span class="elsymbol">{{elements[92].symbol}}</span>
                <br>
                  <small> {{elements[92].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide"  v-on:click="showInfo(61), modalShow = !modalShow" v-bind:title=" elements[61].summary"><small> {{elements[61].number}}</small>  <span class="elsymbol">{{elements[61].symbol}}</span>
                <br>
                  <small> {{elements[61].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(93), modalShow = !modalShow" v-bind:title=" elements[93].summary"><small> {{elements[93].number}}</small>  <span class="elsymbol">{{elements[93].symbol}}</span>
                <br>
                  <small> {{elements[93].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(62), modalShow = !modalShow" v-bind:title=" elements[62].summary"><small> {{elements[62].number}}</small>  <span class="elsymbol">{{elements[62].symbol}}</span>
                <br>
                  <small> {{elements[62].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(94), modalShow = !modalShow" v-bind:title=" elements[94].summary"><small> {{elements[94].number}}</small>  <span class="elsymbol">{{elements[94].symbol}}</span>
                <br>
                  <small> {{elements[94].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide"  v-on:click="showInfo(63), modalShow = !modalShow" v-bind:title=" elements[63].summary"><small> {{elements[63].number}}</small>  <span class="elsymbol">{{elements[63].symbol}}</span>
                <br>
                  <small> {{elements[63].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(95), modalShow = !modalShow" v-bind:title=" elements[95].summary"><small> {{elements[95].number}}</small>  <span class="elsymbol">{{elements[95].symbol}}</span>
                <br>
                  <small> {{elements[95].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(64), modalShow = !modalShow" v-bind:title=" elements[64].summary"><small> {{elements[64].number}}</small>  <span class="elsymbol">{{elements[64].symbol}}</span>
                <br>
                  <small> {{elements[64].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(96), modalShow = !modalShow" v-bind:title=" elements[96].summary"><small> {{elements[96].number}}</small>  <span class="elsymbol">{{elements[96].symbol}}</span>
                <br>
                  <small> {{elements[96].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(65), modalShow = !modalShow" v-bind:title=" elements[65].summary"><small> {{elements[65].number}}</small>  <span class="elsymbol">{{elements[65].symbol}}</span>
                <br>
                  <small> {{elements[65].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(97), modalShow = !modalShow" v-bind:title=" elements[97].summary"><small> {{elements[97].number}}</small>  <span class="elsymbol">{{elements[97].symbol}}</span>
                <br>
                  <small> {{elements[97].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(66), modalShow = !modalShow" v-bind:title=" elements[66].summary"><small> {{elements[66].number}}</small>  <span class="elsymbol">{{elements[66].symbol}}</span>
                <br>
                  <small> {{elements[66].name}} </small></div> 
                <div class="actionide" v-on:click="showInfo(98), modalShow = !modalShow" v-bind:title=" elements[98].summary"><small> {{elements[98].number}}</small>  <span class="elsymbol">{{elements[98].symbol}}</span>
                <br>
                  <small> {{elements[98].name}} </small></div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(67), modalShow = !modalShow" v-bind:title=" elements[67].summary"><small> {{elements[67].number}}</small>  <span class="elsymbol">{{elements[67].symbol}}</span>
                <br>
                  <small> {{elements[67].name}} </small>
              </div> 
                <div class="actionide"  v-on:click="showInfo(99), modalShow = !modalShow" v-bind:title=" elements[99].summary"><small> {{elements[99].number}}</small>  <span class="elsymbol">{{elements[99].symbol}}</span>
                <br>
                  <small> {{elements[99].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide"  v-on:click="showInfo(68), modalShow = !modalShow" v-bind:title=" elements[68].summary"><small> {{elements[68].number}}</small>  <span class="elsymbol">{{elements[68].symbol}}</span>
                <br>
                  <small> {{elements[68].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(100), modalShow = !modalShow" v-bind:title=" elements[100].summary"><small> {{elements[100].number}}</small>  <span class="elsymbol">{{elements[100].symbol}}</span>
                <br>
                  <small> {{elements[100].name}} </small>
              </div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(69), modalShow = !modalShow" v-bind:title=" elements[69].summary"><small> {{elements[69].number}}</small>  <span class="elsymbol">{{elements[69].symbol}}</span>
                <br>
                  <small> {{elements[69].name}} </small></div> 
                <div class="actionide" v-on:click="showInfo(101), modalShow = !modalShow" v-bind:title=" elements[101].summary"><small> {{elements[101].number}}</small>  <span class="elsymbol">{{elements[101].symbol}}</span>
                <br>
                  <small> {{elements[101].name}} </small></div> 
            </div>
            <div>
                <div class="lanthanide" v-on:click="showInfo(70), modalShow = !modalShow" v-bind:title=" elements[70].summary"><small> {{elements[70].number}}</small>  <span class="elsymbol">{{elements[70].symbol}}</span>
                <br>
                  <small> {{elements[70].name}} </small>
              </div> 
                <div class="actionide" v-on:click="showInfo(102), modalShow = !modalShow" v-bind:title=" elements[102].summary"><small> {{elements[102].number}}</small>  <span class="elsymbol">{{elements[102].symbol}}</span>
                <br>
                  <small> {{elements[102].name}} </small>
              </div> 
          </div>
    </div>
    <!--****************************KEY*******************************************-->
    <div>
      
          
            <div>
              <div class=" key" v-on:click=""  ><small>Key   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
              
             
             
            </div>
              
<div>
              <div class="" v-on:click=""  ><small>Key   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
             
             
             
            </div>

            <div>
              <div class="alkali" v-on:click=""  ><small>Alkali   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
             
             
             
            </div>
            <div>
              <div class="alkali-earth" v-on:click=""  ><small>Akali Earth   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
             
            </div>

            <div>
              <div class="transition" v-on:click=""  ><small>Transition   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
            </div>
              <div>
              <div class="metalloids" v-on:click=""  ><small>Metalloids   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
             
             
             
            </div>

             <div>
              <div class="post-transition" v-on:click=""  ><small>Post Trans   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
            
            </div>
              <div>
              <div class="non-metals" v-on:click=""  ><small>Non-Metals   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
            
            </div>
             <div>
              <div class="halogen" v-on:click=""  ><small>Halogens   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
            
            </div>
              <div>
              <div class="noble" v-on:click=""  ><small>Noble Gases   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
            
            </div>
             <div>
              <div class="lanthanide" v-on:click=""  ><small>Lanthanide   </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
            
            </div>
             
              <div>
              <div class="actionide" v-on:click=""  ><small>Actinide  </small>  <span class="elsymbol">  </span>
                <br>
                  <small>    </small>
              </div>
            
            </div>
             
             
             
             
             
            </div>
              

    </div>

    </section>
    </b-col>
        
    </b-row>

    
</b-container>
    

 </body>


</template>

<script>

export default {
  props: {
      elements: {
        type: Array,
        required: true
      }
    },
  data () {
    return {
     
     copyright : 'copyright 2017',
      group1: 1,
      title : "this element name",
      elementName: 'element name comes here',
      appearance: 'Appearance comes here',
      summary: 'summary comes here',
      atomicMass: 1,
      category: 'The category ',
      color: 'color',
      phase: 'phase',
      density: 'density',
      symbols:'symbol',
      shells: 'shells',
      number: 1,
      period: 1,
      discovered_by: 'Discoverer ',
      namer: 'Someone name this thing',
      source: 'Source',
      modalShow: false,
      modalShowBelow: false,
      modalShowBelow2: false,
      lanthanideInfo:{
        name: "Lanthanides",
        number: "57-71"
      },
     actinideInfo:{
        name: "Actinides",
        number: "89-103"
      }
    



    }
  },
  created() {
        this.fetchData(); 
    },
 methods: {
        showInfo: function(index){
          
           //console.log(this.elements[index].name);
           var elInfo = this.elements[index].name;
           var elAppearance =  this.elements[index].appearance;
           var elSummary =  this.elements[index].summary;
            var elCategory =  this.elements[index].category;
             var elColor =  this.elements[index].color;
              var elPhase =  this.elements[index].phase;
              var elDensity =  this.elements[index].density; 
              var elSymbols =  this.elements[index].symbol; 
              var elShells =  this.elements[index].shells; 
              var elMass =  this.elements[index].atomic_mass; 
              var elNumber =  this.elements[index].number; 
              var elPeriod =  this.elements[index].period; 
              var elDiscover =  this.elements[index].discovered_by; 
              var elNamer = this.elements[index].named_by;
              var elSource =  this.elements[index].source;
        
             


           this.elementName = elInfo;
           this.appearance = elAppearance;
           this.summary = elSummary;

           this.category = elCategory;
           this.color = elColor;
           this.phase = elPhase;
           this.density = elDensity;
           this.symbols = elSymbols;
           this.shells = elShells;
           this.atomicMass = elMass;
            this.number = " " + elNumber + " ";
            this.period = elPeriod;
             this.discovered_by = elDiscover;
             this.namer = elNamer;
             this.source = elSource;
             
          
        },
        showInfoSingle: function(index){
            //alert("Bang");
           var elInfo = this.elements[index].name;
           var elAppearance =  this.elements[index].appearance;
           var elSummary =  this.elements[index].summary;
           this.elementName = elInfo;
        }
       
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>



    #periodic_table {
    width: 100%;
    min-width: 300px;
    margin-left: 2%; 
    margin-top: 10px;

}


.key{
  background: blue;
}

#periodic_table > div {
    margin-bottom: 2%;
}

#periodic_table > div > div {
    width: 5.5%;
    display: inline-block;
    margin-right: -7px;
}

#periodic_table > div > div > div {
    border: 2px solid white;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    text-align: center;
    /*background: #ccc;*/
    margin-top: -3px;
    padding: 10% 0;
    color: white;
    font-style: bold;
    cursor: pointer;
}
#periodic_table >div >div > div:hover{
   /* border: 2px solid black;*/
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    text-align: center;
    /*background: white;*/
    margin-top: -3px;
    padding: 10% 0;
    cursor: pointer;
    box-shadow: inset 0 0 0 2px white;
    color: white;


}

.elsymbol{
  font-size: 16px;
  color: white;
}
.series{
  font-size: 16px;
  color: white;
}
.alkali {
    background: #A6A9D7;
}
.alkali-earth{
    background: #787CB3;
}
.group4{
    background: #FF0099;
}
.halogen{
    background: #D8C154;
}
.noble{
     background: #D5D754;
}
.lanthanide{
    background: #226F68;
}
.actionide{
    background: #2AA79E;
}
.transition{
    background: #B17FBD;
}
.post-transition{
background: #E57BC8;
}
.metalloids{
    background: #61CB16;
}
.non-metals{
    background: #70BD39;
}
/* Sweep To Left */
.hvr-sweep-to-left {
  display: inline-block;
  vertical-align: middle;
  -webkit-transform: perspective(1px) translateZ(0);
  transform: perspective(1px) translateZ(0);
  box-shadow: 0 0 1px transparent;
  position: relative;
  -webkit-transition-property: color;
  transition-property: color;
  -webkit-transition-duration: 0.3s;
  transition-duration: 0.3s;
}
small{
    font-size: 10px;
}


@media(max-width:900px) {

small{
  display: none;
}
.elsymbol{
  font-size: 14px;
  color: white;
}
.togo{
  font-size: 8px;
  display: none;
}
}
@media(max-width:800px) {

small{
  font-size: 8px;
}
.elsymbol{
  font-size: 14px;
  color: white;
}
.togo{
  font-size: 8px;
  display: none;
}
}
@media(max-width:600px) {
  #periodic_table > div > div > div{

    border: 1px solid white;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    text-align: center;
    /*background: #ccc;*/
    margin-top: -3px;
    padding: 5% 0;
    color: white;
    font-style: bold;
    cursor: pointer;
    font-size: 16px;
  }

  .elsymbol{
  font-size: 12px;
  color: white;
}

  }


  @media(max-width:200px) {

    small{
  display: none;
}
.elsymbol{
  font-size: 6px;
  color: white;
}
.togo{
  font-size: 8px;
  display: none;
}

    }

</style>
