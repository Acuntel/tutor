# School Brain

Brady Schwartz. USC. Persistent context store for coursework.

## What this is

Two things at once.

**A durable memory** of everything my classes tell me: syllabi, prompts, policies, readings,
lectures, my own notes, and running state on each assignment. When a deadline hits, nothing
is a surprise and nothing is guessed at. Every rule an instructor wrote down lives here in a
form I can search.

**A study system.** I record lectures all semester and feed them in. Each one becomes a
transcript, distilled notes, a study guide, and practice problems, and feeds a running
concept index per course. That index is what makes cumulative review and exam prep possible
without re-reading everything. The pipeline is spec'd in `LEARNING-SYSTEM.md`.

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
├── LEARNING-SYSTEM.md     how a recorded lecture becomes something to study from
├── CRAWL-CHECKLIST.md     what to pull from Brightspace, per course
├── OPEN-QUESTIONS.md      things I need to confirm with an instructor or check on Brightspace
├── INBOX/                 unfiled drops, cleared out periodically
├── semester/              per-semester overview, weekly schedule, combined deadlines
│   └── sources/           screenshots and exports, kept verbatim
└── courses/               one folder per course
    ├── writ-150/          full syllabus loaded
    ├── math-118/          shell, awaiting syllabus
    ├── ctcs-190/          shell, awaiting syllabus
    └── buad-302/          shell, awaiting syllabus
        ├── COURSE.md              distilled facts: logistics, grading, policies
        ├── instructor-profile.md  what this instructor rewards and penalizes
        ├── deadlines.md           every date, with what is actually due
        ├── syllabus/              verbatim source documents
        ├── policies/              AI policy, formatting, attendance, late work
        ├── assignments/           one file per WP, tracking state from prompt to grade
        ├── readings/              reading notes and citation info
        ├── service-learning/      volunteer org, hours log, field notes
        ├── notes/                 class notes and lecture transcripts by date
        ├── study/                 study guides, practice problems, concept index
        └── drafts/                my own writing, versioned
```

## Standing rules for Claude

- File everything I send, the same day, without being asked. Then commit.
- Turn every lecture into notes, a study guide, and practice problems.
- Teach me the material. That is always in scope.
- Never produce my graded work. That is never in scope, in any course.

## Rules I set for myself

- Raw source documents are never edited. Distillations link back to them.
- Every claim in a distilled file traces to a source document. If it does not, it is marked
  as an assumption.
- Course policy beats convenience. If a policy says do it a certain way, do it that way.
- Policies are per course and per instructor. Nothing carries from one course to another.
- 🚨 Dictated lectures must be filed the same day. NessoTalk keeps no transcript text, so
  the only copy is the clipboard until something overwrites it.
