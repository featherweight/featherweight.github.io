---
permalink: /consultants/
layout:    page
title:     Consultants
menu:      Consultants
---

<div class="ui text container">

  <p>Featherweight is built with good will and generosity, yet its development remains primarily a business pursuit. Consider hiring these world-class systems architects build your business and products.</p>
  <p>We know Featherweight inside and out, and we can work with you and your team to create systems beyond what even seems possible.</p>
  <div class="ui horizontal section divider">
    <span>Loaded in random order</span>
  </div>
  
  <div id="consultant_grid" class="ui three cards">
        <div class="ui card transition hidden">
          <div class="blurring dimmable image">
            <div class="ui dimmer">
              <div class="content">
                <div class="center">
                  <div class="ui inverted button">Add Friend</div>
                </div>
              </div>
            </div>
            <img src="../img/consultants/person.png">
          </div>
          <div class="content">
            <a class="header">Jack R. Dunaway 1</a>
            <div class="meta">
              <span class="date">Austin, TX, USA</span>
            </div>
          </div>
          <ul class="">
            <li class="">Architect Retainer (80-hr min)</li>
            <li class="">Design Review ($2k USD min)</li>
          </ul>
          <div class="extra content">
            <a><i class="users icon"></i>2 Members</a>
          </div>
        </div>
        
        
        <div class="ui card transition">
          <div class="blurring dimmable image hidden">
            <div class="ui dimmer">
              <div class="content">
                <div class="center">
                  <div class="ui inverted button">Add Friend</div>
                </div>
              </div>
            </div>
            <img src="../img/consultants/person.png">
          </div>
          <div class="content">
            <a class="header">Jim Bodecker</a>
            <div class="meta">
              <span class="date">Anytown, MO, USA</span>
            </div>
          </div>
          <ul class="">
            <li class="">Architect Retainer (80-hr min)</li>
            <li class="">Design Review ($2k USD min)</li>
          </ul>
          <div class="extra content">
            <a><i class="users icon"></i>Another Company LLC</a>
          </div>
        </div>
        
        <div class="ui card transition">
          <div class="blurring dimmable image hidden">
            <div class="ui dimmer">
              <div class="content">
                <div class="center">
                  <div class="ui inverted button">Add Friend</div>
                </div>
              </div>
            </div>
            <img src="../img/consultants/person.png">
          </div>
          <div class="content">
            <a class="header">Francesca Mendoza</a>
            <div class="meta">
              <span class="date">Bristol, UK</span>
            </div>
          </div>
          <ul class="">
            <li class="">Architect Retainer (80-hr min)</li>
            <li class="">Design Review ($2k USD min)</li>
          </ul>
          <div class="extra content">
            <a><i class="users icon"></i>tinybiz</a>
          </div>
        </div>
        
        <div class="ui card transition">
          <div class="blurring dimmable image hidden">
            <div class="ui dimmer">
              <div class="content">
                <div class="center">
                  <div class="ui inverted button">Add Friend</div>
                </div>
              </div>
            </div>
            <img src="../img/consultants/person.png">
          </div>
          <div class="content">
            <a class="header">Nellie Bryant</a>
            <div class="meta">
              <span class="date">Munich, Germany</span>
            </div>
          </div>
          <ul class="">
            <li class="">Architect Retainer (80-hr min)</li>
            <li class="">Design Review ($2k USD min)</li>
          </ul>
          <div class="extra content">
            <a><i class="users icon"></i>Big Name Long Words Incorporated</a>
          </div>
        </div>
  </div>

  <div class="ui center aligned vertical segment">
    <button id="button_randomize" class="ui compact small button" href="/consultants/"><i class="refresh icon"></i>Shuffle</button>
  </div>
  
  <div class="ui hidden section divider"></div>
  
  <div class="ui segment">
    <form action="//formspree.io/inquiries@featherweight.io" method="POST" class="ui form">
      <div class="two fields">
        <div class="field">
          <label>Name</label>
          <input type="text" name="Name" placeholder="Your name">
        </div>
        <div class="field">
          <label>Email</label>
          <input type="email" name="_replyto" placeholder="Email address">
        </div>
      </div>
      <div class="field">
        <label>Message</label>
        <textarea name="Message" placeholder="What's on your mind?" rows="2"></textarea>
      </div>
      <div class="inline field">
        <div class="ui checkbox">
          <input type="checkbox" tabindex="0" class="hidden">
          <label>I agree to the terms and conditions</label>
        </div>
      </div>
      <input type="hidden" name="_subject" value="Featherweight Consulting Inquiry">
      <input type="hidden" name="_next" value="/#thank-you">
      <input type="text" name="_gotcha" style="display:none">
      <input type="submit" value="Send" class="ui submit button">
    </form>
  </div>
</div>

<div class="ui hidden section divider"></div>

<script type="text/javascript">
  var consultant_grid = document.getElementById("consultant_grid");
  var cards = consultant_grid.children;
  var frag = document.createDocumentFragment();
  
  function randomize_grid() {
    var element;
    var i = 0;
    
    while (cards.length) {
      element = cards[Math.floor(Math.random() * cards.length)];
      element.classList.add("hidden");
      element.classList.remove("visible");
      frag.appendChild(element);
      i++;
    }
    consultant_grid.appendChild(frag);
    
    $('#consultant_grid .card').transition({
        animation : 'scale',
        interval  : 200
      });
  }
  
  document.addEventListener('DOMContentLoaded', function() {
    document.getElementById("button_randomize").addEventListener('click', randomize_grid);
    randomize_grid();
  }, false);

</script>