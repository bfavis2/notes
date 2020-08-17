# Preface
Pragmatic Programmers are:
* Early adopters/Fast adapters - have an instinct for technologies and techniques
* Inquisitive - be a pack rat for little facts and tidbits
* Critical Thinkers - Doesn't accept things as given without the facts
* Realistic - Understand the underlying nature of each problem you face
* Jack of All Trades - Be familiar with a broad set of technologies and environments. Tech is constantly changing

Care about your craft and think about your work - Never run on autopilot and constantly learn.

Getting better is a continuous progress - need to water every day little by little to get somewhere.

# Chapter 1 - A Pragmatic Philosophy

## Responsibility and Ownership

It is your life. You own it. If you don't like it then change. Don't be tied down to external factors. Be proactive and take opportunities.

Take responsibility and build trust. When something goes wrong, don't provide lame excuses or blame others. Provide options on how to fix it.

Follow up "I don't know" with "--but I'll find out later".

##

Don't leave bad designs, wrong decisions, poor code, etc. in your projects. It invites more software rot/technical debt.

Fix problems before they get out of hand and try to do things right the first time by thinking about future problems.

Be a catalyst for change - develop the backbone of project well. Show people and have them want to work on it on their own accord.

Develop "good-enough" software - keep an eye out for the big picture. Don't get distracted by too many bells and whistles.

Make quality a requirements issue - ask users how good they want the software to be.

Know when to stop - don't spoil a perfectly good program with overembellishment and overrefinement. Move on and let your code stand on its own for awhile.

It's never going to be "perfect" and that's ok.

## Knowledge Portfolio

Knowledge is an expiring asset - new technologies, tools, and techniques are constantly popping up.

Treat your knowledge as a portfolio:
* Invest regularly - Get in the habit of learning new things everyday.
* Diversify - The more different things you know, the better you can adjust to change and the thus the more valuable you are.
* Manage risk - Don't put all your eggs in one basket with high reward/high risk ventures. Also, don't just put all the eggs in a conservitave basket and
miss opportunities. Have both.
* Buy low, Sell high - Become an early adopter. Keep an out for potential technologies with room to grow.
* Review and Rebalance - Keep a level of polish on your knowledge. Go back to things you learned a long time ago and keep it up to date.

Ideas to keep invest in your knowledge portfolio:
* Learn a new language once a year
* Read a technical book each month
* Read non-technical books, too
* Take classes
* Participate in local user groups and meetups
* Experiment with different environments
* Stay current

Admit to not knowing something at take it as a challenge to find out more.

Develop critical thinking skills:
* Always ask why to get to the root of the problem
* Who does this benefit?
* What's the context?
* When/Where would this work?
* Why is this a problem?

## Communicate!

The greatest program/software/code is useless unless you can communicate with other people.

Treat English like another programming language.

Know your audience - tailor what you present to what your audience finds important. Stylize according to who you are talking to.

Know what you want say - prepare by writing an outline

Choose an appropiate moment to talk to someone.

Make your ideas look good - Don't just focus on the content and expect people to see what you see.

Actively engange with your audience - have them be part of the process.

Be an active listener. If you listen to people, people will listen to you. Learn from other people.

Get back to people - Respond to people as soon as you can and let them know if you can't fulfill their request right now.

Document everything! Treat documentation as part of the code instead of an afterthought.

# Chapter 2 - A Pragmatic Approach

## The Essence of Good Design

Overarching general principle is to keep code "easy to change" (ETC) - Good designs are easier to change than bad designs.

Programmers should constantly be in "maintenance" mode. It shouldn't wait until an application is released or when bugs present themselves.

### Duplication and DRY

