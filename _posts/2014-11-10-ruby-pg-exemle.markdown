---
layout: post
title:  "ruby db  学习 "
date:   2014-10-10 09:28:51
categories: wiki
---

## ruby 操作pg 的demo
```ruby 
 
    #!/usr/bin/env ruby  
    require 'pg'
    # Output a table of current connections to the DB
    conn = PG.connect( dbname: 'sales' )
    conn.exec( "SELECT * FROM pg_stat_activity" ) do |result|
      puts "     PID | User| Query"
      result.each do |row|
        puts " %7d | %-16s | %s " %
          row.values_at('procpid', 'usename', 'current_query')
      end
    end
```
