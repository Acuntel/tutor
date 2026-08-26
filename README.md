# Tutor

Brady Schwartz. USC. My AI tutor's memory: every course, every lecture, every deadline.

## What this is

A tutor that does not forget. Two halves.

**Memory.** Everything my classes tell me lives here: syllabi, prompts, policies, readings,
lectures, announcements, and the running state of every assignment. When a deadline hits,
nothing is a surprise and nothing is guessed at. Every rule an instructor wrote down is
searchable, in their own words.

**Teaching.** I record lectures all semester and feed them in. Each one becomes a transcript,
distilled notes, a study guide, and practice problems, and it appends to a running concept
index for that course. The index is what turns a pile of lectures into cumulative review and
real exam prep. The pipeline is spec'd in `LEARNING-SYSTEM.md`.

The name is the job: this is not a filing cabinet, it is the thing that teaches me.

## How to use it

1. Send anything, in any form: a prompt PDF, a Brightspace announcement, a dictated lecture,
   an email from an instructor, a photo of the whiteboard, a graded paper with comments. Drop
   it in `INBOX/` or just paste it.
2. It gets filed the same day, without being asked. The verbatim original is kept, a distilled
   version sits beside it, and the whole thing gets committed.
3. Lectures additionally become a study guide and a practice set.
4. Ask to be quizzed whenever. Ask what is due whenever.

## Layout

```
tutor/
├── README.md              you are here
├── CLAUDE.md              operating rules for Claude in this repo
├── LEARNING-SYSTEM.md     how a recorded lecture becomes something to study from
├── CRAWL-CHECKLIST.md     what to pull from Brightspace, per course
├── OPEN-QUESTIONS.md      things I need to confirm with an instructor or check on Brightspace
├── INBOX/                 unfiled drops, cleared out periodically
├── semester/              per-semester overview, weekly schedule, combined deadlines
│   └── sources/           screenshots and exports, kept verbatim
└── courses/
    ├── writ-150/          full syllabus loaded
    ├── math-118/          shell + lectures arriving
    ├── ctcs-190/          shell, awaiting syllabus
    └── buad-302/          shell, awaiting syllabus
```

Every course folder has the same shape:

```
courses/<slug>/
├── COURSE.md              distilled facts: logistics, grading, policies
├── deadlines.md           every date, with what is actually due
├── instructor-profile.md  what this instructor rewards and penalizes
├── syllabus/              verbatim source documents, never edited
├── policies/              AI policy, formatting, attendance, late work
├── assignments/           one file per graded item, prompt through returned grade
├── readings/              reading notes and citation info
├── notes/                 class notes and lecture transcripts by date
├── study/                 study guides, practice problems, concept index
└── drafts/                my own writing, versioned
```

WRIT 150 also has `service-learning/` for the JEP partnership, hours log, and field notes.

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
