Sitora Urazova 
Homework 8/2/18
Test Driven Development 

Test-driven development (TDD):
is a software development process that relies on the repetition of a very short development cycle.

The first step is to quickly add a test, basically just enough code to fail.  Next you run your tests, often the complete test suite although for sake of speed you may decide to run only a subset, to ensure that the new test does in fact fail. You then update your functional code to make it pass the new tests. The fourth step is to run your tests again. If they fail you need to update your functional code and retest. Once the tests pass the next step is to start over (you may first need to refactor any duplication out of your design as needed, turning TFD into TDD).

There are two levels of TDD:
Acceptance TDD (ATDD).  With ATDD you write a single acceptance test, or behavioral specification depending on your preferred terminology, and then just enough production functionality/code to fulfill that test. The goal of ATDD is to specify detailed, executable requirements for your solution on a just in time (JIT) basis. ATDD is also called Behavior Driven Development (BDD).
Developer TDD. With developer TDD you write a single developer test, sometimes inaccurately referred to as a unit test, and then just enough production code to fulfill that test. The goal of developer TDD is to specify a detailed, executable design for your solution on a JIT basis. Developer TDD is often simply called TDD.

Definition
"Test-driven development" refers to a style of programming in which three activities are tightly interwoven: coding, testing (in the form of writing unit tests) and design (in the form of refactoring).

It can be succinctly described by the following set of rules:

write a "single" unit test describing an aspect of the program
run the test, which should fail because the program lacks that feature
write "just enough" code, the simplest possible, to make the test pass
"refactor" the code until it conforms to the simplicity criteria
repeat, "accumulating" unit tests over time

Common Pitfalls
Typical individual mistakes include:

forgetting to run tests frequently
writing too many tests at once
writing tests that are too large or coarse-grained
writing overly trivial tests, for instance omitting assertions
writing tests for trivial code, for instance accessors
Typical team pitfalls include:

partial adoption - only a few developers on the team use TDD
poor maintenance of the test suite - most commonly leading to a test suite with a prohibitively long running time
abandoned test suite (i.e. seldom or never run) - sometimes as a result of poor maintenance, sometimes as a result of team turnover

1. Write a Test
Since development is driven by tests, the obvious first step is to create a new test. This test should be as succinct and as simple as possible, testing a very specific aspect or component of a larger feature. For example, if you’re creating a user registration feature, you could create a single test that encompasses every aspect of registration, from the generation of the form elements, to the user entry, to the database connection, to the data models, and so forth. However, it would be quite difficult to properly create a single test that encompasses all those aspects, let alone one that does so efficiently and effectively from the outset.

Instead, test-driven development encourages you to write the smallest possible test that is necessary to meet the needs of the actively developed feature. Over time, many tests are created, until enough tests exist to cover every aspect of the much larger feature.

Thus, a single test that relates to the user registration feature might be something as simple as: “email field is not blank.” Most tests created in test-driven development use some sort of language-specific framework that allows tests to be “titled” or “named”, typically be writing a simple phrase that defines the behavior (commonly referred to as a user story). Thus, our first test might be titled “email field is not blank”, and its purpose is simply to test that the email field is not empty when the form is submitted.

2. Confirm the Test Fails
Once the test is created, the next step is to confirm that the test fails. The entire purpose of the test-driven development methodology is to force you to think about the requirements of a feature or a section of code, such that a created test will not only be necessary in order to confirm when the feature is finally working as expected, but also that the test will fail prior to implementing said feature. By confirming that the new test fails — and does so for the reason(s) you expect — you can be confident that the test is useful, and will be beneficial once you write the code necessary to pass the test.

3. Write Code to Pass Test
After confirming that the test fails, you now must write the code that will allow the test to pass. One key idea here is that you should not write any additional or extraneous code that goes beyond the scope of the test. Just as we focused on creating the simplest test possible in Step 1, here we want to write the simplest code possible that allows our test to pass.

Code written here will likely be rough and not finalized, but that’s OK. The entire test-driven development process encourages constant refactoring, meaning your current code is likely to change numerous times in the future.

