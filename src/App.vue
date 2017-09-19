<template>
  <div id="app">

<div id="skipnav"><a href="#maincontent">Skip to main content</a></div>

    <!-- Navigation -->
    <nav id="mainNav" class="navbar navbar-default navbar-fixed-top navbar-custom">
        <div class="container">
            <!-- Brand and toggle get grouped for better mobile display -->
            <div class="navbar-header page-scroll">
                <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
                    <span class="sr-only">Toggle navigation</span> Menu <i class="fa fa-bars"></i>
                </button>
                <a class="navbar-brand" href="#page-top">Jordan Braginton</a>
            </div>

            <!-- Collect the nav links, forms, and other content for toggling -->
            <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
                <ul class="nav navbar-nav navbar-right">
                    <li class="hidden">
                        <a href="#page-top"></a>
                    </li>
                    <li class="page-scroll">
                        <a href="#portfolio">Portfolio</a>
                    </li>
                    <li class="page-scroll">
                        <a href="#about">About</a>
                    </li>
                    <li class="page-scroll">
                        <a href="#contact">Contact</a>
                    </li>
                </ul>
            </div>
            <!-- /.navbar-collapse -->
        </div>
        <!-- /.container-fluid -->
    </nav>

    <!-- Header -->
    <header>
        <div class="container" id="maincontent" tabindex="-1">
            <div class="row">
                <div class="col-lg-12">
                    <img class="img-responsive" src="src/img/profile.png" alt="">
                    <div class="intro-text">
                        <h1 class="name">Jordan Braginton</h1>
                        <hr class="star-light">
                        <span class="skills">Web Developer - Data System Manager - Software Engineer</span>
                    </div>
                </div>
            </div>
        </div>
    </header>
    <button v-on:click="openModal()">modal</button>
    <!-- Portfolio Grid Section -->
    <section id="portfolio">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h2>Portfolio</h2>
                    <hr class="star-primary">
                </div>
            </div>
            <div class ="row">
                <div v-for="(item,index) in portfolio" class = "col-sm-6 portfolio-item">
                    <a v-on:click="openModal(index)" class = "portfolio-link">
                    <div class = "caption">
                        <div class = "caption-content">
                            <i class="fa fa-search-plus fa-3x"></i>
                        </div>
                    </div>
                    <img v-bind:src = "item.img" class="img-responsive img-center">
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="success" id="about">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h2>About</h2>
                    <hr class="star-light">
                </div>
            </div>
            <div class="row">
                <div class="col-lg-4 col-lg-offset-2">
                    <p>I love to code. Their is something about making something new that is deeply satisfying about the process. For that reason I invest time every week into learning on my own. I'm also a team player. I like to work with people. In fact I do my best work in a team environment. If you're looking for someone who loves to code, who is good with people, and who is willing to learn, I'm your guy.</p>

                </div>
                <div class="col-lg-4">
                    <p>Personally, nothing is quite as thrilling as a good game of Ultimate Frisbee, a hobby I hope to enjoy one day with my two children when they get a little bigger. I also enjoy a good game of Starcraft with my friends from High School, when we manage to get together. I also enjoy movies, hiking, camping, and any other team activity.</p>

                </div>
                <div class="col-lg-8 col-lg-offset-2 text-center">
                    <a href="src/assets/Resume.pdf" class="btn btn-lg btn-outline">
                        <i class="fa fa-download"></i>Resume
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h2>Contact Me</h2>
                    <hr class="star-primary">
                </div>
            </div>
            <div class="row">
                <div class="col-lg-8 col-lg-offset-2">
                    <!-- To configure the contact form email address, go to mail/contact_me.php and update the email address in the PHP file on line 19. -->
                    <!-- The form should work on most web servers, but if the form is not working you may need to configure your web server differently. -->
                    <form name="sentMessage" id="contactForm" novalidate>
                        <div class="row control-group">
                            <div class="form-group col-xs-12 floating-label-form-group controls">
                                <label for="name">Name</label>
                                <input type="text" class="form-control" placeholder="Name" id="name" v-model = "msg.name" required data-validation-required-message="Please enter your name.">
                                <p class="help-block text-danger"></p>
                            </div>
                        </div>
                        <div class="row control-group">
                            <div class="form-group col-xs-12 floating-label-form-group controls">
                                <label for="email">Email Address</label>
                                <input type="email" class="form-control" placeholder="Email Address" v-model = "msg.email" id="email" required data-validation-required-message="Please enter your email address.">
                                <p class="help-block text-danger"></p>
                            </div>
                        </div>
                        <div class="row control-group">
                            <div class="form-group col-xs-12 floating-label-form-group controls">
                                <label for="phone">Phone Number</label>
                                <input type="tel" class="form-control" placeholder="Phone Number" v-model = "msg.phone" id="phone" required data-validation-required-message="Please enter your phone number.">
                                <p class="help-block text-danger"></p>
                            </div>
                        </div>
                        <div class="row control-group">
                            <div class="form-group col-xs-12 floating-label-form-group controls">
                                <label for="message">Message</label>
                                <textarea rows="5" class="form-control" placeholder="Message" v-model = "msg.msg" id="message" required data-validation-required-message="Please enter a message."></textarea>
                                <p class="help-block text-danger"></p>
                            </div>
                        </div>
                        <br>
                        <div id="success"></div>
                        <div class="row">
                            <div class="form-group col-xs-12">
                                <button v-on:click="contact()" class="btn btn-success btn-lg">Send</button>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="text-center">
        <div class="footer-above">
            <div class="container">
                <div class="row">
                    <div class="footer-col col-md-6">
                        <h3>Location</h3>
                        <p>Spanish  Fork, Utah</p>
                    </div>
                    <div class="footer-col col-md-6">
                        <h3>Around the Web</h3>
                        <ul class="list-inline">
                            <li>
                                <a href="https://www.facebook.com/jordan.braginton" class="btn-social btn-outline"><span class="sr-only">Facebook</span><i class="fa fa-fw fa-facebook"></i></a>
                            </li>
                            <li>
                                <a href="https://www.linkedin.com/in/jordan-braginton-2a28108b/" class="btn-social btn-outline"><span class="sr-only">Linked In</span><i class="fa fa-fw fa-linkedin"></i></a>
                            </li>
                        </ul>
                    </div>
                    <!-- <div class="footer-col col-md-4">
                        <h3>Skills</h3>
                        <p>J</a>.</p>
                    </div> -->
                </div>
            </div>
        </div>
        <!-- <div class="footer-below">
            <div class="container">
                <div class="row">
                    <div class="col-lg-12">
                        Copyright &copy; Your Website 2016
                    </div>
                </div>
            </div>
        </div> -->
    </footer>

    <!-- Scroll to Top Button (Only visible on small and extra-small screen sizes) -->
    <div class="scroll-top page-scroll hidden-sm hidden-xs hidden-lg hidden-md">
        <a class="btn btn-primary" href="#page-top">
            <i class="fa fa-chevron-up"></i>
        </a>
    </div>

    <!-- Portfolio Modals -->

        <modal v-if="mOpen" @close = "mOpen = false">
            <h3 slot = "header"><img class = "small" :src = "portfolioItem.img"><br>{{portfolioItem.title}}
                <br><small>{{portfolioItem.dates}}</small>
            </h3>
          
            <div slot="body" class = "modalInner">

                <p>{{portfolioItem.desc}}</p>
                <p style = "font-size:1em;">Projects</p>
                    <div v-for = "project in portfolioItem.projects" class = "proj">
                        <a v-if="project.href != ''" class = "" :href = "project.ref">{{project.name}}</a>
                        <span v-else>{{project.name}}</span>
                    </div>
            </div>
        </modal>


  </div>
