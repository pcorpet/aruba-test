This container makes it easy to run your
[Aruba](https://github.com/cucumber/aruba) on [Cucumber](https://cucumber.io)
tests without installing anything but Docker.

# Usage

Mount your features in the `/test` folder of the image and run it:

``` bash
docker run --rm -v features:/test/features lascap/aruba-test
```

Note that your `features` folder needs to contain a `features/support/aruba.rb`
that just contains:

``` ruby
require 'aruba/cucumber'
```

## Configuration

If you want to configure it more, you can add `cucumber.xml` file in the
`/test` folder or update the image as you see fit.
