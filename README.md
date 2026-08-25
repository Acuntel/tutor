# School Brain

Brady Schwartz. USC. Persistent context store for coursework.

## What this is

A durable, version-controlled memory of everything my classes tell me: syllabi, prompts,
policies, readings, my own notes, and running state on each assignment. The point is that
when a deadline hits, nothing is a surprise and nothing is guessed at. Every rule the
instructor wrote down lives here in a form I can search.

## How to use it

1. Anything new (a prompt PDF, a Brightspace announcement, lecture notes, an email from an
   instructor, a graded paper with comments) goes into `INBOX/` as-is.
2. Ask Claude to file it. It gets distilled into the right course folder and the raw copy
   is kept in `syllabus/` or `readings/` so nothing is lost in summarization.
3. Before writing anything for a class, read that course's `COURSE.md` and `policies/`.

## Layout

```
school-brain/
├── README.md              you are here
├── CLAUDE.md              operating rules for Claude in this repo
├── OPEN-QUESTIONS.md      things I need to confirm with an instructor or check on Brightspace
├── INBOX/                 unfiled drops, cleared out periodically
├── semester/              per-semester overview and combined deadline calendar
└── courses/
    └── writ-150/          one folder per course
        ├── COURSE.md              distilled facts: logistics, grading, policies
        ├── instructor-profile.md  what this instructor rewards and penalizes
        ├── deadlines.md           every date, with what is actually due
        ├── syllabus/              verbatim source documents
        ├── policies/              AI policy, formatting, attendance, late work
        ├── assignments/           one file per WP, tracking state from prompt to grade
        ├── readings/              reading notes and citation info
        ├── service-learning/      volunteer org, hours log, field notes
        ├── notes/                 class notes by date
        └── drafts/                my own writing, versioned
```

## Rules I set for myself

- Raw source documents are never edited. Distillations link back to them.
- Every claim in a distilled file traces to a source document. If it does not, it is marked
  as an assumption.
- Course policy beats convenience. If a policy says do it a certain way, do it that way.
