---
layout: post
title: "The two-wheeled unicorn"
date: 2026-05-31 20:00:00 +0000
math: true
---

It is a known fact of life that anyone bitten by the motorcycling bug will eventually waste an inordinate amount of time searching for _the bike_. That one machine that satisfies every desire and fulfils every practical need. The two-wheeled Swiss Army knife. The ride to end all rides. But see, this is impossible. Not impossible as a figure of speech. Mathematically impossible. I am not saying this. _Science_ is.

The fantasy is always the same. One bike that can do everything well. Comfortable enough to cross countries, fast enough to make the long way home an actual choice, and cheap enough that the bank does not start sending handwritten letters. A bike for touring, commuting, errands, holidays, bad weather, good weather, and the mysterious category known as "just popping out for twenty minutes", which no motorcyclist has ever completed in under two hours.

Manufacturers know this fantasy well. They sell it constantly. Every few months a new machine appears with panniers, riding modes, a tall screen, red brake calipers, a ludicrous "starting from" price, and a clean, crisp press photo taken somewhere mountainous. The implication is clear: this time, finally, the compromise has been defeated.

It has not. The compromise has merely been pushed under the rug.

In computer science (motorcycle-only readers, please bear with me; it will be over soon) there is something called the CAP theorem. In its actual form, it says that a distributed data store cannot guarantee consistency and availability during a network partition. In its popular, dangerously simplified form: when conditions become hostile, something must give. In the world of business, the same principle is known as "good, fast, and cheap: choose two". Well, it turns out that the CAP theorem applies to motorcycles too: a bike may be **comfortable**, **affordable**, or **performant**. It may even be two of these. It can never, by theatrical abuse of mathematics, be all three.

This is not a moral claim. It is not even a matter of taste; mind you, taste is how we got into this mess. The point of the theorem is that each of these properties can be made precisely measurable, with only enough rounding to keep the joke alive. Let's break it down.

**Comfort** is the degree to which a bike can support a long trip without requiring a chiropractor on retainer. A comfortable bike can be used instead of a car for a long journey without sacrificing more than your love of bikes can justify. The car may still be quieter, warmer, safer, and better at carrying furniture. That is not the point. The point is that the bike has enough weather protection, luggage, range, ergonomics, and amenities that choosing it remains a reasonable option rather than an act of stubbornness.

The Comfort index is scored out of ten points:

- tall windscreen: 1 point
- additional weather protection: 1 point
- factory luggage support: 1 point
- factory luggage included: 1 point
- fuel range of at least 300 km: 1 point
- fuel range of at least 500 km: 1 point
- upright or neutral long-distance ergonomics: 1 point
- cruise control: 1 point
- top case: 1 point
- passenger backrest and armrests: 1 point

Each item is a simple boolean: one point if the bike has it, zero if it does not. The points are cumulative. A bike with more than 500 km of range also gets the 300 km point. A bike with factory luggage included may also get the luggage-support point. A pillion seat counts for nothing; even superbikes provide a small upholstered apology where a passenger might theoretically, ill-advisedly try to fit. That piece of hardware is unequivocally stating: "Do not sit on me. I am barely a seat, if at all."

Pardon the slight detour. The formula is:

<div>$$C = \dfrac{\text{comfort pts}}{5}$$</div>

If `C >= 1`, the bike is _comfortable_.

**Performance** is also quantified, with only a forgivable amount of fraud. A performant bike does not merely produce torque in spades, but has the architecture to support it. It must have enough power relative to weight, enough cornering clearance to be able to steer the bike, suspension that can keep the tyres usefully attached to the road, and brakes that can bring the whole enterprise back from optimism. Otherwise, it's a lounge chair fired from a cannon.

The Performance index is:

<div>$$P = \dfrac{hp \cdot 1000}{m \times 408} \cdot \left(\dfrac{\theta}{43}\right)^2 \cdot \dfrac{(1+s)(1+d)}{4}$$</div>

where θ is the lean angle in degrees, m is the wet weight in kilograms, and s and d are boolean values representing advanced suspension and double front discs respectively.

If `P >= 1`, the bike is _performant_.

The lean-angle factor is squared in the formula, with 43 degrees as the reference point—roughly where a performance-oriented naked or sport bike naturally sits. A comfort-focused adventure bike at 37 degrees scores 74% of the reference lean factor; a cruiser at 33 degrees scores 59%; one at 28 degrees scores 42%. Track-oriented machines, which might lean to 55 or 60 degrees, are rewarded accordingly. The reference was set here deliberately: 43 degrees is not a lean angle you reach while focused primarily on comfort or cost.

<aside class="admonition" markdown="1">
The lean angle used here is a shortcut. A principled measure would be derived from cornering physics: the minimum lean required to clear a known reference corner at a defined speed, computed from the centripetal constraint $v^2 = rg\tan\theta$. A famous hairpin at competitive-but-legal pace imposes a known geometric constraint; the lean angle at which a bike can safely meet it would be the actual threshold. The maximum achievable lean angle serves as a proxy on the reasonable assumption that a manufacturer designing for performance builds in the clearance to use it.
</aside>

The hardware modifier is multiplicative: each component independently halves the score if absent. A bike with both keeps the full score. A bike missing one loses 50%. A bike missing both loses 75%, which is the theorem's polite way of raising an eyebrow at the manufacturer's priorities. The reason the modifier exists is that their absence is rarely accidental: inverted forks and dual brakes cost money, and a manufacturer optimising for affordability will cut them first, confident that the target customer will be distracted by the colour options. A bike with a good power-to-weight ratio but no inverted forks and no dual discs is telling you something about its priorities. The index listens.

