# compsci3mi3-assignment-3-solved
**TO GET THIS SOLUTION VISIT:** [COMPSCI3MI3 Assignment 3 Solved](https://www.ankitcodinghub.com/product/compsci3mi3-cs-3mi3-fundamentals-of-programming-languages-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;117732&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;COMPSCI3MI3 Assignment 3 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
Idea

The goals of this assignment are:

1. Learn how to interpret small-step semantics

2. Learn how to translate semantics into an implementation

3. Learn how to identify buggy semantics

Logistics

A project template is available on the course GitHub that includes all of the code from this document, along with a testing framework. You can find it at the following url: https://github.com/JacquesCarette/COMPSCI3MI3-F2023/tree/main/Assignments/a3

The Tasks

1 Revenge of the Goblins and Gnomes [40 points]

The goblins and gnomes of the magical island were very entertained by your riddle solving program. Unfortunately, they got bored of that pretty fast, and will not let you go home unless you can write a program that plays the famous Gnomish game called “SKI”.

The rules of “SKI” are as follows: you are given an expression in the following grammar:

hexpri ::= S

| K

| I

| hexpri hexpri

| (hexpri)

Unparenthesized expressions are left associated, so SKI should be parsed as (SK)I. To play “SKI”, you must apply the following sequence of reduction rules :

Sxyz → xz(yz) Kxy → x Ix → x

Implement a Haskell datatype called SKI that corresponds to the provided BNF, and then implement a Haskell function with the following signature that performs a single step of these reduction rules.

ski : : SKI −&gt; Maybe SKI

The function ski should return a Just containing a reduced value, or Nothing if no reductions were possible. Write at least 10 tests using HUnit, making sure that you test all reduction rules, as well as edge cases. Code is worth 15 points, tests are worth 15, and documentation is worth 10. You should write your code in a file called “src/A3/SKI.hs”, and your tests in a file called “test/SKITests.hs”; both of these files are already set up for you in the project skeleton.

2 Loopy Lambdas

One of the major reasons programming-language theorists love the λ-calculus is that it is a good basis for building other programming languages. Here, we will consider an extension of the λ-calculus that adds natural numbers, and a simple looping construct.

hexpri ::= hvari

| λ hvari. hexpri

| hexpri hexpri

| 0

| 1 + hexpri

| loop hexpri hexpri hexpri

| (hexpri)

Intuitively, ‘loop i s f’ denotes a loop that counts down from i to 0, applying f at each step until it terminates with s. However, intuition isn’t enough: we need some sort of formal semantics to specify exactly how our programs evaluate!

2.1 One Small Step for Lambdakind [40 points]

Implement the following operational semantics in Haskell; it should have the signature stepLoop : : Expr −&gt; Maybe Expr

(λx.e1)e2 → e1[e2/x]

loop e1 e2 e3 → loop loop 0 e2 e3 → e2 loop (1 + e1) e2 e3 → e3 (loop e1 e2 e3)

The Expr type can be found in the project skeleton, along with code for checking α-equivalence of terms and performing substitutions.

You should also write at least 25 tests, making sure to cover all constructors, as well as edge cases. At least 3 of these tests should construct your student number. You are allowed (and encouraged!) to use the provided helper functions in your testing code.

Furthermore, both you step function and tests should be documented. The documentation for the step function should make clear what rules you are applying, and the documentation for the tests explain why you are testing something. Code is worth 15 points, tests are worth 15, and documentation is worth 10. You should write your code in a file called “src/A3/LoopyLambda.hs”, and your tests in a file called “test/LoopyLambdaTests.hs”; both of these files are already set up for you in the project skeleton.

2.2 Another Small Step for Lambdakind? [20 points]

Consider the following additional reduction rule.

loop e1 e2 e3 → loop

If it is possible to extend our implementation with this reduction rule, write a function stepLoopExtra : : Expr −&gt; Maybe Expr

If it is not possible, explain why. Your answer should take the form of a comment, using the following format:

{− [ Question 2.2]: &lt;your answer here&gt;

−}

Submission Requirements

• Must be handed in as a .zip, .gz, or .7z file. Other archive formats will not be accepted, resulting in a score of 0. The archive should be called A3 macemailid.zip (with your email address, I am

“carette”, substituted in).

• The name of the file does matter.

• If you looked things up online (or in a book) to help, document it in your code. If you have asked a friend for help, document that too. “Looked things up online” includes all AI tools. Put this in a README file (as plain text, Markdown, or HTML).

Bonus

Mechanized Metatheory [Difficulty: FF]

Encode the loopy lambda calculus in either Agda or Idris 2, and encode the reduction rules as an indexed type. Use this indexed type to prove that (λx.xx)(λx.xx) has no normal form.

Include the Agda or Idris file inside of the submitted .zip file.

Downhill SKI-ing [Difficulty: FFF]

S 7→ λx.λy.λz.xz (y z)

K 7→ λx.λy.x

I 7→ λx.x

In fact, it is also possible to interpret lambda calculus into SKI. Your task is to invent an algorithm for compiling expressions in the untyped λ-calculus into SKI expressions, and to implement this algorithm in Haskell.

This should be submitted as src/A3/LambdaToSKI.hs.

Self-referential SKI [Difficulty: FFFFF]

Church-encoding allows us to represent datatypes inside of the untyped λ-calculus. Furthermore, the syntax of untyped λ-calculus is itself a datatype. If we put these two facts together, we can encode the syntax of untyped λ-calculus inside of itself via Church-encodings. Use this observation to implement the compiler from λ-calculus into SKI inside of your implementation of the untyped λ-calculus. For fun, note that you can use your solution from Bonus 2 to make your program “self-hosting”: it is a compiler from untyped λ-calculus to SKI, written only using SKI!

This should be submitted as src/A3/SelfReferenceSKI.hs. Be warned: this is devilishly hard.
