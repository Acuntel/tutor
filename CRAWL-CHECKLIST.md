# Brightspace crawl checklist

What to pull from Brightspace for each course, and where it lands in this repo. Written to
be repeatable: run it at the start of every semester, and again whenever a course posts
something new.

**Host:** `brightspace.usc.edu`
**Access method:** Claude in Chrome extension. Claude operates inside the browser session
Brady has already authenticated. Claude never handles the USC password or the Duo prompt.
The extension pauses at any login page or CAPTCHA and hands control back.

## Per course

Run this for each of: WRIT 150, MATH 118, CTCS 190, BUAD 302.

| # | Brightspace location | What to capture | Lands in |
|---|---|---|---|
| 1 | Content, syllabus module | The syllabus file itself, downloaded | `courses/<slug>/syllabus/` verbatim |
| 2 | Content, full module tree | Every module and topic title, in order, with any posted dates | `courses/<slug>/COURSE.md` |
| 3 | Assignments (Dropbox) | Every assignment: name, due date, points, instructions | `courses/<slug>/deadlines.md` and one file per item in `assignments/` |
| 4 | Quizzes | Name, due or availability date, points, attempts allowed | `courses/<slug>/deadlines.md` |
| 5 | Discussions | Any graded topic, with its due date | `courses/<slug>/deadlines.md` |
| 6 | Grades | The grading scheme: categories, weights, and how the final grade is computed | `courses/<slug>/COURSE.md` |
| 7 | Announcements | All posted so far, with dates | `courses/<slug>/notes/announcements.md` |
| 8 | Course home, instructor info | Name, email, office hours, office location, contact preferences | `courses/<slug>/COURSE.md` |

## The two things to extract first

For any course whose syllabus has not been read yet, these two come before anything else:

1. **The AI policy.** Verbatim, into `courses/<slug>/policies/ai-policy.md`. Until it exists
   in writing, that course is treated as prohibiting AI on graded work. Policies never
   transfer between courses in either direction.
2. **The grading breakdown.** Weights, and any pass/fail gate that sits outside the weights,
   such as WRIT 150's rule that a single missing essay fails the course regardless of points.

## After every crawl

- Update `semester/fall-2026.md`: the combined deadline calendar and the AI policy status table.
- Update `OPEN-QUESTIONS.md`: remove what got answered, add what the crawl could not resolve.
- Flag any contradiction between Brightspace and a syllabus rather than silently picking one.
- Commit, with a message naming which courses were crawled and what changed.

## Notes

- Dates on Brightspace can differ from the syllabus. When they do, both get recorded and the
  conflict goes to `OPEN-QUESTIONS.md` to be settled with the instructor. Brightspace is
  usually newer, but that is an assumption, not a rule.
- A due date with no time attached is not a fact. Capture the time as Brightspace shows it.
- Downloaded files keep their original filenames and are never edited.