</template>

<script>
export default {
  name: 'app',
  methods:{
      openModal:function(i){
          this.portfolioItem = this.portfolio[i] 
          this.mOpen = true;
      },
      contact:function(){
        let msg = this.msg;
        $.ajax({
            type:"POST",
            url:"https://localhost:9000/contact",
            data:msg,
            response:function(res){
                console.log(res);
            }

        })  
          
      }
  },
  data () {
    return {
      msg: {
          name:"",
          email:"",
          phone:"",
          msg:""
      },
      mOpen:false,

      portfolioItem:{
              title:"Dev Mountain",
              img:"src/img/portfolio/devm2.png",
              desc:"g",
              dates:"", 
              projects:[],
              type:""},
      portfolio:[
          {
              title:"Dev Mountain",
              img:"src/img/portfolio/devm2.png",
              desc:`This is where I learned to love coding! Their was a lot of good energy here and while it
               definately is not a comprehensive program, it gave me the tools and confidence to get to where I 
               am today. We started with html and css and moved all the way into angular and node. While many of 
               these projects are very simple they were highly educational.`,
              dates:"Spring 2014", 
              projects:[
                  {name:"TMNT", ref : "https://github.com/bragtown/TeamTMNT"},
                  {name:'RTFM',ref:'https://github.com/bragtown/RTFM'},
                  {name:'Worktalk',ref:'https://github.com/bragtown/worktalk'},
                  {name:'Codepen Login clone',ref:'https://github.com/bragtown/codepen-loginsignup-clone'},
                  {name:'Angular-friends',ref:'https://github.com/bragtown/angular-friends'},
                  {name:'Quiver-Invoice',ref:'https://github.com/bragtown/quiver-invoice'},
                  {name:'Twitter-Clone',ref:'https://github.com/bragtown/twitter-clone'},
                  {name:'Debuggin Exercises',ref:'https://github.com/bragtown/debugging-exercises'},
                  {name:'Svbtl',ref:'https://github.com/bragtown/svbtle'},
                  {name:'Wikimedia-layout',ref:'https://github.com/bragtown/wikimedia-layout'},
                  {name:'Seek',ref:'https://github.com/bragtown/seek'},
                  {name:'Lawyer Scoreboard',ref:'https://github.com/bragtown/lawyer-scoreboard'},
                  {name:'Soapy',ref:'https://github.com/bragtown/soapy'}
                ],
              type:""
          },
          {
              title:"Utah Valley University",
              img:"src/img/portfolio/uvu.png",
              desc:`The UVU Computer Science department provides a broad range of programs that support students 
              in many areas. Faculty members in the CS department represent years of experience in various related 
              occupations and their academic credentials span an impressive variety of specializations. All members
               of the CS department work together to provide an educational experience designed to prepare graduates
                with the knowledge and skills required to succeed in the dynamic fields related to computer science.`,
              dates:"Current",
              projects:[
                  {name:`Virtual Machine and Compiler`, ref:``},
                  {name:`Love Calculator - Computer Architecture`, ref:``},
                  {name:`Adventure Game - Java`, ref:``},
                  {name:`Alpine Animal Ark - Web II`, ref:``},
                  {name:`Chess - Web I`, ref:``},
                  {name:`Virtual Machine - Software Engineering`, ref:``},
                  {name:`Data Structures`, ref:``},
                  {name:`Data Base Management`, ref:``},
                  {name:`Discrete Mathmatics`, ref:``}
              ],
              type:""
          },
          {
              title:"Ascent Companies",
              img:"src/img/portfolio/rca.png",
              desc:`I work for Ascent as the database manager, but I also get to play around with ANYTHING related
               to data, including the user interface. I help to track`,
              dates:"Current",
              projects:[
                  {name:`Mobile Lead Management`, ref:``},
                  {name:`Fleet Management`, ref:``},
                  {name:`Flag Board`, ref:``},
                  {name:`Snap Board`, ref:``},
                  {name:`Clinical Dashboard`, ref:``},
                  {name:`Call Center`, ref:``},
                  {name:`RSS Graphs`, ref:``},
                  {name:`Parent Portals`, ref:``},
                  {name:`Application`, ref:``},
                  {name:`Student Portal`, ref:``},
                  {name:`Group Therapy Calendar`, ref:``},
                  {name:`Treatment Hub`, ref:``}
              ],
              type:""
          },
          {
              title:"Personal Development",
              img:"src/img/portfolio/personal.jpg",
              desc:`The real trick to coding is finding time to do it on my own and for myself. Making things for me 
              is one of my favorite things to do, as infrequently as I get to do it.`,
              dates:"Current",
              projects:[
                  {name:`Cardgame`, ref:``},
                  {name:`Snapshot Notes`, ref:``},
                  {name:`Sacrament Program`, ref:``},
                  {name:`YM Attendance`, ref:``},
                  {name:`Blog`, ref:``},
                  {name:`Resume`, ref:``}
              ],
              type:""
          },
      ]
    }
  }
}
</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.proj{
    display: inline;
    padding: 7px;
}
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
.small{
    height: auto;
    width: 8em;
}
</style>
