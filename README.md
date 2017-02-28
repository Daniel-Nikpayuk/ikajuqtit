ikajuqtit
=========

The specification for a mathematically oriented programming language.

### **Why?**

What will this language offer that others do not? How is it an improvement upon other languages?

1. **Efficiency**: I raised myself on C++ and prefer its level of run-time efficiency, but I also
know its weaknesses, notably its ad-hoc type system achieved through template meta-programming
and its slow development cycle.  To this end I prefer the wisdoms of theoretical type systems
achieved by languages like Haskell. I'm not trying to say this is *C++ done right* because I'm
perfectly willing to let go of its traditions, but I must admit how much it has influenced this
language as well.

2. **Expressivity**: For all they're worth, Haskell and others I also find lacking. For as
expressive as they are, they are also incremental in many ways to languages that have come before,
and so inherit some of their expressive and design limitations. I'm an artist and designer at heart,
as a mathematician my favorite branch is Topology, not because of its beautiful theoretical results,
but because of its elegant expressive language of open sets, and how you can use those to model
and access so many patterns. For expressive as functional languages are, they're still not
expressive enough for me and I know I can do better.

   > To this end, the most radical departures from existing languages are as follows:

   > **Typology**: I Conceptualize the idea of *type* differently. I aim for the same level
     of deductive type system rigour as Haskell et al. but believe this can be achieved while
     still maintaining C++ level of efficiency and even still improved expressivity. My main
     idea is to modularize type from variable.

   > In imperative languages such as C++ for example you declare a variable and assign it a permanent
     type there and then, never being able to change.  There is a small amount of flexibility in
     that you can coerce your type, but it has to be coerced to something inherently similar.
     This is not modular design, and I don't see any real reason for such a restriction.

   > In functional languages such as Haskell because you try to avoid the assignment operator,
     variables are in fact conceptualized differently, they're more like "one time use" names,
     but otherwise they are still permenantly assigned types the way imperative languages are.

   > In qanik, for now you can view variables as being untyped, but rather the values they
     store are types themselves. I go even further than that though: For example let's say
     you have a number such as '14', in qanik it doesn't have a type, it is a type, meaning
     you can assign it to a variable as type information.

   > **Structurality**: In functional languages with first class functions it can be shown there's
     a duality between structure and function---meaning you can not only define a function as
     a structural implementation, you could in theory define a structure as a functional implementation.
     In qanik you have the ability to view function definitions themselves as dynamic data structures
     which can be altered the way data structures would be.

   > In C++ and Haskell, the grammar to declare/define functions is still too limiting in their expressivity.
     In qanik one views code structurally (as data structures), and so it makes sense to be able to declare
     parts of functions, and later on combine them to become full meaningful functions. If enough info is
     present at compile time to determine a complete function, then the function is built there and then
     losing nothing in efficiency or optimization.

   > To help explain this further: Extending upon the modular typology above, what then is the
     purpose of a variable? In qanik I view it as a sort of filter, where you have a filter
     algebra to form more complex filters which end up becoming untyped data structures.

   > The idea then is that you can mutably assign type info to filters, not just variables,
     meaning you can have a complex filter (as data structure) and assign it variable type info.
     If you can filter and manipulate data as structures, why not filter and manipulate functions
     as structures too?

3. **Translation**: This builds upon expressivity and comes from my influence as a mathematician
   who has manipulated many many formulas and identities.

At the heart of this is *translation*, and in particular translation of data structures. Again, this is a very
mathematical way of thinking. In math you manipulate formulas and identities, changing structure but not content.

The following offers the philosophy of the underlying design intended for this language, as well
as possible grammar of the actual language.

### **Motivation**

The Inuit word *ikajuqtit* means **spirit helpers**. This is the name of the specification, the name of the language
itself will be *qanik*, an word for snow. Using Inuit words partly is cultural pride, but actually the nature
of the Inuktitut language itself is in many ways analogous to the design of this programming language---seemed
like a good fit.

The aim here is to present a specification for a programming language not quite like any other. I think the first
question most coders would ask hearing this would be: Why yet another language? What's worthy, different, distinct
about yours over all the others? ...I aim to offer a vision.

The number one reason I have been dissatisfied with other programming languages---and is the primary design motivation
for researching my own---is that none I have so far seen present coding as *a way of thinking*.

