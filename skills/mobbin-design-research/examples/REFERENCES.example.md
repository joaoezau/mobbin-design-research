# Profile screen: references

File: `references/mobbin/profile/REFERENCES.md`

Question this pass answers: how do the best apps arrange identity, a progress summary and settings access on a profile?

## Screens used

| # | App | mobbin_url | Image | What to take |
|---|---|---|---|---|
| 1 | App A | https://mobbin.com/screens/00000000-0000-0000-0000-000000000001 | img/01-app-a-profile.jpg | Avatar 72 px, name and handle stacked, one primary action under them |
| 2 | App B | https://mobbin.com/screens/00000000-0000-0000-0000-000000000002 | img/02-app-b-profile.jpg | Summary row of 3 stats with one number each; settings as a top-right icon |
| 3 | App C | https://mobbin.com/screens/00000000-0000-0000-0000-000000000003 | img/03-app-c-profile.jpg | Segmented control for content tabs; selected state by fill, not underline |

## Flows used

| App | mobbin_url | Steps | What to take |
|---|---|---|---|
| App A | https://mobbin.com/flows/00000000-0000-0000-0000-000000000004 | 5 | Edit profile opens as a sheet, not a pushed screen; back closes it |

## Why these and not others
- 1 and 2 are the best at hierarchy; 3 is the only one with a clear segmented switch.
- Dropped: a dense dashboard-style profile (too many equal-weight blocks).

## Open questions
- Where does privacy live? (None of the three show it on the profile itself.)

Note: `image_url` links expire. Keep the downloaded files in `img/`; `mobbin_url` is the durable record.
