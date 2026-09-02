# Lancaster, Morecambe & District Badminton League Scheduler

Calendar subscription feeds for the 2026/27 season — one `.ics` file per team, all three divisions.

Live at: https://liamgibsonn.github.io/badminton-scheduler/

## Files

- `index.html` — landing page with subscribe buttons for every team
- `<team>.ics` — one calendar feed per team (30 files)
- `.nojekyll` — stops GitHub processing the site as a blog

## Rearranging a match

1. Open the team's `.ics` file on github.com and click the pencil icon
2. Find the event — they're in week order, and each has `UID:<team>-2026-wk07@badminton-scheduler`
3. Change `DTSTART` / `DTEND` (format `YYYYMMDDTHHMMSS`), and `LOCATION` if the venue moved
4. Change `SEQUENCE:0` to `SEQUENCE:1` so calendar apps treat the edit as authoritative (bump it again on the next edit)
5. Commit

Edit **both** teams' files — each match appears in two feeds.

Because the UID stays the same, subscribers get the event *moved* rather than duplicated. Never change a UID for an existing match.

## Notes

- Times come from each club's home night; every match is blocked out for 3 hours
- Venue addresses are filled in for Carnforth, University of Cumbria, Bay Leadership Academy, LRGS and Ripley. Preesall, Kirkby Lonsdale and Ingleton show the venue name only — add full addresses to those `LOCATION` lines when known
- Keep the file names and URLs stable across seasons. Overwrite the contents each August rather than creating a new folder, so nobody has to re-subscribe
