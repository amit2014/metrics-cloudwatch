# Metrics for CloudWatch
Sends [Metrics](https://github.com/codahale/metrics/) reporting to [Amazon's CloudWatch](http://aws.amazon.com/cloudwatch/).

This is Appuri's fork of Plausible Labs' [metrics-cloudwatch](https://github.com/plausiblelabs/metrics-cloudwatch)
CloudWatch reporter for Dropwizard. There are a few enhancements in this fork:

- Enable support for IAM instance profiles.
- Push Maven releases to Github

## Pushing a release to Github

Our release process is inspired by [this Stackoverflow answer](http://stackoverflow.com/questions/14013644/hosting-a-maven-repository-on-github).
Follow these steps:

- Make sure your Maven `settings.xml` is NOT world-readable by running `chmod 700 ~/.m2/settings.xml`
- Update your `settings.xml`:

```
<settings>
  <servers>
    <server>
      <id>github</id>
      <username>YOUR-USERNAME</username>
      <password>YOUR-PASSWORD</password>
    </server>
  </servers>
</settings>
```
- Prepare the release using `mvn clean deploy` and `mvn release:prepare`
- Perform the release using `mvn release:perform`
