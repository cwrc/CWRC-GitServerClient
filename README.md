![Picture](http://www.cwrc.ca/wp-content/uploads/2010/12/CWRC_Dec-2-10_smaller.png)

# CWRC-GitServerClient

[![Travis](https://img.shields.io/travis/jchartrand/CWRC-GitServerClient.svg)](https://travis-ci.org/jchartrand/CWRC-GitServerClient)
[![Codecov](https://img.shields.io/codecov/c/github/jchartrand/CWRC-GitServerClient.svg)](https://codecov.io/gh/jchartrand/CWRC-GitServerClient)
[![version](https://img.shields.io/npm/v/cwrc-git-server-client.svg)](http://npm.im/cwrc-git-server-client)
[![downloads](https://img.shields.io/npm/dm/cwrc-git-server-client.svg)](http://npm-stat.com/charts.html?package=cwrc-git-server-client&from=2015-08-01)
[![GPL-2.0](https://img.shields.io/npm/l/cwrc-git-server-client.svg)](http://opensource.org/licenses/GPL-2.0)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)



1. [Overview](#overview)
1. [Demo](#demo)
1. [Installation](#installation)
1. [Use](#use)
1. [API](#api)

### Overview

Makes http calls to the [CWRC-GitServer](https://github.com/cwrc/CWRC-GitServer), typically invoked from [CWRC-GitDelegator](https://github.com/jchartrand/CWRC-GitDelegoator) running in[CWRC-GitWriter](https://github.com/cwrc/CWRC-GitWriter). 

### Demo 

The [CWRC GitHub Sandbox](http://208.75.74.217/editor_github.html) uses the NPM package published from this repository along with the code in [CWRC-Writer](https://github.com/jchartrand/CWRC-Writer), [CWRC-GitServer](https://github.com/jchartrand/CWRC-GitServer), [CWRC-GitWriter](https://github.com/jchartrand/CWRC-GitWriter), and [CWRC-GitDelegator](https://github.com/jchartrand/CWRC-GitServer). The same code is easily (for someone with modest development experience) installed on any server to run your own instance.

### Installation

`npm install cwrc-git-server-client`   

To simultaneously register as a dependency in your package.json:

`npm install cwrc-git-server-client --save`   

or in shortcut form:

`npm i -S cwrc-git-server-client`

### Use

One example:

var cwrcGitServerClient = require('cwrc-git-server-client');
var repos = cwrcGitServerClient.getReposForAuthenticatedGithubUser();

The spec directory contains specifications (tests) that can help better understand the API. Also see [CWRC-GitDelegator](https://github.com/jchartrand/CWRC-GitDelegoator) which fully uses the API.

### API

The methods exposed (API) by this package are:

```
	createCWRCRepo(repoName, description, isPrivate, theDoc, annotations, versionTimestamp)

	getReposForGithubUser(githubName)

    getReposForAuthenticatedGithubUser()

    saveDoc(repo, owner, parentCommitSHA, baseTreeSHA, docText, versionTimestamp)

    getDoc(repoName)

    getInfoForAuthenticatedUser()

```