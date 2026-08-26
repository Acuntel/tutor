# Learning system

How a lecture becomes something Brady can actually study from.

He records lectures with NessoTalk PTT all semester and feeds them in. This is what happens
to each one, automatically, without him asking.

## The pipeline

```
recording → transcript → notes → study guide → practice problems → concept index
                                                                          ↓
                                                            cumulative review + exams
```

### 1. Transcript, verbatim

`courses/<slug>/notes/YYYY-MM-DD-lecture-transcript.md`

Raw speech-to-text. Never edited. Frontmatter records when it was captured, how long the
audio was, the word count, and the `ptt.log` hash so the file can be traced back to a
specific session.

🚨 **Same-day or it is lost.** NessoTalk stores no transcript text. `~/.dictation/ptt.log`
records only `✓ N words · <hash>`. The text sits in the clipboard until something overwrites
it. Recovery: `pbpaste | wc -w`, then match N against the log.

### 2. Notes, distilled

`courses/<slug>/notes/YYYY-MM-DD.md`

What was actually taught, in clean notation:
- Every formula, definition, and result, written properly
- Worked examples from the lecture, with the arithmetic verified
- **A "mis-transcriptions" section.** Speech-to-text garbles math constantly. `e` becomes
  `B`, `x` becomes `X`, minus signs vanish. Corrections go here; the raw file stays untouched.
- Anything the instructor said about exams, homework, or grading, quoted
- What was left unfinished, and what is missing if the recording started late

Anything computed that the instructor did not say gets labeled as such. Never blur the line
between what was taught and what was worked out afterward.

### 3. Study guide

`courses/<slug>/study/YYYY-MM-DD-guide.md`

Not a restatement of the notes. This answers:
- **What is this for?** The problem the concept solves.
- **How does it connect** to what came before?
- **What are the traps?** The mistakes this topic is designed to catch.
- **What does a test question look like?** The recognizable shapes.
- **What has to be memorized** versus what can be re-derived.

### 4. Practice problems

`courses/<slug>/study/YYYY-MM-DD-practice.md`

- Ordered easy to hard, ending above the difficulty of the lecture examples
- Every numeric answer verified before it is written down
- **Solutions in a separate section at the bottom**, so the problems can be attempted first
- At least one conceptual question with no arithmetic
- At least one problem that runs a formula backward, solving for `r` or `t` rather than for
  the amount

### 5. Concept index

`courses/<slug>/study/concepts.md`

One running table per course. Every concept, the date it was introduced, where it is covered,
and its current confidence level. This is what makes cumulative review and exam prep possible
instead of re-reading every lecture.

## Quiz mode

When Brady asks to be quizzed:

- One question at a time. Wait for his answer before moving on.
- Do not give the answer away in the question.
- When he is wrong, ask what he was thinking before explaining. The error pattern matters
  more than the individual miss.
- At the end, name what the wrong answers had in common, and update confidence levels in
  `concepts.md`.
- Weight toward concepts marked shaky and toward anything not reviewed in two weeks.

## Exam prep

When an exam date lands in a `deadlines.md`, work backward from it:
- Pull every concept from `concepts.md` in scope for that exam
- Sort by confidence, weakest first
- Build a mixed problem set that does not tell him which topic each question is testing,
  because that is the part real exams do and practice sets usually do not

## The line

Teaching Brady the material is always in scope, in every course: explaining, quizzing,
building study guides, writing practice problems, working examples, finding his gaps.

Producing his graded work is never in scope, in any course. For WRIT 150 that boundary is
written out in detail in `courses/writ-150/policies/ai-policy.md` and it is strict: no
drafting, no rewriting, no revising, no editing, no outlining. For courses whose policy is
not yet known, assume the same until Brady produces it in writing.

A practice problem I invented is mine to solve. A problem set he is turning in is his.
