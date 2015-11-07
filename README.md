# testing Composer subdir (using github svn support)

## Problems

composer.json have to put top level of the repository. this is little bit hard to maintain multiple
programming language proejct.
Github supports svn access. svn could checkout child directory directly.
you can put composer.json on child directory if you use this svn behaviour.


## Solution

```
{
	"repositories": [
		{
			"type": "svn", <-- don't put vcs due to prevent git autodetection
			"url": "https://github.com/chobie/composer-test",
			"trunk-path": "trunk/a", <-- choose sub directory which contains composer.json
			"branches-path": false,
			"tags-path": false
		}
	],
	"require": {
		"chobie/composer-test": "dev-master"
	}
}
```