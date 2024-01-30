# wishlist

* internal, built-in pubsub like `ActiveSupport::Notifications` without external dependencies

    * enables logger
    * enables test-framework integration
    * enables instrumentation
    * internal code as pubsub consumers

* external pubsub via outbox mechanism

    * hook in rabbitmq, kafka, etc.
    * would be interesting to see if Atom-like consumer 
      fits this usecase as well (IDDD)

* persistent projections as external process or in-process threads

    * first-class support for read models — catchup, rebuild
    * no need for external system to enable asynchronous event handlers

* concurrent synchronous handlers

    * perform Thread.join or Pool.wait_for_termination
    * simillar to asynchronous in lack of handler ordering, 
      however ordering to be achieved by reducing concurrency to 1

* postgres only, driven by server-side functions, constraints and procedures

    * taking https://github.com/message-db/message-db/tree/master/database approach to SQL
    * tested with `pgt`

* sorbet types with mutation testing to reduce test ratio

    * minitest as a non-rspec, mutant-friendly framework
    * units stubbed at database driver layer — `pg`
    * integration test suite as a safety net

* release automation

    * build and push releases in CI
    * prepare release note stubs automatically

* benchmarking from day one on a reasonable data set

    * releases dont introduce performance regressions
    * probably needs a dedicated machine

* deleting events as a valid operation 

    * sane way to cleanup old, uneeded events — experiments, backups or closed periods

* current Ruby only

    * smaller CI pipelines, less distractions
    * older versions via business inquiry or community forks

* correlation, causation, by_type, by_some_attribute out of the box and without leaking implementation detauils to the end user

    * start as queries
    * optimize further (i.e.to linked streams if queries not enough)

* any-temporal — have as many indexed timestamps as you wish

* validate with non-Ruby implementation

    * Haskell would be fn to implement

* expect framework implemented on top some day, dont be one

    * pierogi-rails as a typical RailsWay plug-in
    * pierogi-śmietana as a set of some practices, i.e. bring decider or aggregate_root, processes DSL, browser, etc.
    * pierogi-res as an API compatibility layer, provided data has such compatibility layer too in form of SQL views, etc.

* CLI diagnostic interface

    * includes environment and setup information
    * mandatory for bug reports
    * optional telemetry — send your setup anonymously to remote web endpoint


