# java-prototype

Owner: Kris Nova

Author: Kris Nova [Github][5]


# Overview

`java-prototype` simulates a troublesome monolithic Java application that is designed to be hard to orchestrate in containers.

# Install

Installing with maven

```bash
./mvnw clean package
```

Want to upgrade the version of maven used by the maven wrapper?

```bash
./mvnw -N io.takari:maven:wrapper -Dmaven=3.5.2
```

Also for a quick development run the following command to build and run the application.

```bash
make dev
```

# Configuring

### MySQL

There are three environmental variables that need to be defined in order to authenticate with a MySQL server.

```bash
export JAVAPROTOTYPE_MYSQL_CONNECTION_STRING="jdbc:mysql://my.server.url/database"
export JAVAPROTOTYPE_MYSQL_CONNECTION_USER="user"
export JAVAPROTOTYPE_MYSQL_CONNECTION_PASS="password"
```

# Containerization

AWS: Include `buildspec.yml` in a CodeBuild object linking your clone or fork of this repo.  Replace the four variables with the correct data for your project:
1. $AWS_DEFAULT_REGION
1. $IMAGE_REPO_NAME
1. $IMAGE_TAG
1. $AWS_ACCOUNT_ID

An image must exist in $IMAGE_REPO_NAME (it can be scratch or any placeholder.  A successful build will overwrite the image).  Follow directions [here](https://docs.aws.amazon.com/codebuild/latest/userguide/getting-started.html) if this is your first time using AWS CodeBuild.

# Troubleshooting

If you encounter any problems that the documentation does not address, [file an issue][3] or talk to us on the [Kubernetes Slack team][4] channel `#monolith`.

# Contributing

Thanks for taking the time to join our community and start contributing!

Feedback and discussion is available on [the mailing list][2].

* Please familiarize yourself with the [Code of Conduct][0] before contributing.
* See [CONTRIBUTING.md][1] for instructions on the developer certificate of origin that we require.


# Changelog

[0]: https://github.com/heptio/java-prototype/CODE-OF-CONDUCT.md
[1]: https://github.com/heptio/java-prototype/CONTRIBUTING.md
[2]: https://groups.google.com/forum/#!forum/monolithic-apps-to-k8s
[3]: https://github.com/heptio/java-prototype/issues
[4]: http://slack.kubernetes.io/
[5]: https://github.com/kris-nova/
