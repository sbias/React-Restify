#React-Restify 
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/CapMousse/React-Restify/badges/quality-score.png?s=6d1986dbc42d5fc5a1e23134896b284797de29b0)](https://scrutinizer-ci.com/g/CapMousse/React-Restify/)

This fork accepts json instead of form-encoded post and put data

> RESTful api made easy for [ReactPHP](http://nodephp.org/), seriously.

##Instalation
In your `composer.json`

    "require"       : {
        "capmousse/react-restify": "dev-master"
    },


##Create server

Here is an exemple of a simple HTTP server replying to all get call like `http://127.0.0.1:1337/hello/you`

```php
require 'vendor/autoload.php';

$server = new CapMousse\ReactRestify\Server("MyAPP", "0.0.0.1");

$server->get('/hello/{name}', function ($request, $response, $next) {
    $response->write("Hello ".$request->name);
    $next();
});

$runner = new CapMousse\ReactRestify\Runner($server);
$runner->listen(1337);
```

More examples can be found on the example directory like the **Todo** example, the most complete

## Design goals

*React-Restify* was primary made to build RESTful api easily. It can be used like *Silex*, but without the framework part.

Next part will be to support Sockets, Upgrade Requests... to create a real time API server.

##Licence

MIT, see LICENCE file
