# Adonis Mail 📩

This repo is a AdonisJs provider to send emails using one of the available drivers, or by writing your own driver.

It uses [node mailer](https://nodemailer.com) internally to parse and send emails.

[![NPM Version][npm-image]][npm-url]
[![Build Status][travis-image]][travis-url]
[![Appveyor][appveyor-image]][appveyor-url]
[![Coveralls][coveralls-image]][coveralls-url]

<img src="http://res.cloudinary.com/adonisjs/image/upload/q_100/v1497112678/adonis-purple_pzkmzt.svg" width="200px" align="right" hspace="30px" vspace="140px">

## What's in the box?

This repo contains following providers.

1. Consistent API to send email
2. Support for multiple drivers include **smtp**,**sparkmost**,**mailgun**,**amazon ses** etc.
3. API to add your own drivers
4. Write email content inside Edge templates.

## Node/OS Target

This repo/branch is supposed to run fine on all major OS platforms and targets `Node.js >=7.0`

## Development

Great! If you are planning to contribute to the framework, make sure to adhere to following conventions, since a consistent code-base is always joy to work with.

Run the following command to see list of available npm scripts.

```
npm run
```

## Environment Variables

There is a `.env.example` file in the project root, rename it as `.env` and add values for all services to run tests on your local. 

DO MAKE SURE TO NOT COMMIT THE `.env` FILE.

### Tests & Linting

1. Lint your code using standardJs. Run `npm run lint` command to check if there are any linting errors.
2. Make sure you write tests for all the changes/bug fixes.
3. Also you can write **regression tests**, which shows that something is failing but doesn't breaks the build. Which is actually a nice way to show that something fails. Regression tests are written using `test.failing()` method.
4. Make sure all the tests are passing on `travis` and `appveyor`.

### General Practices

Since Es6 is in, you should strive to use latest features. For example:

1. Use `Spread` over `arguments` keyword.
2. Never use `bind` or `call`. After calling these methods, we cannot guarantee the scope of any methods and in AdonisJs codebase we do not override the methods scope.
3. Make sure to write proper docblock.

## Issues & PR

It is always helpful if we try to follow certain practices when creating issues or PR's, since it will save everyone's time.

1. Always try creating regression tests when you find a bug (if possible).
2. Share some context on what you are trying to do, with enough code to reproduce the issue.
3. For general questions, please create a forum thread.
4. When creating a PR for a feature, make sure to create a parallel PR for docs too.


## Regression Tests

Regression tests are tests, which shows how a piece of code fails under certain circumstance, but the beauty is even after the failure, the test suite will never fail. Actually is a nice way to notify about bugs, but making sure everything is green.

The regression tests are created using

```
test.failing('2 + 2 is always 4, but add method returns 6', (assert) => {
 assert.true(add(2, 2), 4)
})
```

Now since the `add` method has a bug, it will return `6` instead of `4`. But the build will pass.

[appveyor-image]: https://img.shields.io/appveyor/ci/thetutlage/adonis-mail/master.svg?style=flat-square

[appveyor-url]: https://ci.appveyor.com/project/thetutlage/adonis-mail

[npm-image]: https://img.shields.io/npm/v/@adonisjs/mail.svg?style=flat-square
[npm-url]: https://npmjs.org/package/@adonisjs/mail

[travis-image]: https://img.shields.io/travis/adonisjs/adonis-mail/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/adonisjs/adonis-mail

[coveralls-image]: https://img.shields.io/coveralls/adonisjs/adonis-mail/develop.svg?style=flat-square

[coveralls-url]: https://coveralls.io/github/adonisjs/adonis-mail
