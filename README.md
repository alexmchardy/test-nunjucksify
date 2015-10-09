This repo is just to demo an issue I'm seeing with the browserify transform [nunjucksify](https://github.com/rotundasoftware/nunjucksify).

Browserify hangs when using `nunjucksify`, if it is run from a directory that contains a file or directory named `views`.

To see the issue yourself:
```
git clone git@github.com:alexmchardy/test-nunjucksify.git
cd test-nunjucksify
npm install
./node_modules/.bin/browserify simple.nunj -t nunjucksify
```

##### Expected
Browserify outputs the transformed code to `stdout` and exits.

##### Actual
Browserify outputs the transformed code to `stdout` *but never exits*.