<aside class="admonition" markdown="1">
The hardware flags are themselves a shortcut. A rigorous measure would use actual stopping distance from a reference speed, and lateral load capacity from suspension data, each normalised against a defined threshold, scoring 1 if the bike meets the mark, above or below accordingly. Inverted forks and dual-disc front brakes serve as stand-ins: manufacturers who specify this hardware are signalling performance intent, and the inverse holds. A bike with a large single-disc and a quality radially-mounted caliper might stop shorter than one with dual smaller discs; the proxy cannot see this, but a measured stopping distance would.
</aside>

**Affordability** is the part where everyone starts lying to themselves. The proper measure would include tyres, servicing, fuel, insurance, tax, depreciation, accessories, finance, parking, and the domestic diplomacy required by yet another garage neighbour. Unfortunately, calculating that accurately across countries would turn this article into investigative journalism, and nobody came here to read a tax report with handlebars.

So the Affordability index uses a portable proxy: inflation-adjusted new purchase price, normalised against local GDP per capita. Second-hand bargains are not allowed, because otherwise every theorem can be defeated by a suspicious listing 300 km away with "minor electrical issue" and "'tis but a scratch" in the description.

The formula is:

<div>$$A = \dfrac{0.25 \times \text{GDP per capita}}{\text{adjusted price}}$$</div>

If `A >= 1`, the bike is _affordable_.

A bike is affordable only if its new price is no more than a quarter of local GDP per capita. A Honda SH125i clears this in Spain. A Honda SH350i clears it too, barely. A Moto Guzzi V7 is cheap compared to its BMW or Ducati equivalents, but it is _not_ a cheap bike.

Once these measurements are firmly established, the motorcycle universe sorts itself with the full authority of arithmetic and the ineffable support of huge swathes of [anecdotal data](/motorcycles/cap-data/).

The conclusion at which you, O bright reader, will surely arrive is as follows:

- A bike that is **comfortable and affordable** cannot be **performant**
- A bike that is **comfortable and performant** cannot be **affordable**
- A bike that is **performant and affordable** cannot be **comfortable**

**Comfort and performance, not affordability** is the domain of fast tourers, which also happen to be expensive: BMW RTs and K1600s, Ducati Multistradas, S1000XRs, and similar machines that can cross countries quickly while protecting the rider from most of the consequences of doing so, though not necessarily from licensing authorities. They are comfortable. They are fast. They are not cheap to buy, and the ownership experience is unlikely to be confused with public transport.

**Comfort and affordability, not performance** is where the sensible yet boring machinery lives: Honda NC750X, CB500X or NX500, Suzuki V-Strom 650, old Deauvilles, and the better maxi-scooters. These bikes can do long days without cruelty and can be bought without auctioning off anything vital. They may move well enough, but they do not defy physics.

**Performance and affordability, not comfort** is the land of excellent regrettable decisions: the Yamaha MT-07, and the lighter end of the naked and sport-bike world. These bikes are quick, sharp, entertaining, and attainable. They are also not the obvious choice for a cold, wet, luggage-heavy day, let alone touring two-up. The Triumph Trident 660 shares this spirit but sits on the wrong side of the affordability line at Spanish prices. The Suzuki SV650 and Kawasaki Ninja 650 miss from the other direction: genuinely affordable and close to the performance threshold, but their hardware specification tells the story—no inverted forks—and the formula agrees.

Of course, there are single-axis bikes. There are even zero-axis bikes out there, but we did not gather here to embarrass anyone, so they will remain unmentioned.

Luxury tourers and some heavy cruisers that look after you beautifully while treating performance and affordability as optional extras inhabit the **comfort-only** category. Small scooters and commuters, the noble machines that cost little, ask little, and deliver exactly the proportional amount of excitement and amenity one should expect, are classified as just **affordable**. Serious sport bikes and exotic machinery that prioritise speed so completely that comfort and affordability are asked to wait outside can be found in the **performance-only** category.

The interesting bit about these categories is that they are the only meaningful ones, which explains with mathematical precision why the perfect bike keeps refusing to appear. Every candidate that claims all three is quietly grading at least one axis on a curve. Comfortable _for a sport bike_. Performant _for a tourer_. Affordable _for that brand_. These are not lies, exactly. That does not make them true either.

This is why the perfect bike does not exist. Not because engineers lack imagination, or because manufacturers are lazy, or because motorcyclists are impossible to satisfy (though that last one is most likely true). It does not exist because the requirements fight each other. Comfort adds weight, volume, equipment, and cost. Performance demands power, chassis, brakes, tyres, clearance, and usually more cost. Affordability resists all of it.

So how many bikes are enough?

One bike may be enough for one purpose. A commuter does not need to be a grand tourer. A track toy does not need to care about luggage. A long-distance bike does not need to be cheap enough to leave outside a supermarket without developing a twitch. But the fantasy of one perfect bike, the machine that is comfortable, affordable, and performant at the same time, is now debunked beyond any shred of doubt.

If you need to cover all three bases, you need more than one bike, and you do not need more than two. This is not indulgence. It is compliance with mathematics. It is abiding by the laws of physics.

> Yeah, Mr. White! Yeah, science!
-- Jesse Pinkman

---

[The numbers →](/motorcycles/cap-data/)
{: .cap-appendix}
