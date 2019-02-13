![Bonsai - Hosted Elasticsearch](bonsai-logo.png)

## Kibana Supported on Bonsai

You can now easily launch Kibana your Bonsai cluster dashboard if your cluster's Elasticsearch version >= v5.

---

![Kibana](kibana.png)

Run Kibana 5 or 6 on Heroku with one click. Brought to you by [Bonsai: Hosted Elasticsearch](https://bonsai.io/).

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/omc/heroku-kibana)

## Note on Kibana 5.x

Version 5.x of Kibana has changed its authentication requirements. Cluster credentials need to be entered to access the Kibana dashboard. Bonsai clusters are provisioned with HTTP Basic Auth credentials by default, and these need to be provided to Kibana when it is loaded into a browser.

The username and password are made available when the app is created, in the build log. The credentials can also be found by running `heroku config:get BONSAI_URL -a <app_name>`, or by looking in the Heroku dashboard. The credentials in `BONSAI_URL` are of the form `https://user:pass@some-slug.some-region.bonsai.io`

OSX/BSD users can use the following snippet to extract the username and password easily:

```
heroku config:get BONSAI_URL -a <app_name> | sed -E 's/.*:\/\/([a-zA-Z0-9]{1,}):([a-zA-Z0-9]{1,})@.*/Username: \1@Password: \2/' | tr '@' '\n'
```

The GNU equivalent would be:

```
heroku config:get BONSAI_URL -a <app_name> | sed -r 's/.*:\/\/([a-zA-Z0-9]{1,}):([a-zA-Z0-9]{1,})@.*/Username: \1@Password: \2/' | tr '@' '\n'
```