4. Confirm the Test Passes
Once your new code is written, confirm that the test now passes. In our example case, we’ve confirmed that submitting our registration form with a blank email field causes our test to fail, while entering text in the email field allows the test to pass. Believe it or not, that’s all there is to the the basic test-driven development process.

5. Refactor
During the fifth step, even though you now have a test that passes, the process of writing the code necessary to allow said test to pass may have introduced some duplications or inconsistencies. That’s perfectly normal and expected, but the importance of the refactoring step is to take the time to locate those problem areas and to focus on simplifying the codebase.

This process should also include frequent re-running of all previous tests, to confirm that you haven’t accidentally introduced any additional bugs, or changed something that now causes a previously passing test to fail. Most developers will know this practice as regression testing — confirming that functional code doesn’t break due to new changes.

6. Repeat All Steps
Arguably, there is a sixth step in this five-step test-driven development process: repeat. If everything is kept small (small use cases, small tests, small code changes, small confirmations, etc), then the entire process, from writing a failing test to confirming a passing test and refactoring, can often take only a few minutes. Thus, the process is repeated over and over, with each new test slowly incrementing the entire codebase, progressing closer and closer to a fully-realized and completed feature.

Red-green-refactor is a simplified, shorthand version of test-driven development that you may hear from time to time, and it’s just another way of referring to the basic steps outlined above. A red test is a failing test, while a green test is a passing test, so the process of red-green-refactor just means to create a failing test, make it pass, and then refactor.

Tool-Assisted Test-Driven Development
For most modern software development projects, test-driven development is largely based around the use of other tools that dramatically assist with the process. The most beneficial of these tools is easily the automated test runner or automated task runner. There are too many such tools to list here, but depending on the language or framework you’re using, there’s bound to be multiple choices available to you.

The obvious benefit to an automated test runner is the ability to have all your tests executed automatically without your direct intervention. For developer-centric testing, such as most unit testing that is the core of test-driven development practices, not having to worry about manually executing tests yourself is a lifesaver. Many automated test runners can even execute tests when changes are made to a desired set of files. This way, your tests can always be running in the background, and if a test fails due to a recent change in the code, you can be alerted immediately, while otherwise focusing entirely on the code you’re working on.

Advantages of Test-Driven Development
Reduces the Reliance on Debugging: Since test-driven development focuses on writing tests first, and only then creating code intended to pass said tests, many developers find that a test-driven development life cycle can dramatically reduce the need for debugging. Since test-driven development encourages a much deeper understanding of logic and functional requirements during test writing and coding, the cause of a failing test can often be quickly recognized and remedied.
Considers the User Experience: The process of initially thinking about and writing a test fundamentally forces your brain to work backwards: You first consider how the function will be used, then how it might be implemented, and then how a test to encompass that should be written. This encourages you to consider the user experience aspect of the feature (and therefore the entire project as a whole).
Can Decrease Overall Development Time: According to some, test-driven development practices have been shown to reduce the total development time for a project when compared to a traditional, non-test-driven model. While total lines of code increase (due to the extra lines in tests), frequent testing often prevents bugs and catches existing bugs much earlier in the process, preventing them from becoming problematic later down the line.
Disadvantages of Test-Driven Development
Discourages Big Picture Design: Since test-driven development encourages developers to write the simplest possible test, then resolve that test with the simplest possible code, this can often lead to a severe lack of scope regarding the overall design of a feature or the whole project. When using test-driven development practices, it’s all too easy to miss the forest for the trees, since your entire focus is on the minutiae of the problem at hand. Repeating these focused practices during minute-to-minute development often leads to designs that are too specific in nature, rather than stepping back and looking at the big picture.
Difficult to Apply in All Cases: Test-driven development is great at handling smaller projects, or even small components and features of larger projects. Unfortunately, test-driven development practices may begin to falter when applied to incredibly massive or complex projects. Writing tests for a complex feature that you may not yet fully understand can be difficult if not impossible. Writing tests is great, but if those new tests don’t accurately represent the requirements of the feature, they serve no purpose (or may even actively hinder development). Moreover, some projects — particularly those dealing with legacy code or third-party systems — simply don’t lend themselves to test-driven development practices, because it may be near-impossible to create tests that properly integrate with those systems or that legacy code.
Requires Additional Time Investment: While arguably the time spent on generating tests upfront is saved later on in the development life cycle (see Advantages above), the fact remains that test-driven developmentrequires a significant upfront output of time and energy to come up with and write tests. For many developers, that time may be better spent simply writing new or refactoring existing code,

