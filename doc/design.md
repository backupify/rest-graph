
# Design

## Introduction

rest-graph is a lightweight Facebook Graph API client.  By lightweight, it
means it's modular and compact, and only provides essential functionality.
It's designed to be transparent to Facebook Graph API, so it doesn't try to
fix Facebook's bugs nor inconsistency problems.  People should be able to
read Facebook's documentation (though sometimes it's not quite helpful) in
order to use rest-graph, instead of learning how rest-graph would work.
(of course, Ruby experience is required.)

In other words, before starts, you might need to know how Facebook's Graph
API works, for example, how to fetch data, how to do authentication, etc.
Here's the links:

* Graph API: <http://developers.facebook.com/docs/reference/api>
* Authentication: <http://developers.facebook.com/docs/authentication>

For advanced usage, you might want to read the followings, too:

* FQL: <http://developers.facebook.com/docs/reference/fql>
* Old REST API: <http://developers.facebook.com/docs/reference/rest>

Since rest-graph is trying to be transparent to Facebook Graph API, some
might find it's not so useful because of Facebook's bugs or inconsistency
problems.  This might be a disadvantage comparing to others client libraries
which mimic the issues for you, but the advantage would be for people who
have already known how Facebook Graph API works, say, people who used to
develop Facebook Apps with PHP or any other tools, could easily know how to
use rest-graph with their old knowledges.  On the other hand, if Facebook
fixed their bugs or inconsistency problems, you don't need to wait for
rest-graph fixing the problems.  You will directly depend on Facebook,
but not depend on rest-graph which depends on Facebook.  More layers,
more problems.  rest-graph is a client library, but not Facebook framework.

Still, if the inconsistency problems are very obvious and would not change
in the near future, for example, `oauth/access_token` API would not return
a JSON as typical Graph APIs do, instead, it returns a query string as in
URL.  In this case, rest-graph uses `Rack::Utils.parse_query` to parse the
query for you.  If you feel there are more cases rest-graph should handle
like this, please feel free to file a ticket on our issue tracker on Github.

* <https://github.com/cardinalblue/rest-graph/issues>

Or you could start a topic on our mailing list:

* <http://groups.google.com/group/rest-graph/topics>

Either one is welcomed.

## Name

rest-graph is named after the first dependency rest-client.

## License

rest-graph is licensed under Apache License 2.0.

## Target Usage and Structure [TODO]

* config_util.rb
* rails_util.rb
* test_util.rb
* facebook_util.rb