solas-chart
-----------

`solas-chart` is scaffolding for new chart repositories hosted by Samsung CNCT. It implements our best practices, such as one chart per repo, seperate repos for charts and container images (see https://github.com/samsung-cnct/solas-chart), CI for all the things, and so on.

SOLAS is also an international maritime treaty to ensure ships comply with minimum safety standards in construction, equipment and operation.

# Quickstart

- The name of chart repos should be of the form `chart-${NAME}`. For example, `chart-sample` is the name of the chart which installs an application named `sample`.
- [Create](https://help.github.com/articles/creating-a-new-repository/) a new empty repo under the `samsung-cnct` [org](https://github.com/samsung-cnct) using the GitHub GUI, for example https://github.com/samsung-cnct/chart-sample .
- [Duplicate](https://help.github.com/articles/duplicating-a-repository/) this repo (https://github.com/samsung-cnct/solas-chart) and push it to the `chart-sample` repo you created in the previous step. Note the arguments to clone and push.

```
git clone --bare https://github.com/samsung-cnct/solas-chart.git
cd solas.git
git push --mirror https://github.com/samsung-cnct/chart-sample.git
cd ..
rm -rf solas-chart.git
```

- [Fork](https://help.github.com/articles/fork-a-repo/) the `chart-sample` repo (https://github.com/samsung-cnct/chart-sample) and begin submiitting PRs.

# Copy in your source chart

Create a subdirectory with the name of your chart (eg sample-chart) in which you put the contents of your chart.

# What to do next?

- You should configure CI/CD by following the instructions for [GitHub](https://github.com/samsung-cnct/solas-chart/blob/master/docs/github.md), [Jenkins](https://github.com/samsung-cnct/solas-chart/blob/master/docs/jenkins.md), and [Quay](https://github.com/samsung-cnct/solas-chart/blob/master/docs/quay.md).

- You may want to update the teams [Slack notifications](https://samsung-cnct.slack.com/apps/search?q=github) to notify developers of PR and issue activiy. To do this you will need [Admin Privileges](https://help.github.com/articles/repository-permission-levels-for-an-organization/). To ensure that you are not the only one who can maintain these integrations, it is recommended that you grant a GitHub Team (e.g. `commontools`) permissions and not a single individual contributor.

- If your project will be administered by a GitHUb team (e.g. `commontools`), you will need to contact an owner of the `samsung-cnct` organization so they can grant the `commontools` team admin privileges. Reachout in the `#cnct-dev` or `#team-tooltime` Slack channels.

# Best Practices

> Group related objects into a single file whenever it makes sense. One file is often easier to manage than several.

> Define and use labels that identify semantic attributes of your application or deployment. [For example,] `{ app: myapp, tier: frontend, phase: test, deployment: v3 }`.

 - [Configuration Best Practices](https://kubernetes.io/docs/concepts/configuration/overview/)

