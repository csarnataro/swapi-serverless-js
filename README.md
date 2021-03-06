# SWAPI serverless

>   A porting of [swapi.co](https://swapi.co) using a JAMStack architecture,
    with JavaScript serverless functions (implemented through [fastify](https://fastify.io)) for the JSON APIs and Next.js 
    statically generated pages for the front-end.

### Goals
1.  Achieve feature parity of original swapi.co (unmaintained) or 
    [swapi.dev](https://swapi.dev) API, but using a JAMStack architecture, 
    with back-end logic implemented by serverless lambda functions

2.  Restore the original swapi.co site or build a brand new swapi site, possibly 
    hosted on [Netlify](www.netlify.com)

### Data
All the data are loaded at request time from JSON fixture files, copied from 
the original repo https://github.com/phalt/swapi/tree/master/resources/fixtures.

In addition to that, some data coming from open PRs on the original unmaintained
repo have been added manually (e.g. some data regarding the 7th film of the 
saga, *The Force Awakens*).

Of course, in a real world application, data would be stored and fetched
from a datastore (a RDBMS or a NoSQL database like MongoDB or FaunaDB).

In the original project (based on Django framework), those JSON files were
intended to be loaded into a database by using the python utility `loaddata`.

But due to the limited amount of data to manage, we're not using any database,
on purpose. Instead we're loading and manipulating the needed information at 
request time, with apparently no visible delay (a benchmark would be helpful, 
though).

Updates to the data will be done directly in the fixture files. 
(Please open a PR if you find some error or missing data)

### How to run it locally
Run it locally with:
```
npm run dev
```

Navigate to `http://localhost:4000/api/films` for the JSON APIs

Navigate to `http://localhost:3000/` for the human-friendly frontend

### Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

We're using [commitizen](https://github.com/commitizen/cz-cli) to enforce 
[conventional commits](https://www.conventionalcommits.org/en/v1.0.0/).

This means that when you're ready to commit you should use 

``` bash
npm run commit
```

### Tests

```
npm run test
```