### **Influence**

I have many interdisciplinary influences, which is why I claim this is a language like no other. Otherwise, my influence
largely comes from my training as a pure mathematician. In my own education, I have particularly spent a lot of time on
the foundations of math, and although *category theory* is currently more fashionable---especially in the context of
programming---much more of my influence comes from *set theory*. Math means many different things to many different people,
but for me I have come to see it as the language of patterns, where each branch following the **axiomatic** approach
offers a unique perspective, a way of thinking about a particular type of pattern.  When you learn a particular branch
of math, you are learning the language and system of a particular pattern, and once fluent, then out in the real world
you will recognize (and validate) this pattern against your axioms, and once you do you all of a sudden have an entire
sublanguage to express and discuss and transform and translate without having to do the costly (but fun) research and development
all over again.  For me mathematics is about opening yourself up to new worldviews.

In my studies of computing science and programming on the other hand, I have seldom come across its theory or application being
presented in this way, to my own disappointment of course. I certainly understand the history and influence of Industry on
programming languages, and that so far computing science has been developed by the engineers, who often have a different set
of experiences and outlook than us mathematicians, I get how that factors into the designs of programming languages as we
know it, but I think it's time we axiomatize, formalize, and consolidate the worldviews of computing science into branches
paralleling math.  Why? It's good for Industry, it's good for Education.

We have a *Tower of Babel* of languages effect going on right now. We cannot design innovation and natural societal diversity
to the level of precision that we can the grammars of languages (nor should we try), but that doesn't mean we shouldn't
try at all: We can apply social policy, sociological policy to influence healthy production environments and atmospheres.
This much is a far bigger arena than I can cover here, but a small sliver of that topic I will mention here is this
interoperative chaos. When you have that many languages, scalability becomes an issue when you're spending too much resources
on the overhead needed to translate from ecosystem to ecosystem. This also becomes a security concern. It becomes harder to
ensure security best practices when you have so many systems interoperating. It becomes harder to ensure the assumptions one
relies on even hold in the first place.

As for Education, this again is about a way of thinking. Practical technology is always ever changing. As a career you might
look to keep up with this constantly changing landscape, but if you're looking to build a foundation, you need a way of thinking.
You need to train and teach and learn what computation is as a way of thinking.

### **Interdisciplinality**

What is computation?

I mentioned my influence is interdisciplinary. One of my biggest influences is actually the *Humanities* including the
*Digital Humanities*. Why? Because the Humanities, especially *critical* and *deconstructive* humanities aim to problematize
and show the complexity of socially constructed realities and their relationship to politics and justice and society:
They study complexity in a way very similar to complexity theorists do, only their terminology and methodologies differ
in subtle ways. The humanities study the range of human experience and its expression and with the exception of linguists
as well as computing scientists, humanists have the greatest academic knowledge of how language works.
If you're aiming to build a programming language, it makes sense to be at least somewhat well versed in language.

So I ask the question *what is computation?* in a way which parallels asking first year university humanities students:
*What is literature?* ...it is my own belief that there is no single correct answer and that it's the journey itself which
is the point.  If that's not enough for you---if you're looking for application---then the journey of exploration, finding
a solution then problematizing it only to start over in a never ending cycle in effect teaches you the landscape:
You think deeply and learn deeply about the nature of literature and communication, or in this case computation.
This is to say, for our interests I seek a programming language which teaches you to become **computationally literate**.

There is no right answer to what computation *is*, but as we must start somewhere I will tell you a story:

To answer our question, we have to go back to origins. It was mathematicians who originally theorized about the nature
of computation: Lovelace, Turing, Church, Kleene, Godel, etc.

If you're looking to describe computation in an objective mathematical way, you start by indexing it against well-known
clear cut mathematical objects. This is to say: You find mathematical objects which you can philosophically claim are
*computable*. If you can find such sound mathematical objects (which already exist) then it becomes a matter of finding
models which you prove can successfully imitate or approximate your specification. Historically the computational
objects I speak of are *computable functions* (or "total recursive functions", but as "recursive" as a word is overused
across many disciplines that becomes diffusing and confusing). Naturally the first and major historical implementations
of these computable functions are famously **Turing Machines** and **The Lambda Calculus**.

