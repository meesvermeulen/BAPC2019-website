---
layout: default
menutitle: Home
title: no
order: 0
menu: main
---

<div class="countdown">
    <div class="timer"><b class="countdownvalue" id="days"></b><span class="word">days</span></div>
    <div class="timer"><b class="countdownvalue" id="hours"></b><span class="word">hours</span></div>
    <div class="timer"><b class="countdownvalue" id="minutes"></b><span class="word">minutes</span></div>
    <div class="timer"><b class="countdownvalue" id="seconds"></b><span class="word">seconds</span></div>
</div>

<script src="/assets/js/countdown.js"></script>
<script>
    $(document).ready(function() {
        var target_date = new Date(2019, 9, 19, 9, 0, 0);
        var count = new Countdown(target_date, new Date());

        count.countdown(function(time) {
            if (time.days < 10) {
                $("#days").html("0" + time.days);
            } else {
                $("#days").html(time.days);
            }
            if (time.hours < 10) {
                $("#hours").html("0" + time.hours);
            } else {
                $("#hours").html(time.hours);
            }
            if (time.minutes < 10) {
                $("#minutes").html("0" + time.minutes);
            } else {
                $("#minutes").html(time.minutes);
            }
            if (time.seconds < 10) {
                $("#seconds").html("0" + time.seconds);
            } else {
                $("#seconds").html(time.seconds);
            }
        });
    });
</script>
<style>
    .countdown {
        display: flex;
        justify-content: space-around;
        margin-bottom: 12px;
    }
    @media (max-width: 380px) {
        .countdown {
            display: none;
        }
    }
    .timer {
        padding: 10px;
        text-align: center;
    }
    .countdownvalue {
        display: block;
        font-size: 4rem;
        line-height: 1;
    }
    .word {
        display: block;
    }
</style>

### About the BAPC

The Benelux Algorithm Programming Contest (BAPC) is a contest in which about 50 teams from leading universities in Luxemburg,
Belgium and the Netherlands are served a series of algorithmic problems/puzzles. The goal of each team is to solve as many
puzzles as possible within the set time limit. Solutions need to be programmed out on a computer and can be submitted to a
semi-automated judging system, after which the solution is checked. The teams that have solved the most puzzles at the end
of the contest qualify for the Northwestern European Regional Contest (NWERC). In this regional competition the teams can
qualify themselves for a ticket to the International Collegiate Programming Contest (ICPC), also known as the World Finals.

The BAPC {{site.year}} will take place on <b>{{site.day}}</b> at the Radboud University in Nijmegen, The Netherlands and is co-organised by <a href='https://www.desda.org/' target="_blank">Desda</a>
and <a href='https://thalia.nu' target="_blank">Thalia</a>.

### During the contest

The scorebord will be available live during the contest [here](/results.html). A livestream of the award ceremony will be available on the homepage after the contest itself has ended.

### Semi-live and live contest for non-participants

Furthermore, there will be a semi-live contest hosted by one of the DOMjudge developers at [contest.domjudge.org](http://contest.domjudge.org/). Anyone can self-register already, but the contest will start 30 minutes after the live contest has started. For people attending locally, there will be the possibility to participate on the live DOMjudge server at the same time as the participants.

### Previous contests

<p id="previousContests">
    Websites of the previous years are available: {% assign previous = site.year | minus : 1 %}
    {% for i in (2010..previous) %}
        <a href="http://{{i}}.bapc.eu/" target="_blank">{{i}}</a>{% unless forloop.last %},{% endunless %}{% endfor %}.
</p>
