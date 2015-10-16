Description
===========

An OpenShift cartridge for installing Hubot

Installation
============

* With the OpenShift command line tools:

```
$ rhc app create hubot nodejs-0.10 http://cartreflect-claytondev.rhcloud.com/reflect?github=smarterclayton/openshift-redis-cart --from-code=https://github.com/inercia/hubot-openshift
```

* Create the new Hubot integration by going to https://my.slack.com/services/new/hubot

* Set the Slack token with

```
$ rhc env set HUBOT_SLACK_TOKEN=xoxb-1234-5678-91011-00e4dd -a hubot
```


Testing your bot locally
------------------------

`cd` to the `checkout` directory and run:

```
$ HUBOT_SLACK_TOKEN=xoxb-1234-5678-91011-00e4dd ./bin/hubot --adapter slack
```

Configuration
=============

`HUBOT_SLACK_TOKEN` - this is the API token for the Slack user you would like to run Hubot under.

To add or remove your bot from specific channels or private groups, you can use the /kick and /invite slash commands that are built into Slack.

Installing additional Hubot scripts
===================================

Look for a new script [here](https://github.com/hubot-scripts). In this example, we will install `hubot-standup-alarm`

Then `cd` to the `checkout` directory and run:

```
$ npm install hubot-standup-alarm --save
```

Enable the script by adding the name to the `external-scripts.json` file (you may need to create this file).
For example:

```
  ["hubot-standup-alarm"]
```

Do a ' npm install`, `git commit` && `git push`

You can also install scripts from [here](https://github.com/github/hubot-scripts/tree/master/src/scripts) by adding then to `hubot-scripts.json`
