---
layout: single
title:  "RubyKaigi 2025 – Migrating RBS's parser to pure C"
excerpt: >-
  My first full-length conference talk, in which I share how we transformed the RBS parser into a pure C library, that can be embedded into any system, even without Ruby!
date: 2025-04-17 16:20:00 +0900
last_modified_at: 2025-05-31 20:40:00 -0500
permalink: /RubyKaigi2025
---

I had the great pleasure to present my team's work at [RubyKaigi 2025](https://rubykaigi.org/2025), in Matsuyama, Japan. This was my first ever conference talk, at the largest international conference for the Ruby programming language, no less!

## Video

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/AgY9tm4sBbc?start=4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<br>

Nailed my introduction. 😄

## Slides

Here is the [original Keynote file](/resources/RubyKaigi2025/RBS-talk.key.zip) with animations, and a more universal [PDF export](/resources/RubyKaigi2025/RBS-talk-slides.pdf).

## Summary

**From C extension to pure C: Migrating RBS**

Learn how we migrated [RBS](https://github.com/ruby/rbs) to remove its dependency on the Ruby VM and expose a new C API. In addition to being faster and more memory-efficient, it’s now more portable: tools like Prism, Sorbet, JRuby and TruffleRuby will be able to use RBS directly. Type checkers like Steep and Sorbet will now be able to parse multiple RBS files in parallel, unconstrained by the GVL.

The Ruby VM offers many luxuries that can help ease C extension development, such as garbage collection, exceptions, and the many built-in data structures like `Array` and `Hash`. Unfortunately, to be maximally portable and multi-threaded, some C extensions like RBS and Prism will need to forego these conveniences. We’ll show techniques for replicating them in pure C.

Join us to explore advanced techniques in writing C extensions and see how this universal RBS parser paves the way for improved tooling and collaboration in the Ruby ecosystem.

## Further reading

* See the Sorbet documentation page on [RSB support](https://sorbet.org/docs/rbs-support).
* Two related RubyKaigi 2025 talks from my team:
  * [Vinicius Stock](https://vinistock.com/) presented [Embracing Ruby magic: Statically analyzing DSLs](https://rubykaigi.org/2025/presentations/vinistock.html).
  * [Alexandre Terrasa](https://github.com/Morriar) presented [Inline RBS comments for seamless type checking with Sorbet](https://rubykaigi.org/2025/presentations/Morriar.html).
* The [huge PR](https://github.com/ruby/rbs/pull/2398) that landed our changes.