Pros of Test Driven Development
Because you are writing small tests at a time, it forces your code to be more modular (otherwise they’d be hard to test against). TDD helps you learn, understand, and internalise the key principles of good modular design.
TDD also forces good architecture. In order to make your code unit-testable, it must be properly modularized. Writing the tests first, various architectural problems tend to surface earlier.
Documents your code better than documentation (it doesn’t go out of date since you’re running it all the time).
Makes code easier to maintain and refactor. TDD helps to provide clarity during the implementation process and provides a safety-net when you want to refactor the code you’ve just written.
Makes collaboration easier and more efficient, team members can edit each others code with confidence because the tests will inform them if the changes are making the code behave in unexpected ways.
Because TDD essentially forces you to write unit tests before writing implementation code, refactoring of code becomes easier and faster. Refactoring code written two years ago is hard. If that code is backed up by a set of good unit tests, the process is made so much easier.
Helps prevents defects – well, at least it helps you find design or requirement issues right at the beginning. TDD provides early warning to design problems (when they are easier to fix).
Helps programmers really understand their code.
Creates an automated regression test suite, basically for free. i.e. you don’t need to spend time afterwards writing unit tests to test the implementation code.
It encourages small steps and improves the design because it makes you cut the unnecessary dependencies to facilitate the setup.
It helps to clarify requirements because you have to figure out concretely what inputs you have to feed and what outputs you expect.
Unit tests are especially valuable as a safety net when the code needs to be changed to either add new features or fix an existing bug. Since maintenance accounts for between 60 and 90% of the software life cycle, it’s hard to overstate how the time taken up front to create a decent set of unit tests can pay for itself over and over again over the lifetime of the project.
Testing while writing also forces you to try to make your interfaces clean enough to be tested. It’s sometimes hard to see the advantage of this until you work on a body of code where it wasn’t done, and the only way to exercise and focus on a given piece of code is to run the whole system and set a break-point.
“Stupid” mistakes are caught almost immediately. It helps developers find mistakes that would waste everyone’s time if they were found in QA.
Cons of Test Driven Development
The test suite itself has to be maintained; tests may not be completely deterministic (i.e. reliant on external dependencies).
The tests may be hard to write, esp. beyond the unit testing level.
Initially, it slows down development; for rapidly iterative startup environments the implementation code may not be ready for some time due to spending time writing tests first. (But in the long run, it actually speeds up development)
Like any programming, there is a big difference between doing it and doing it well.  Writing good unit tests is an art form. This aspect of TDD is often not discussed, many managers tend to focus on metrics like code coverage; those metrics tell you nothing about the quality of the unit tests.
Unit testing is something the whole team has to buy into.
A challenge to learn. It can be intimidating and not easy for anyone to learn at first, especially trying to learn it on your own. It requires a lot of dedication (discipline, practice, persistence) and you have to have the goal that you want to continually get better at it.
Hard to apply to existing legacy code.
Lot’s of misconceptions that keep programmers from learning it.
Hard to start working this way. Especially if you have many many years of working the other way.
You sometimes have to mock a lot of things or things that are difficult to mock. It’s beneficial in the long term, but painful right now.
You have to perform housekeeping continually. Because booking more and more tests make your build longer and longer, it’s necessary to refine those tests to make them running more quickly or to remove redundant tests.
Like any good technique, unit testing can be carried to an extreme. The biggest benefits come from a moderate effort, with the tests always exercising the code in the simplest way possible.  If you find yourself frequently refactoring your tests, there’s a good chance you’re spending too much time on the test suite.
It can be easy to get distracted by “fluff” or fancy features in the unit testing framework. We should remember that simple tests are the fastest to create and the easiest to manage.
Although it is absolutely necessary, creating tests for failures can be tedious, but it pays off big time in the end.
Early stage refactoring requires refactoring test classes as well.
Unless everyone on the team correctly maintains their tests, the whole system can quickly degrade.