The reason there is no one right answer then to this question of computation is that historically following our mathematical
specification we run into a problem, more specifically **The Halting Problem**. It is here our discipline of computing
science splits into its pure and applied varieties, the pure still being researched (at a pace far too slow for Industry
standards) by mathematicians, while its applied variety being pursued by engineers.

With engineering introduces a different way of thinking: Mitigating complexity. There are practical complexities to mitigate
in software production (bugs), but just as importantly (more importantly) there are semantic complexities to mitigation
such as the halting problem. This is where more recent *functional* languages come in. With the advent of **Curry-Howard
Isomorphism** and the corresponding typed lambda calculus, we have a model of expressing computable functions with a builtin
design to mitigate halting.

This is all well known though, this is what I call *formal* language (artificial language, mechanical language),
but I would be repleat to not mention it and demonstrate an awareness of the landscape of language itself before
I even begin to describe my own.

In contrast to formal language, I also take my influence from *natural* (organic) language.

#### **Natural Language**

What is natural language?  I'd say the answer to this suffers from complexity as well, though I will put forth my own theory.

A little background first: As mentioned before, part of my influence comes from the Humanities. As a student at the time
I had embraced the Humanities to correct a personal educational deficiency on my part, but having come from a math background
previously I was constantly comparing the difference between formal and natural language as I learned.

The conclusion I've drawn is that the way to model natural language is through a kind of sociological politics. My theory
is that language is self-similar to the politics of that species (in math terms: not isomorphic, but something like homomorphic).
For example a consequence of this is if you were trying to understand the language of a given insect species, you would first
need to understand its politics. I would argue one should not assume the politics (and thus the language) of such a species would
be anything like human politics and language.

What about human politics then? Humans are mammals, we have evolved to be in tribes. As an Inuk not far removed from a traditional
way of life, my parents raised me with the sensibilities of how to belong to such a community. Also, as I participate in this modern
labour force I have many years of work experience under my belt already, and I have seen how people work in large teams---it's
pretty similar to tribal politics. With that said, I'm willing to say an effective model to tribal politics is that there are
what I would call "pillars of support" as people that keep the community together. In such an organic living setting, things
are always changing, but these pillars of support remain stable and thus tether everyone else together. These pillars of support
not only are stable on their own, but they reinforce each other as well. Of course as this is an organic ever changing setting,
even these pillars do change over time, but usually when successful if one pillar falls or fades or leaves another rises to
replace it.

It is my theory if you want to model human language (or even culture) this is the main contributing theory to start with.
In application this means when looking at existing human grammar, one looks for those pillars of grammar which provide the
fundamental support for everything else in the language. One looks to see how they reinforce each other, and how that
effects the politics of any surrounding grammar after that. Patterns of sociology and politics should evidence themselves
when looking at how language changes over time among other things.

#### **Grammatical Case**

associations (words), attributes (equivalence relation), arrangement (ordered equivalence relation)

How to define a noun? It is a name with an identity, but an identity is defined as adjective + navigational space.
It is its own sort of expression with environment needing evaluation.

As to how this theory informs the formal grammar of a formal language will be elaborated upon in the following.
Before that though, I should also explain how *interface design* is another influence:

#### **Identity**

Identity is nomadic.

Identity as orientation.

identity as sifter + navigational space.

#### **Interface Design**

I want to create in interface specification at the same level of rigour as one would code a program itself.
If a grammar design decision is made, it needs to fit the narrative paradigmatic design of the language as a whole,
with proofs as to why and how it is and does.

As coders, we learn quite a lot about general design, especially when it comes to mitigating the complexities of
our ever more complicated programs---we learn through paradigms how to successfully scale amoung other things.

In my experience with programming languages in general, one deficit I've found is that the designers of languages
don't seem to put as much effort into interface design of the language's grammar itself. This is unfortunate.
Well, it's one thing to make such a claim, but in reality, what does this even mean?

descriptive language, navigation, interface design, neurons, place cells.

#### **Signal Processing**

information theory, complexity theory, structural vs functional compression. Structural/Functional paralleling Humanities.

Part of the conceptualization of variables as filters comes from signal processing.

### **Design**

direct map to hardware, zero-overhead abstraction.

navigational, generational paradigm design.

#### **Memory Narrative**

### **Run time**

run time data structures / functions.

### **Compile time**

compile type typology, hardware as primitives.

