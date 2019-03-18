## Background

Exercism is an online platform that helps people improve their fluency in programming languages. Through a mixture of interesting programming challenges, mentoring, and community-learning, we help people develop fluency in the basic syntax, data structures, language features, and standard library of the language, as well as the conventions and idioms of the language community.

The basic workflow of Exercism is as follows: A learner signs up to a language track. They are presented with a spine of Core Exercises, each teaching a different topic. Using our command-line interface, they download the exercise, read the introduction and solve it by making the pre-written tests pass, then submit it for review. A volunteer mentor will review the exercise and post feedback and guidance on how to make it more idiomatic. The learner will then iterate on their solution until the mentor marks it as completed. At this stage, the learner unlocks the next Core Exercise and also a series of Side Exercises, which offer more complex challenges on related topics. While learners can request mentoring on these Side Exercises, we encourage them to look at how others in the community have solved the same problem, and learn from reading their solutions.

Our biggest barrier to fulfilling our goals today is being able to deal with scale. Our volunteer-led mentoring approach means that we rely on people giving their time to help others. As of today, we are just about managing to keep up with the mentoring demand. However, if we start to actively advertise to people who are not part of the middle-class community who typically discover us, we risk quickly overwhelming our mentors and making Exercism unsustainable. We have a long-term, multi-threaded strategy to solve this problem, which includes restructuring tracks, adding and improving mentoring tools, adding content to allow people to learn more easily from each other, and automating the more mundane and routine parts of mentoring. This repository addresses the final one of those challenges — the automation of mentoring — which is by far the most technically challenging, complex, and time-intense part of our plan.

Our volunteer-mentors are crucial to Exercism’s success. They are responsible for reviewing learner’s solutions, analysing whether they meet the success criteria of the exercise or need to be improved, empathetically understanding a learner’s thought process, providing encouraging and helpful feedback, and teaching a language’s idioms.

For the Core Exercises that form the spine of an Exercism language track, we estimate that about 25% are good enough to be marked as complete first time. A further 55% have problems that fall into common buckets, which can be mentored by pasting repeatable snippets to a student. Only about 20% of solutions actually require a mentor to be inventive and thoughtful in their feedback. The 80% of solutions that do not truly engage a mentor’s brain are a frustrating and boring time-sink for people who are willing to volunteer their time to helping others, and do not make the most of their expertise.

In parallel to the mentors’ pain-points, depending on the track, learners wait for 1-2 days before receiving feedback on their solution and are unable move forward on the track in the interim. If you fall into the 25% bucket of students who have submitted a perfectly valid solution, this wait is extremely frustrating. To the rest, this delay is suboptimal at best. Learners often lose momentum due to this wait and become frustrated at the process.

## What we're building

To solve this, we intend to develop an automated analysis system that can analyse a solution to understand if: the solution is good enough and can be automatically approved; a simple piece of feedback can be provided to move the learner forward; or the solution requires mentor attention. Our long-term goals is to develop deep-learning algorithms that can analyse the Abstract Syntax Trees (ASTs) of the 930,000 submissions that have been submitted, and detect common patterns and related comments by mentors. Our shorter-term goal is to use [static analysis](https://en.wikipedia.org/wiki/Static_program_analysis) of the code to determine what common feedback can be given based on the most commonly repeated errors seen by mentors, and our first step in that is to build a framework for applying static analysis to auto-approve good solutions on the first few Core Exercises in the language tracks. We believe that in doing this we can reduce the submission queues by 50%, accelerate the feedback cycle for a learner who is getting things mainly right from one day to ten minutes, and eliminate the majority of “boring” work for mentors.

We believe that this static analysis project will have an immediate impact in three ways:

- It will reduce the number of solutions in the mentoring queue
- It will remove the most boring job from mentors and ensure their attention can be directed where it’s more useful, tapping into their capacity to pass on their knowledge to others
- It will avoid blocking learners by forcing them to wait for feedback when they could simply move on

## Building it

Our core team are building out three parts to this: 
1) The integration of static analysis into the mentoring flow
2) The infrastructure to achieve this
3) A production-ready proof-of-concept for auto-approving the “Two Fer” exercise in Ruby. 

We are also inviting other contributor to build proof-of-concepts in other languages. We have a project with [students at Cornell taking cs5152](http://www.cs.cornell.edu/courses/cs5152/2019sp/) who are building out these proof of concepts as part of their course.

Once we are happy with the Ruby implementation, have integrated this into the website, we intend to expand the project to:
- Auto-approve (a significant portion of solutions to) Two-fer in all Exercism languages
- Auto-approve (a significant portion of solutions to) other exercises across the site
- Provide feedback on possible improvements within auto-approved exercises
