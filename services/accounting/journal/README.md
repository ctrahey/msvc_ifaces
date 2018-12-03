# Accounting Journal

A "General Journal" service. Recieves and logs double-entry accounting journal entries, and provides them for reading back in time-series.

# Unique Features

This service is largely consistent with traditional accounting journals, with the addition of allowing multiple currencies in the entries.
Entries must still be in balance. That is, if you have ¥25 and $5 debits, you must have ¥25 and $5 credits.

# Concessions

## Amounts as floats
While we all know about floating point arithmetic issues, it was determined that a service interface is 
sufficiently decoupled from how the service performs any arithmetic. Futher, this service is not actually 
expected to perform any arithmetic (whereas, a Ledger will). The interface expressed here places no limits
on how the amounts are stored by the implementation (ideally, not as floats).

## Currency denominations as 100% Decimal
After much consideration, we have decided to concede that all amounts can be expressed in a single decimal
value. There are a few key points to understand about this decision:

1. Will not support [non-decimal denominations](https://en.wikipedia.org/wiki/Non-decimal_currency)
2. Will emphasize the burden on other systems to handle arithmetic properly

Alternatives have been considered, such as taking in amounts as a dict of "amount parts" and integer values thereof.
For example:

```
value: {
    currency: usd,
    as_string: '$12.34',
    parts: [
     { amount: 12, denomination: dollars}
     { amount: 34, denomination: cents}
    ]
}
```

 But it was deemed overkill in a world that is almost purely complying with decimal denominations.