<!---
Copyright 2015 The AMP HTML Authors. All Rights Reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS-IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

### <a name=”amp-audio”></a> `amp-audio`

A replacement for the HTML5 `audio` tag. Like all embedded external resources in a AMP file, the audio is lazily loaded only when the `amp-audio` element is in or near the viewport.

The `amp-audio` component is only to be used for direct HTML5 audio file embeds.

#### Behavior

The `amp-audio` component loads the audio resource specified by its `src` attribute lazily, at a time determined by the runtime. It can be controlled much the same way as a standard HTML5 `audio` tag.

The `amp-audio` component HTML accepts up to three unique types of HTML nodes as children - `source` tags, a placeholder for before the audio starts, and a fallback if the browser doesn’t support HTML5 audio.

`source` tag children can be used in the same way as the standard `audio` tag, to specify different source files to play.

One or zero immediate child nodes can have the `placeholder` attribute. If present, this node and its children form a placeholder that will display instead of the audio. A click or tap anywhere inside of the `amp-audio` container will replace the placeholder with the audio itself.

One or zero immediate child nodes can have the `fallback` attribute. If present, this node and its children form the content that will be displayed if HTML5 audio is not supported on the user’s browser.

For example:
```html
<amp-audio width=400 height=300 src=”https://yourhost.com/audios/myaudio.mp3”>
    <div fallback>
        <p>Your browser doesn’t support HTML5 audio</p>
    </div>
    <source type="audio/mpeg" src="foo.mp3">
    <source type="audio/ogg" src="foo.ogg">
</amp-audio>
```
#### Attributes

**autoplay**

The `autoplay` attribute allows the author to specify when - if ever - the animated image will autoplay.

The presence of the attribute alone implies that the animated image will always autoplay. The author may specify values to limit when the animations will autoplay. Allowable values are `desktop`, `tablet`, or `mobile`, with multiple values separated by a space. The runtime makes a best-guess approximation to the device type to apply this value.

**loop**

If present, will automatically loop the audio back to the start upon reaching the end.

**muted**

If present, will mute the audio by default.
