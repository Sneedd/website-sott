# Password

## Security

| Rule                      | Default / Example            | Description                                 |
| ------------------------- | ---------------------------- | ------------------------------------------- |
| Length                    | ≥ 12 chars                   | Longer passwords are harder to determine.   |
| Character variety         | Upper, lower, number, symbol | Increases resistance to guessing attacks.   |
| Uncommon combinations     | Avoid words / patterns       | Prevents dictionary and pattern attacks.    |
| Password history          | Last 5 remembered            | Stops reuse of recent passwords.            |
| Minimum age               | 1 day                        | Prevents rapid cycling through passwords.   |
| Maximum lifetime          | 90 days                      | Forces periodic password refresh.           |
| Salt                      | Unique per password          | Prevents precomputed hash attacks.          |
| Pepper                    | Server-side secret           | Adds extra protection if hashes leak.       |
| Lockout policy            | 5 failed attempts            | Against brute-force guessing.               |
| Wait times                | Eventually exponential       | Slows brute-force but remains user-friendly.|
| 2FA / MFA                 | Recommended                  | Adds a second factor for security.          |
| Hashing algorithm         | bcrypt / Argon2              | Secure one-way password storage.            |
| Transport security        | HTTPS                        | Protects passwords in transit.              |

* Side notes
  * Argon2 is memory-hard and computationally expensive (could need 100-500ms per hash)
  * SHA512 should be used e.g. with PBKDF2
  * PBKDF2 repeats hash in iteration which makes it computationally expensive but not memory-hard


