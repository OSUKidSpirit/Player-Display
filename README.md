# Player Display

The Player Display automatically resizes the YouTube videos to 16:9 ratio for KidSpirit videos.

The code repo is available on GitHub at [https://github.com/OSUKidSpirit/Player-Display](https://github.com/OSUKidSpirit/Player-Display)

## Usage

To use the Player Display, simply add `class="anthonian-player"` to the YouTube embed code and change the `width=""` to `width="100%"` like this:

```html
<iframe class="anthonian-player" width="100%" height="315" src="{{ URL }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

Feel free to add multiple videos using the same method, for example:

```html
<iframe class="anthonian-player" width="100%" height="315" src="{{ URL }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<h3>Some random heading</h3>
<iframe class="anthonian-player" width="100%" height="315" src="{{ URL }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<p>Some random texts</p>
<iframe class="anthonian-player" width="100%" height="315" src="{{ URL }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe class="anthonian-player" width="100%" height="315" src="{{ URL }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

Then place the following JavaScript at the very bottom of the page, add a new section if needed. DO NOT add multiple JavaScript on the same page, one will work for all videos.

```html
<script>
  var player = document.getElementsByClassName("anthonian-player");
  window.addEventListener("load", playerSizer);
  window.addEventListener("resize", playerSizer);
  function playerSizer() {
    for (var i = 0; i < player.length; i++) {
      let width = player[i].offsetWidth;
      player[i].style.height = (width * 0.5625) + "px";
    }
  }
</script>
```
