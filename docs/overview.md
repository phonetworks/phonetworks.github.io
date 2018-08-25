---
currentMenu: home
---


<script>
function close_all() {
    document.getElementById('dCloning').style.display="none";
    document.getElementById('dEditing').style.display="none";
    document.getElementById('dBuilding').style.display="none";
    document.getElementById('dPlaying').style.display="none";
    var i = 0;
    while(i < document.getElementsByClassName('dPicker').length) {
        document.getElementsByClassName('dPicker')[i++].style.fontWeight="400";
    }
}
var first = {};
first["Cloning"] = true;
function pick(div, to_bolden) {
    close_all();
    if(first[div]==undefined||!first[div]) {
        var x = document.createElement("script");
        var data_id = document.getElementById('d'+div).getAttribute("data-id");
        x.src = "https://asciinema.org/a/"+data_id+".js";
        x.async = true;
        x.id = "asciicast-"+data_id;
        x.setAttribute("data-autoplay", true);
        x.setAttribute("data-speed", 2);
        document.getElementById('d'+div).appendChild(x);
        first[div] = true;
    }
    document.getElementById('d'+div).style.display="block";
    to_bolden.style.fontWeight="900";
}
</script>

## Meet Graph Apps 👯‍

[ <a href="#" onclick="pick('Cloning', this)" class="dPicker" style="font-weight:900;">Cloning a Recipe</a> ] &nbsp; [ <a href="#" onclick="pick('Editing', this)" class="dPicker">Editing Schema Files</a> ] &nbsp; [ <a href="#" onclick="pick('Building', this)"  class="dPicker">Building</a> ] &nbsp; [ <a href="#" onclick="pick('Playing', this)"  class="dPicker">Working with the APIs</a> ]

<div  style="display:block;" data-id="ElK47XRwn9cAwx2OZicJ5VA1N" id="dCloning">
<script type="text/javascript" src="https://asciinema.org/a/ElK47XRwn9cAwx2OZicJ5VA1N.js" id="asciicast-ElK47XRwn9cAwx2OZicJ5VA1N" data-autoplay="true" data-speed="2" async></script>
</div>

<div id="dEditing" data-id="jyHXB6sCH1c2syvyXUNwlmUlU" style="display:none;">
</div>

<div id="dBuilding" data-id="YTCxY878nCDCDBMBCZnEaC3z5" style="display:none;">
</div>

<div id="dPlaying" data-id="8aTCBtvoPhjSEujGxl3S6NObP" style="display:none;">
</div>

Phở Networks is an open source, **infinitely scalable**, event-driven, **extensible** stack that gives you solid foundations to build **social-enabled apps**.

When developing a social-enabled app, you have four options to base it off:

Foundation          | Maturity | Scalability  | Convenience
----------------    | ------   | --------     | --------------------
Relational Database |   10     |     3        |   6
NoSQL               |   8      |     8*       |   6
Graph Database      |   6      |     3        |   4
Phở                 |   3      |     10       |   10

\* there is no major SN that uses mongodb but they all use redis and memcache

Social-enabled apps consist of graphs, and graphs are by definition difficult to break down into shards using relational databases, therefore it is extremely costly to scale a fast-growing social-enabled app. 

Built with portability and scale-out in mind, Phở Networks apps can run on web, desktop, mobile, IoT (internet of things) & embedded platforms, and serve just a handful number of users or billions using open source software and commodity hardware.

## Use Cases 🤔

What is a social-enabled app? Here are some examples:

* [A blog or news web site (with different actor models such as readers, authors, editors, contributors).](http://techcrunch.com)
* [A personal/business web site with some level of interactivity such as page comments and subscription for updates.]()
* [A macro social network like Facebook, instagram and Twitter.](http://facebook.com)
* [A wiki for the game World of Warcraft.](http://wowwiki.wikia.com/wiki/Portal:Main)
* [A micro social network like a Yahoo Group that connects stock Chevrolet and GMC truck fans in the US.](https://groups.yahoo.com/neo/groups/old-chevy-truck/info)
* [A meetup that connects Python developers in Istanbul, Turkey.](https://www.meetup.com/python-istanbul/events/238314057/)
* [A mobile health/fitness app  that ranks your activity and calorie intake amongst your friends.](http://fitbit.com)
* [A mobile game that ranks your activity/score among your friends who play the same game.](http://www.kiloo.com/games/subway-surfers/)
* [A multi-player console game that matches you with other gamers in real-time.](https://www.halowaypoint.com/en-us)
* An IoT camera attached to your car plate, monitors other cars around, forms a real-time traffic graph and alerts you with commute potentials. (💡)

The applications of social-enabled apps are limitless. The bottomline is that any app that touches humans and help them interact are social-enabled by definition.

## Scalability 💪

While designing Phở Networks, our aim was to build a truly infinitely scalable open source fully extensible social backend. The biggest challenge was database. Today's popular databases such as MySQL are hard to maintain with growing traffic and millions of daily active users. The answer to these problems are (a) to shard your data (b) to switch to a NoSQL solution. Although sharding data is tedious and expensive, and NoSQL solutions are notoriously yet to standardize and stabilize. In response, inspired by FriendFeed founder Bret Taylor's [schema-less MySQL blog post](http://backchannel.org/blog/friendfeed-schemaless-mysql), we chose to create a stack that would be built upon stable technologies and use atomic methods to establish a horizontally scalable platform to handle any workload.

At Phở, our default choice of stable keeper of truth has been Redis. Although this and all of our choices can be adapted to your platform of choice using custom adapters. For indexing, we use ElasticSearch. For event-driven messaging, we use ZeroMQ. The platform itself is therefore clusterable to an endless number of machines using round-robin DNS and high-availability solutions that continuously listen for service heartbeats.

While this is too many open source technologies to digest, we've made it easy for you to get started via Vagrant and docker images.

## Theory 🤓

Pho-Kernel is a first of its kind backend. It is not a database but it is closely coupled with Redis, a proven distributed persistable in-memory storage service. Moreover, Phở stack gives you a familiar programming interface for graph-type relationship models that are in heavy use with social-enabled apps.

![Architecture](https://github.com/phonetworks/pho-lib-graph/raw/master/.github/lib-graph-components.png "Pho LibGraph Architecture")

Phở introduces GAO to model social graphs. Nodes and Edges are atomic entities of any graph. In the GAO model, the atomic nodes are:

* Graph
* Actor
* Object

Phở Networks allows you to extend  these abstract entities with your own, and create a new social network, or use one of our existing [recipes](https://github.com/pho-recipes) to replicate well-known solutions for your own domain-specific community needs.


## License 💩

MIT, see [LICENSE](https://github.com/phonetworks/pho-framework/blob/master/LICENSE)





