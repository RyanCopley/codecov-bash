Codecov Global Uploader
=======================
> Upload reports to Codecov for all supported languages.


### Simply

```bash
bash <(curl -s https://codecov.io/bash)
```

### CI Companies Supported
|                       Company                       |                                                               Supported                                                               | Tokens Required  |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| [Travis CI](https://travis-ci.org/)                 | Yes [![Build Status](https://secure.travis-ci.org/codecov/codecov-bash.svg?branch=master)](http://travis-ci.org/codecov/codecov-bash) | Private only     |
| [CircleCI](https://circleci.com/)                   | Yes [![Circle CI](https://img.shields.io/circleci/project/codecov/codecov-bash.svg)](https://circleci.com/gh/codecov/codecov-bash)    | Private only     |
| [Codeship](https://codeship.com/)                   | Yes                                                                                                                                   | Public & Private |
| [Jenkins](https://jenkins-ci.org/)                  | Yes                                                                                                                                   | Public & Private |
| [Semaphore](https://semaphoreci.com/)               | Yes                                                                                                                                   | Public & Private |
| [drone.io](https://drone.io/)                       | Yes                                                                                                                                   | Public & Private |
| [AppVeyor](http://www.appveyor.com/)                | Yes                                                                                                                                   | Public & Private |
| [Wercker](http://wercker.com/)                      | Yes                                                                                                                                   | Public & Private |
| [Magnum CI](https://magnum-ci.com/)                 | Yes                                                                                                                                   | Public & Private |
| [Shippable](http://www.shippable.com/)              | Yes                                                                                                                                   | Public & Private |
| [Gitlab CI](https://about.gitlab.com/gitlab-ci/)    | Yes                                                                                                                                   | Public & Private |
| [snap ci](https://snap-ci.com_)                     | Yes                                                                                                                                   | Public & Private |
| git                                                 | Yes (as a fallback)                                                                                                                   | Public & Private |
| [Buildbot](http://buildbot.net/)                    | `coming soon` https://github.com/buildbot/buildbot/pull/1671                                                                          |                  |
| [Bamboo](https://www.atlassian.com/software/bamboo) | `coming soon`                                                                                                                         |                  |
| [Solano Labs](https://www.solanolabs.com/)          | `coming soon`                                                                                                                         |                  |

> Using Travis CI? Settings `sudo: false` may speed up your builds and still works with this uploader.

### More Options

```
CODECOV_TOKEN   Private repo token for uploading
CODECOV_ENV     List of config vars that are stored for this build
CODECOV_URL     Enterprise url
CODECOV_SLUG    Repository slug (ex "owner/repo") used in Enterprise instead of private repo token
```

```yaml
# .travis.yml example
env:
  global:
    - CODECOV_TOKEN=9dcefbad-1cef-4895-8fb7-a90cf4737904
    - CODECOV_ENV=KEEP,THESE,ENV,VALUES
    - CODECOV_URL=https://your-enterprise.com
    - CODECOV_SLUG=myteam/myrepo

after_success:
  - bash <(curl -s https://codecov.io/bash)
```

#### One line

```bash
curl -s https://codecov.io/bash | bash /dev/stdin -t 15482e9c-3612-4812-b19b-f5e79139dfe3
```
