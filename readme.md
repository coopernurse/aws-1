Overview
========

Provides [Racket](http://www.racket-lang.org) support for many [Amazon
Web Services](http://aws.amazon.com/documentation/):

* [S3 storage](http://docs.amazonwebservices.com/AmazonS3/latest/dev/Welcome.html).

* [SimpleDB database](http://docs.amazonwebservices.com/AmazonSimpleDB/latest/DeveloperGuide/Welcome.html).

* [SES email](http://docs.amazonwebservices.com/ses/latest/DeveloperGuide/Welcome.html).

* [SNS notification](http://docs.amazonwebservices.com/sns/latest/api/Welcome.html?r=9480).

* [SQS queues](http://docs.amazonwebservices.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/Welcome.html).

* [CloudWatch monitoring](http://docs.amazonwebservices.com/AmazonCloudWatch/latest/DeveloperGuide/Welcome.html).

* [Glacier
  archiving](http://docs.amazonwebservices.com/amazonglacier/latest/dev/introduction.html). _New in v1.3, 2012-08-30_

* [Authorization signature version 4](http://docs.amazonwebservices.com/general/latest/gr/signature-version-4.html).  _New in v1.3, 2012-08-30_

* [Route 53](http://docs.amazonwebservices.com/Route53/latest/APIReference/Welcome.html). _New in v1.4, 2012-11-26_

* [Dynamo](http://docs.amazonwebservices.com/amazondynamodb/latest/developerguide/Introduction.html). _New in v1.4, 2012-11-26_


Documentation
=============

* [HTML format on pkg-build.racket-lang.org](http://pkg-build.racket-lang.org/doc/aws/index.html).

* [Markdown format on GitHub](https://github.com/greghendershott/aws/blob/master/aws/manual.md).

Requirements
============

* The access keys for an Amazon Web Services account. (If you want to
  experiment but are concerned about cost, keep in mind that AWS has a
  "free tier" for certain usage.)

* My `http` library. Install: `raco pkg install
  http`. [Source](https://github.com/greghendershott/http).

* My `sha` library. Install: `raco pkg install
  sha`. [Source](https://github.com/greghendershott/sha)

Unit tests
==========

To simply use the library you don't need to run the unit tests. But if you
want to run them:

* The tests require you to specify certain personal information in a dot
  file. See
  [example-dot-aws-tests-data](https://github.com/greghendershott/aws/blob/master/tests/example-dot-aws-tests-data)
  for more information.

* The `rackunit` tests use the submodule feature added in Racket 5.3. Tests are
  inside `(module+ test ...)` forms.

  * You can run the tests for one `foo.rkt` file with `raco test foo.rkt`.

  * You can run tests for all files using `raco test -x ./`.  (The `-x` flag is
    important to avoid evaluating rkt files that have no `test` module
    whatsoever.)

* Be aware that the tests are extensive and will do significant data
  transfer with Amazon AWS. Although this shouldn't cost a _lot_ of
  money, it will take some time for them to complete.