Duplicate knowledge can be a nightmare for maintence so strive for DRY (Don't Repeat Yourself).

"Every piece of knowledge must have a single, unambiguous, authoritative representation within a system."

You will eventually always forget if you have repeat information in multiple locations so have it only in one to make it easier to maintain.

Not all code duplication is knowledge duplication. It's about the knowledge they represent instead of the content of the code.

It is not necessary to docstring all functions with what the function does exactly. Let the code speak for itself.

If you must repeat, like for performance gains, do so locally. Don't let the violation be exposed to the outside world.

Where possible always use accessor functions to read and write the attributes of objects.

Meyer's Uniform Access Principle - "All services offered by a module should be available through a uniform notation, which does not betray whether they are imlemented through storage or through compuation."

Often code interfaces with the outside world. Whether it makes remote calls, fetches data from an external source, or uses an API. This is duplication because both have knowledge of the representation of the interface. If the interface changes at one end, the other end will break.

Sometimes it's impossible to avoid, but it can be mitigated.

For duplication across internal APIs - look for tools that specify the API in a neutral format. Ideally, these tools will store all APIs in a central repository for shared access.

For duplication across external APIs - public APIs are documented using OpenAPI. Allows you to import the API spec into your local API tools and integrate more reliably with the service.

Duplication with Data Sources - ??? I did not understand this part ???

Interdeveloper duplication is insiduous and hard to deal with. Set up proper communication with your team or even set u a project librarian whose job is to facilitate knowledge exchange.

Make code easy to reuse!

### Orthogonality

Orthogonality refers to objects/systems that are independent or decoupled from eachother. i.e. if you can change one thing without changing another thing, they are orthogonal.

Eliminate effects between unrelated things. Design self-contained components (indepedent and having only a single, well-defined purpose).

Orthogonal systems increases productivity and reduces risk.

Modular, component based, and layered refer to the same general idea of orthogonality. Components organized into layers each provide a level of abstraction.

Also be wary of coupling your design to external factors, like using a phone number as a customer identifier. Instead set up your own key that you control.

Your code should be shy - modules shouldn't reveal any unenecessary information to other modules. They should be isolated.

Avoid global data. Pass along context through paramters in an objects' constructors for example.

Get in the habit of being constantly critical of your code.

Orthogonal systems are much easier to test.

If a unit test has to get a bunch of other information from the rest of the system, then that module isn't very well decoupled. Bug fixes are the same way.

Orthogonality applies to documentation too. The content should be independent of the style of documentation.

No decisions are final - always assume that things can be changed around and be flexible.

Hide third-party APIs behind your own abstraction layers.

Break your code into components.

### Tracer Bullets and Prototyping

Refers to using a sort of flare first to refine your aim and to get a good sense of where you are aiming at before firing actual bullets. The same concept can apply to software.

For a new project, instead of specifying systems to the last detail and trying to get it right the first time, try to just use a "tracer bullet" to just find the target and refine it from there.

Tracer bullets get to the target fast and the developer gets immediate feedback.

Look for the very important and potentialy risky requirements first.

Tracer code is not disposable. It should be built off of.

Convential alternative is a heavy engineering approach - divide code into modules that are coded in a vacuum. Combine all the modules at the end and have a fully completed application that can be used and tested.

Tracer code has some key advantages:
* Users to see something early
* Gives developers a structure to work around
* Builds an integration platform
* Gives something to demonstrate and show
* Clearer sense of progress

Tracer code doesn't always hit the mark so adjust accordingly. Tracer code is relatively small so it should be easier to adjust.

Tracer code is different than prototyping. Prototyping aims to explore specific aspects of the final product and is usually disposable.

Think of tracer code as the skeleton of the final product, while prototyping is like a bad replica of a certain aspect of the final product that can't be used again.

Prototypes don't necessarly have to be code - you could map out the workflow or application logic with post-it notes for example.

Items that carry a risk, are critical to the system, or are experimental are all good candidates to prototype.

Prototypes are learning tools.

When building prototypes you can gloss over the minor details. The aim is to get something represensative and decently functional.

Make sure everyone, including management, that the protoype is not the final products or deployable.

### Domain Languages

\*The domain language section doesn't really make sense to me\*

Different languages comes with different features that change the way you solve a problem.

Program close to the problem domain language.

Internal domain languages are just extensions of the host languages - they are compiled and ran just like any other piece of code.

Internal domain languages are bound by the syntax of the host language and thus are forced to compromise.

External languages are converted or parsed into a form that the host language can run.

External languages are much more flexible, but you need to write a parser to actually read it - this might require too much effort.

### Estimation

Use estimates to avoid surprises.


