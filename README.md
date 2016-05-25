JIRA API Ruby Gem
===============================

Forked from [jira-ruby](https://github.com/sumoheavy/jira-ruby)

> By default, both JIRA issue navigator and REST API return a maximum of 1000 search results.

So this version fix this limitation when using `jql` to retrieve all the issues.

## Note:
When encounter the following SSL issue, 
```
`connect': SSL_connect returned=1 errno=0 state=SSLv3 read serv
er certificate B: certificate verify failed (OpenSSL::SSL::SSLError)
```
The solution is add the `:ssl_verify_mode => OpenSSL::SSL::VERIFY_NONE` to the options, e.g.
```
options = {
            :username => username,
            :password => password,
            :site     => site_url,
            :context_path => '/',
            :auth_type => :basic,
            :ssl_verify_mode => OpenSSL::SSL::VERIFY_NONE,
            :read_timeout => 120
          }
```