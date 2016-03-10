This container makes it easy to run your
[Aruba](https://github.com/cucumber/aruba) on [Cucumber](https://cucumber.io)
tests without installing anything but Docker.

# Usage

Mount your features in the `/test` folder of the image and run it:

``` bash
docker run --rm -v $(realpath features):/test/features -t lascap/aruba-test
```

Note that your `features` folder needs to contain a `features/support/aruba.rb`
that just contains:

``` ruby
require 'aruba/cucumber'
```

## Configuration

If you want to configure it more, you should extend the image so that you can add a `cucumber.xml` file or a more complex setup. Create a new `Dockerfile`:

``` dockerfile
FROM lascap/aruba-test

# Add our specific Cucumber options.
ADD cucumber.xml /test
```
