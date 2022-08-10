# 🎺 Remix Bebop Stack

![Charlie_Parker,_Tommy_Potter,_Miles_Davis,_Duke_Jordan,_Max_Roach_(Gottlieb_06851)](https://user-images.githubusercontent.com/2739726/183922149-5140dc98-208a-411c-9d84-f02419c62abc.jpeg)

Learn more about [Remix Stacks](https://remix.run/stacks).

    npx create-remix --template epeterson320/bebop-stack

## 🎁 What's in the stack

* Bulletproof authentication with [Auth0](https://auth0.com/).
* Authorization (declarative attribute-based access control) with [Oso](https://www.osohq.com/)
* Database ORM, migrations, and seeding with [MikroORM](https://mikro-orm.io/) (using PostgreSQL by default).
* Testing with [Jest](https://jestjs.io/).
* Some handy VSCode settings: recommended extensions and full-stack debug config.
* Linting with [ESLint](https://eslint.org).
* Code formatting with [Prettier](https://prettier.io).
* Git hooks with [Husky](https://typicode.github.io/husky/#/).
* UI kit with [MUI](https://mui.com/).
* No default deployment, because you probably have opinions, but the app is Dockerized
* Typescript, with [Typescript](https://www.typescriptlang.org/).

## 🚫 What's not in the stack

* Prisma
* Storybook
* Breejs, queues, or anything in the background
* Cypress

## Authorization

The main idea behind the authorization model (and the starting data model) is that nearly every B2B app has _organizations_ which in turn have _resources_. For example, Github orgs have repos, Slack orgs have channels, Office 365 orgs have all sorts of documents and spreadsheets, Figma orgs have graphics files, and the list goes on. In every case, if you create a resource within your org, you own it and control its permissions, with the exception that your organization's admins can access all resources within the org. App admins (i.e. customer support agents for the SaaS) can access resources across any organization.

That authorization model is what you get out of the box, powered by [Oso](https://www.osohq.com/), and the rules can be modified and expanded by editing the **.polar** files inside **auth/**. See their docs for help. If you don't know much about authorization, prepare to have your mind blown.

## FAQ

#### Why MikroORM and not Prisma? 

Because [Prisma doesn't support GIS types or geospatial queries](https://github.com/prisma/prisma/issues/2789), which means if you use Prisma, you're going to have a hard time getting your app to do anything useful that deals with real-world space and distance.

#### Why can't I use Storybook?

Because you're building an app, not a component library. You need to value your time enough to pick a solid UI kit that lets you work at different levels of abstraction (components, theme parameters, utility classes, raw CSS or CSS-in-JS) and already has all the major components you're going to need. That's why MUI comes with this project.

#### Why is Cypress not included?

Because ugh. Every project I've ever worked on using Cypress has like five e2e tests, four of them failing and one false positive.

#### Bundle size?

I don't care about bundle size. Hopefully we can still be friends.

## Known Issues

I haven't written any of the code yet, so there's that.

## Contributing

Please contribute if you feel led.
