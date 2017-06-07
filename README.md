
### Getting a ceiling fan spinning

Let's assume we're running locally for now:

- we'll be using [`concourse/lite`](http://concourse.ci/vagrant.html),
  so first [get vagrant](https://www.vagrantup.com/)
- then

  ```sh
     # cd concourse-multi-image
     # vagrant up
  ```

- in a browser go to <http://192.168.100.4:8080> (by default)
- download `fly` and somehow have it findable on your `PATH`, e.g. move to `/usr/local/bin`
- add your concourse lol: `fly -t lite login -c http://192.168.100.4:8080`

### Watching the fan spin

```sh
   # fly -t lite set-pipeline -p hello -c hello.yml
   # fly -t lite unpause-pipeline -p hello
   # fly -t lite trigger-job -j hello/hello-world
```

Honestly though it's more fun to play with the subcommands since incrementally responding to the error output leads to a valid constructed command