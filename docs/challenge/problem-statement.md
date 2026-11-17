# Problem statement

A small banking service holds accounts for the customers of one business client. Once a day, the client sends a CSV file of transfers to make between those accounts. The task is to build a program that:

1. loads the opening balance of every account for one client from a CSV file;
2. applies one day of transfers from a second CSV file, in the order they appear;
3. never lets an account balance go below $0.00: a transfer that would do so is not made.

Each account is identified by a 16-digit number.

## Sample files

Two sample files are in this folder, and the same files are in [`data/`](../../data/), where the program uses them by default.

[`account_balances.csv`](account_balances.csv): one account per line, with its opening balance.

| Account | Opening balance |
|---:|---:|
| 1111234522226789 | 5000.00 |
| 1111234522221234 | 10000.00 |
| 2222123433331212 | 550.00 |
| 1212343433335665 | 1200.00 |
| 3212343433335755 | 50000.00 |

[`transactions.csv`](transactions.csv): one transfer per line, as the account to take the money from, the account to pay it to, and the amount.

| From | To | Amount |
|---:|---:|---:|
| 1111234522226789 | 1212343433335665 | 500.00 |
| 3212343433335755 | 2222123433331212 | 1000.00 |
| 3212343433335755 | 1111234522226789 | 320.50 |
| 1111234522221234 | 1212343433335665 | 25.60 |

## Assessment criteria

The solution is judged on 13 points:

- **Data structure:** uses domain models; uses native data structures readably.
- **Tests:** uses RSpec; has some coverage; has good coverage; tests are orthogonal; tests explain the functionality.
- **Object orientation:** models encapsulate logic appropriately; respects separation of concerns; short methods; readable methods.
- **General:** runs and provides feedback; calculates the test files accurately.
