[![Build Status](https://travis-ci.org/Instrumental/instrumental_agent-node.svg?branch=master)](https://travis-ci.org/Instrumental/instrumental_agent-node)


# Instrumental Node.js Agent

Instrumental is a [application monitoring platform](https://instrumentalapp.com) built for developers who want a better understanding of their production software. Powerful tools, like the [Instrumental Query Language](https://instrumentalapp.com/docs/query-language), combined with an exploration-focused interface allow you to get real answers to complex questions, in real-time.

This agent supports custom metric monitoring for Node.js applications. It provides high-data reliability at high scale, without ever blocking your process or causing an exception.

## Installation

````shell
npm install instrumental_agent
````

Package details on [npmjs.com](https://www.npmjs.com/package/instrumental_agent)

## Usage

You will need to set the API token. API tokens can be found in the [project tokens documentation](https://instrumentalapp.com/docs/tokens) or in your user settings page. Use the 'enabled' flag to control if the agent actually reports. This is useful for not reporting in dev/test/staging/etc. environments.

````javascript
var I = require('instrumental_agent);
I.configure({
  // from here: https://instrumentalapp.com/docs/tokens
  apiKey:  'project_token',

  // optional, default shown
  host:    'collector.instrumentalapp.com',

  // optional, default shown
  enabled: true,
});

// increments
I.increment('metric.name' /*, value = 1, time = now, count = 1 */);

// gauges
I.gauge('metric.name', 82.12 /*, time = now, count = 1 */);

// notices
I.notice('An event occurred' /*, time = now, duration = 0 */);
````


# Contributing

Make a PR! Say roughly what you've changed, why you did so, and any ancillary data you have like gotchas, issues you suspect, awesomeness, etc.

## Run the Tests and other Helpers

```
> npm install
> npm test # this should be all green
> npm run coverage # this should probably be like… as good as when you started
> npm run jshint # ??? I guess no errors? not sure what this does
```

# Releasing

1. Sign up for npmjs.com
2. Pull latest master
3. Merge feature branch(es) into master
4. `npm test`
5. Increment version in repo
  - `package.json`
6. Update [CHANGELOG.md](CHANGELOG.md)
7. Commit "Release version vX.Y.Z"
8. Push to GitHub
9. `npm publish`
10. Tag version: `git tag 'vX.Y.Z' && git push --tags`
11. Verify update on https://www.npmjs.com/package/instrumental_agent
12. Refresh documentation on instrumentalapp.com

# Cool Contributors :sunglasses:

* @spacetc62
* @gmcnaught
* @janxious
* @jqr
* @jason-o-matic
* @JamesPaden
