---
title: What it’s like to be a developer at iyzico
---

I have been working at iyzico as a frontend engineer for almost 3 months. From the perspective of a relatively newcomer, I want to share my experiences during these 3 months.

## How was my first day at the job?
On the first day of the job, I was given a first day challenge to complete until the end of the day. It was an email template for an event that the company is organizing. This might not sound like real challenge to you. At first, I thought the same. But there are a few important things that you need to be careful about when it comes to an email template with pure HTML and CSS. The first thing is you need to make sure that your template looks good in every possible devices (phones, desktops, tablets etc.), browsers and email clients. Another thing is you need to style your HTML inline because some email clients strip away the whole HEAD section. In addition to these, I had to use tables for the design I was given. Styling HTML tables is a real pain, especially when you have to write inline styles.

At the end of the day, I completed the challenge after several revisions and testings. Then I heard a bell sound. This was a traditional gathering alarm for the engineering team and it was ringing for me. All of the engineering team gathered to give me a reward (a big Lego package) for my achievement. Then we took a picture altogether. It was such a great day.

![](https://cdn-images-1.medium.com/max/800/1*yftk8HKxqeaQc5VJS90amw.jpeg)
## What about my team and what we are working on?
I work on the front-end team where our main job is creating and maintaining modern web and mobile applications for our products and helping other departments with their requirements. Our team consists of 4 people. The main projects we are working right now are the new merchant control panel and its mobile application.
## What are the most common tools that we use?
We use Git with Bitbucket for source code management and reviews, Bamboo for CI/CD, Confluence for team collaboration and documentations, Slack for instant messaging. Backend developers are using JetBrains for IDE as they are coding in Java. Developers on the front-end team use whatever IDE that suits for them. Majority of the developers are using VS Code.
## Which technologies are we using in the front end?
In terms of choosing a front-end technology stack, there are couple of things that we follow. First of all, it should meet our requirements and keep things simple. It should also be open-source and accepted by the ecosystem. And finally It should have a long term support.

For small projects that are not going to be complex in the future, we use jQuery. The reason is that it is already known and used by our backend developers. They can easily maintain their own front-end projects by themselves. For mid and complex level projects, we use React/Preact, Redux, Styled Components, Webpack, Jest and Graphql stack. In addition to web applications, we are also developing a mobile application for our customers. For that application, we are using React Native. It makes our life a lot easy since we already have a codebase written with React which some parts of it can be reused in React Native application. Plus, we can ship to both IOS and Android platforms with one codebase. Currently, this stack is working great for us and we are happy to be using bleeding edge technologies at work.
## What is the development process like?
At iyzico, engineering teams are using Scrum methodology. Every week we make a sprint planning meeting and every morning we make a daily meeting. Everybody informs their team members about what they did yesterday and what they are going to do the following day. Then we pick our assigned tasks from a sprint backlog and coding starts. We create a new branch for every task. After completing a discrete unit of work (fixing a bug, implementing a feature, writing a test etc.), we create a pull request. Other team members review the pull request. Once everything looks good, we merge the pull request. At this point our CI/CD pipeline takes over and runs all our unit and integration tests. If everything passes, it’s automatically deployed to staging environment. After everything works as expected in staging and test environments, we finally deploy to production.
## What is code review like?
We take code review seriously. Every change goes through review by at least one team member. We use Bitbucket’s pull request mechanism for code review. We notify developers on the team using Slack when we open up a pull request. After their approval, code is merged into development branch.
## How is testing done, and what kind of tests are run?
We have unit tests, functional tests and integration tests in the front-end. All of which must run successfully before code can be merged. Beside unit tests, we write snapshot tests for our React components using Jest. For the most part, snapshot tests remove the need for writing unit tests. It makes writing tests very easy for us.
## How is code deployed?
Engineering teams at iyzico embraces a continuous deployment methodology, which means changes are scaled smaller and deployed often. We uses Atlassian’s Bamboo for CI/CD.
## What is an average day-in-the-life of someone on the front-end team?
An average day for a developer starts off by daily meeting with the team, then quick checking emails and messages on Slack. After that, we dig into tasks we are assigned to and write lots of code. When our work is finished with a task, we submit a pull request, request reviews from team members, merge it once everything is OK and automated deployment handles the rest of the work. On Fridays, we do planning meetings for the next week’s sprint.
## What about company and its culture?
iyzico is a great place to work at. Everybody is very supportive and collaborative. You feel like you were part of the team from the beginning of the company.
From the point of job satisfaction, there are very talented and passionate people at iyzico. Working with them and learning from them is a great value. On the other side, we always encouraged to try new technologies and use them in our projects if they work for us. We have brown-bag sessions that create a learning culture within the company. Everybody shares their knowledge with the rest of the company once in a week.

We have Monthly Meetings that we organize every month that everybody in the company attends. In this meeting, company metrics, good or bad things in general are shared, newcomers are welcomed, anniversary stories are told.
## Conclusion
Overall, I’m very happy to be part of iyzico family and really excited to see what we are going to accomplish in the future. Hope this post gives you an idea about the company and our development process.