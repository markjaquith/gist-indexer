# Gist Indexer

Does a `git clone` of all your GitHub gists, both public and private. Now you can have a local archive of all of them, and can search them using command line tools like `awk`.

Unfortunately, this requires a slurp of the gist.github.com site, as the API does not currently give information about your private gists.

## Requirements

* PHP 5.2
* Git
* Github Account
* Knowledge of how to grab cookie values from your browser

## Instructions

1. Grab your `_gh_sess` cookie value. You're on your own here.
2. `export` that cookie value into `GIST_SESSION`: `export GIST_SESSION='{session_value_here}'`.
3. From the directory that you want to house your gist archive, run the `gist-indexer` script.

## More Info

* If the directory doesn't exist, it'll get a `git clone`.
* If the directory does exist, it'll get a `git pull`.
* If you get 'Bad session value', then you'll have to go log in again and grab a fresh session value.

## FAQ

### Is this against the GitHub terms of service?

I am not a lawyer, but my reading of their [terms of service][tos] does not appear to forbid this sort of limited, targeted scraping (it's just scraping **your** data, after all). It would be wonderful if they'd update the Gist API to 
support discovery of private gists. Until then, this will have to do.

[tos]: http://help.github.com/terms-of-service/

### Will you make it so that I don't have to manually enter the session value?

No. That would require storing of your GitHub username and password. I don't want to do that.

## License & Copyright

Gist Indexer is Copyright Mark Jaquith 2012, and is offered under the terms of the GNU General Public License, version 2, or any later version.
