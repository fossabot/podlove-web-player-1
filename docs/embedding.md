---
layout: page
title: Embedding
navigation: 2
---

# Embedding

<p id="example" class="section"></p>
<script src="{{ 'embed.js' | relative_url }}"></script>
<script>
    podlovePlayer('#example', './fixtures/example.json');
</script>

## Signature
```javascript
*   Podlove Player Factory
*   @param {string, dom node}   selector        - CSS selector or dom node
*   @param {string, object}     configuration   - Path to JSON config or configuration object
*   @returns {Promise}          store           - Promise returning a redux store
*/
podlovePlayer(selector, configuration)
```

- Selector can be a css selector or a dom node reference
- An iframe as the canvas is injected into the reference, encapsulating the player
- Configuration can be provided as a meta object or an url to the configuration json file
- Canvas width can be defined by the template
- Canvas height is adapted to players height


Using a selector that matches multiple elements the player will be rendered in the first matching element.
The _podlovePlayer_ returns a promise with a redux store as a result that can be used to change the player state from outside.

### Example Embedding with JSON File

```html
<div id="example"></div>
<script src="embed.js"></script>
<script>
    podlovePlayer('#example', './fixtures/example.json');
</script>
```

### Example Embedding with Meta Object

```html
<div id="example"></div>
<script src="embed.js"></script>
<script>
    podlovePlayer('#example', {
        title: 'FS171 Invasion!',
        subtitle: 'LAN Planung - Kalender - Bingo - Wikipedia - Akkukalibration - Alte iPads und iPods - Find My Friends - iPhone Music Player - Apple Watch - Kommandozeile - Star Wars - Dante - Internet of Things Security - VPN',
        summary: 'Wir haben eine wie wir finden abwechslungsreiche Sendung produziert, die wir Euch wie immer mit Freude bereitstellen. Während die Live-Hörer Freak-Show-Bingo spielen, greifen wir das Wikipedia-Thema der letzten Sendung auf und liefern auch noch weitere Aspekte des optimalen Star-Wars-Medienkonsums frei Haus. Dazu viel Nerderei rund um die Kommandozeile, eine Einschätzung der Perspektive der Apple Watch, ein Rant über die mangelhafte Security  im Internet of Things (and Buildings) und allerlei anderer Kram.  Roddi setzt dieses Mal aus, sonst Vollbesetzung.',
        publicationDate: '2016-02-11T03:13:55+00:00',
        poster: 'https://freakshow.fm/wp-content/cache/podlove/04/662a9d4edcf77ea2abe3c74681f509/freak-show_200x200.jpg',
        show: {
            title: 'Freak Show',
            subtitle: 'Menschen! Technik! Sensationen!',
            summary: 'Die muntere Talk Show um Leben mit Technik, das Netz und Technikkultur. Bisweilen Apple-lastig aber selten einseitig. Wir leben und lieben Technologie und reden darüber. Mit Tim, hukl, roddi, Clemens und Denis. Freak Show hieß irgendwann mal mobileMacs.',
            poster: 'https://freakshow.fm/wp-content/cache/podlove/04/662a9d4edcf77ea2abe3c74681f509/freak-show_200x200.jpg',
            url: 'https://freakshow.fm'
        },
        duration: '04:15:32',
        chapters: [
            { start:"00:00:00", title: 'Intro'},
            { start:"00:01:39", title: 'Begrüßung'},
            { start:"00:04:58", title: 'IETF Meeting Netzwerk'},
            { start:"00:18:37", title: 'Kalender'},
            { start:"00:33:40", title: 'Freak Show Bingo'},
            { start:"00:35:37", title: 'Wikipedia'},
            { start:"01:17:26", title: 'iPhone Akkukalibration'},
            { start:"01:24:55", title: 'Alte iPads und iPod touches'},
            { start:"01:31:02", title: 'Find My Friends'},
            { start:"01:41:46", title: 'iPhone Music Player'},
            { start:"01:56:13", title: 'Apple Watch'},
            { start:"02:11:51", title: 'Kommandozeile: System Appreciation'},
            { start:"02:23:10", title: 'Sound und Design für Games'},
            { start:"02:24:59", title: 'Kommandozeile: Remote Deployment'},
            { start:"02:32:37", title: 'Kommandozeile: Man Pages'},
            { start:"02:44:31", title: 'Kommandozeile: screen vs. tmux'},
            { start:"02:58:02", title: 'Star Wars: Machete Order & Phantom Edit'},
            { start:"03:20:05", title: 'Kopfhörer-Ersatzteile'},
            { start:"03:23:39", title: 'Dante'},
            { start:"03:38:03", title: 'Dante Via'},
            { start:"03:45:33", title: 'Internet of Things Security'},
            { start:"03:56:11", title: 'That One Privacy Guy\'s VPN Comparison Chart'},
            { start:"04:10:00", title: 'Ausklang'}
        ],
        audio: [
            'http://freakshow.fm/podlove/file/4468/s/download/c/select-show/fs171-invasion.m4a',
            'http://freakshow.fm/podlove/file/4467/s/download/c/select-show/fs171-invasion.mp3',
            'http://freakshow.fm/podlove/file/4466/s/download/c/select-show/fs171-invasion.oga',
            'http://freakshow.fm/podlove/file/4465/s/download/c/select-show/fs171-invasion.opus'
        ],
        reference: {
            config: '//podlove-player.surge.sh/fixtures/example.json',
            share: '//podlove-player.surge.sh/share'
        }
    });
</script>
```