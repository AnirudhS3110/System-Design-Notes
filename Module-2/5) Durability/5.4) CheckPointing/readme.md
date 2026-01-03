# Checkpointing:
- It balances Durability with Recovery time.    
- Imagine you are using WAL, if we are logging items for months, once the System crashes and at the time of recovery, going through all the logs and Recovering the Data would take HOURS.
- CheckPointing solves this.
- Periodically(Maybe every minute) , the Database Server Flushes ALL the IN memory Changes to the Disk and mark a POINT in the WAL Saying, **EVERYTHING BEFORE THIS POINT IS SAFELY FLUSHED INTO THE DISK**
- So at time of Crash Recovery, no need to play the log from begining, its enough to **play teh log from last checkpoint**
- THis reduces Recovery time significantly.
- PostgresSQL does this automatically.
- MySQL and Redis also have similar mechanisms.

## TradeOff:
- it may cause Performance Hiccups
- DBs spread CheckPoints across times, spreading it smoothly across time ensures no Stalling of WRITES.

## <a href="../5.3) Durability Metrics/readme.md">Prev: Durability Metrics </a>