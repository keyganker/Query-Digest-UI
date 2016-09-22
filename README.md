Query-Digest-UI
====

This is a advanced, but easy to install, ui for [pt-query-digest](http://www.percona.com/doc/percona-toolkit/pt-query-digest.html) or [mk-query-digest](http://www.maatkit.org/doc/mk-query-digest.html).

Features
====
-   Dynamic filtering and searching of queries
-   Colorized and normalized SQL syntax
-   Explain the query dynamically
-   Integrated [pt-query-advisor](http://www.percona.com/doc/percona-toolkit/2.0/pt-query-advisor.html) support
-   Detailed query historic stats, support for [log_slow_verbosity](http://www.percona.com/doc/percona-server/5.5/diagnostics/slow_extended_55.html#log_slow_verbosity).

Requirements
====
Apache, mod_php, php_pdo

Install
====
Clone to a docroot, copy config.php.example to config.php and edit.
Head to the root url in your browser and away you go!

Import slow log
====
pt-query-digest --user={username} --password={password} --review h={db host},D=slow_query_log,t=global_query_review --history h={db host},D=slow_query_log,t=global_query_review_history --no-report --limit=0% --filter=" \$event->{Bytes} = length(\$event->{arg}) and \$event->{hostname}=\"$HOSTNAME\"" {PATH_TO_SLOW_LOG}

