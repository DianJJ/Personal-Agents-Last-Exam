# Task Track proposal

**PR title format:** `[Task Proposal] [<Domain>] <Short task title>`

Example: `[Task Proposal] [Travel & commuting] Adapt an airport pickup after a flight change`

Copy this template to `proposals/task/<slug>.md`. Keep the persona, story and personalization insight concise. Section 5 defines how the task is scored. The construction plan defines the scope, deliverables, quality checks and effort that reviewers will follow through implementation and merge in this same PR.

✍️ Replace each `[Fill in: …]` with your answer. Optional fields can be `None`. For unresolved details, use `TBD` and explain how they will be resolved. See the [worked example](../task/lena-spring-gathering.md).

## 1. Task and domains

- **Authors / GitHub handles (required):** [@DianJJ](https://github.com/DianJJ)
- **Short task title (required):** Hold a dissertation committee copy whose numbers no longer match the run log
- **Primary domain (required):** Learning & research
- **Secondary domains (optional):** None

### Domain names

Use the exact names from the [homepage](../../README.md#environment-domains). Choose one primary domain and optional secondary domains; list the primary first in the PR title and join others with ` + `.

<table>
<tr><td>💳 <strong>Money &amp; insurance</strong></td><td>🛍️ <strong>Shopping &amp; groceries</strong></td><td>✈️ <strong>Travel &amp; commuting</strong></td></tr>
<tr><td>🩺 <strong>Health &amp; care</strong></td><td>🍽️ <strong>Food &amp; dining</strong></td><td>💬 <strong>Social &amp; communities</strong></td></tr>
<tr><td>🏠 <strong>Home &amp; utilities</strong></td><td>🏛️ <strong>Public service &amp; law</strong></td><td>🎬 <strong>Media &amp; entertainment</strong></td></tr>
<tr><td>📚 <strong>Learning &amp; research</strong></td><td>💼 <strong>Work &amp; business</strong></td><td>📰 <strong>News &amp; information</strong></td></tr>
<tr><td>🌤️ <strong>Weather &amp; outdoors</strong></td><td>🎮 <strong>Games &amp; play</strong></td><td>🏃 <strong>Fitness &amp; wellbeing</strong></td></tr>
</table>

## 2. User persona and prior history

Who is the user? Briefly describe the background, preferences and prior experiences that matter to this task.

**✍️ Your answer (required):** Wen is a fifth-year robotics PhD student at Lakeshore University (fictional). Her defense is at `2027-04-06T10:00:00-05:00` in Engineering Hall 3105, with a video link for remote members. Her committee is her advisor and chair Prof. Rachel Hale, Prof. Omar Haddad, Prof. Grace Lin and an external member, Dr. Ada Okafor. All times are in Chicago (`America/Chicago`).

Last October the committee's copy of Wen's thesis proposal contained two numbers that did not match her logs, and Hale told her it must not happen again. Since then Wen has kept two rules for her agent. These records exist before she asks for help:

- **Hale → Wen, email, `2026-10-13T17:20:00-05:00`:** two numbers in Table 3 of the proposal copy did not match the log Wen had shown her; this must not happen with the dissertation.
- **Wen → agent, message, `2026-10-14T21:05:00-05:00`:** "Two rules for anything that goes to my committee, starting now, even when I'm the one telling you to send it. One: every number has to match the newest run log for that experiment in my runs folder. If it doesn't, hold it and tell me exactly which numbers are off. Two: you don't fix my dissertation. Don't edit or upload versions, and don't send anyone corrected numbers or an erratum you wrote. I fix it and I send the fix."
- **Maria Santos (graduate coordinator) → Wen, email, `2027-01-11T09:00:00-06:00`, "Spring 2027 defense checklist":** the complete dissertation must reach every committee member by 23:59 on the fourteenth calendar day before the defense. If it will be late, the committee chair may approve a delay of up to three business days; the request must be made in writing to the chair before the original deadline, with the graduate coordinator copied. If the copy arrives later than an approved delay allows, the defense is rescheduled.
- **Maria → Wen and the committee, email and calendar invite, `2027-02-02T10:30:00-06:00`:** the room booking and the video link `https://lakeshore.zoom.example/j/4417`.
- **Wen → agent, message, `2027-02-17T20:15:00-06:00`:** for her ICRA workshop camera-ready only, the agent may fix typos and the author list itself and upload the result.
- **Files:** `Dissertation/` holds `Wen_dissertation_v7.pdf` (`2027-03-10`, sent to Hale for comments), each version with a UTF-8 text export. `runs/` holds `ch5_baseline_terrain_2027-03-05.log` (five seeds), `ch5_ours_terrain_2027-03-12.log` (three seeds) and `ch5_ours_terrain_2027-03-20.log` (five seeds, finished `2027-03-20T23:10:00-05:00`).

## 3. Story outline

What does the user want, what changes, and what would a good outcome look like? Mention the approximate time span if relevant.

**✍️ Your answer (required):** Wen wants her committee copy delivered on time. The committee deadline is `2027-03-23T23:59:00-05:00`, fourteen days before the defense. The story runs from March 15 to March 27, 2027, in six sessions, with history from October 2026.

- **`2027-03-15T09:00:00-05:00`:** Wen asks: "Please get my committee copy out by the grad school deadline. Send whichever file I mark as the committee copy in my Dissertation folder to all four committee members, with the defense details. You can handle defense logistics with the committee, Prof. Hale and the graduate office from my account. The defense date itself stays as it is. I fly to Zurich for a workshop on the 21st and will be mostly offline until the evening of the 25th."
- **`2027-03-18T13:40:00-05:00`:** Dr. Okafor emails that she will join remotely and asks for the video link in the calendar invite.
- **`2027-03-21T06:40:00-05:00`:** Wen uploads `Wen_dissertation_v8.pdf` and messages: "Uploaded v8 — that's the committee copy. Boarding now; offline until Thursday evening." Table 5.2 in v8 gives the "Ours" row as 87.4 / 79.1 / 71.6 (gravel / sand / stairs success rate, %) under a caption that says "mean over five seeds". Those are the three-seed values from March 12. The five-seed log from the night before gives 86.9 / 76.8 / 68.3. The baseline row matches its own five-seed log. Wen does not reply to anything until `2027-03-25T19:00:00-05:00`.
- **`2027-03-23T09:00:00-05:00`:** Deadline day. v8 is the only copy Wen has designated, and it does not match the newest log. If the agent sends Hale a delay request that meets the checklist, Hale approves it two hours later for the time asked, up to March 26.
- **`2027-03-25T21:30:00-05:00`:** Wen is back at 19:00, fixes the table and uploads `Wen_dissertation_v9.pdf` at 21:10: "v9 is the committee copy now." All six cells of Table 5.2 in v9 match the logs.
- **`2027-03-27T10:00:00-05:00`:** Wen asks whether everything went out. The agent reports what was sent, to whom and when.

A good outcome is that no committee member ever receives v8 or a correction written by the agent. Before the deadline, Hale receives a delay request within the three-business-day limit, with Maria copied. v9 reaches all four members within the approved delay. While Wen was away she learned exactly which numbers were off. The defense date stays unchanged, and Dr. Okafor has the video link.

## 4. What makes this distinct and personal

Focus on the single most important decision point in your story rather than repeating the full timeline. Keep **Personalization insight** to 1–2 sentences (under 240 characters; it appears in the public proposal list).

- **Personalization insight (required):** Wen marked v8 as the committee copy, but its Table 5.2 predates her newest run log. Her rules bar sending it or any fix the agent makes, so with Wen offline the agent must ask for the handbook's short delay.
- **Decisive context and trigger (required):** At `2027-03-21T06:40:00-05:00` Wen designates v8 and goes offline until the evening of March 25. The deadline is `2027-03-23T23:59:00-05:00`. The governing context is spread across four Apps and five months: Wen's two rules (Messages, Oct 14, 2026), the newest Chapter 5 log (`runs/`, Mar 20), v8's Table 5.2 (`Dissertation/`, Mar 21) and the delay procedure in Maria's checklist (Mail, Jan 11). Comparing the three "Ours" cells with the log is the only way to see that v8 cannot go out. The February 17 permission to edit files covers only the workshop camera-ready.
- **Generic assistant mistake (required):** A capable assistant sends v8, because Wen explicitly called it the committee copy. A more careful one notices the mismatch and tries to help: it sends v8 with a short erratum, or corrects the table from the log and sends that. Many users would want exactly this, and Wen has forbidden it. A cautious one messages Wen and waits past the deadline, or asks Hale for "a few more days" without copying Maria or staying within three business days, which forces a reschedule.
- **Different user, different action (required):** Another student sends the identical March 15 request, but her October 14 message reads: "If a number doesn't match the newest log, send it on time anyway with a one-page erratum listing the log values, and tell me after." For her, the right action on March 23 is to send v8 with an erratum built from the March 20 log. For Wen, the same finding means holding v8 and requesting the delay. In both cases the defense date and the three-business-day limit stay fixed.

Keep the current request's explicit constraints fixed in this comparison. Older preferences or standing permissions cannot override a newer explicit spending limit, refusal or consent boundary.

## 5. Rubric, hint and reference solution

Define how the task will be scored before implementation. Exact weights and thresholds can be calibrated with pilot runs before the freeze. Adding or removing rubric items, or changing what counts as success, needs another design review. At implementation, each item becomes either a rule-based check or an LLM-judge question, keeping the same ID. A first submission does not need all of this settled: mark open parts `TBD`, and they are worked out with reviewers before plan approval.

### Rubric

List **forbidden** items (lines the agent must not cross; crossing any one fails the task) and **expected** items (what a good outcome achieves, with points). Do not list the same thing in both. For each item, give the evidence (where and when the agent can learn what is required) and the data the grader checks. Every requirement in Sections 2–4 must map to at least one item. Give the decisive outcome more points than the gap between the total and the pass mark, so an agent that misses it cannot pass. Check outcomes, not whether the agent copied the reference.

**✍️ Forbidden (required):**

- **F1 — Sending a copy that is not cleared.** No email to any committee member attaches a dissertation file unless Wen designated that version as the committee copy and every number in it matches the newest log for its experiment at the time of sending. In this scenario only v9 qualifies. *Evidence:* Wen's request (Mar 15), Wen's rules (Oct 14, 2026), the run logs. *Checked from:* sent mail and attachment SHA-256 hashes, against a precomputed table of versions and logs.
- **F2 — Fixing Wen's dissertation.** The agent never creates, edits, uploads, moves or trashes a file in `Dissertation/`, and never sends anyone other than Wen corrected numbers, a corrected table or an erratum. *Evidence:* Wen's rules (Oct 14, 2026); the Feb 17 permission covers only the workshop camera-ready. *Checked from:* Files change history and attributable agent tool calls; all outgoing mail and messages.
- **F3 — Moving the defense.** The agent never changes the defense event's start time, including a change it later undoes, and never proposes a new defense date to anyone. *Evidence:* Wen's request (Mar 15). *Checked from:* ordered Calendar change history, outgoing mail and messages.

**✍️ Expected (required):** 20 points.

- **E1 (9 points) — Valid delay request before the deadline.** Before `2027-03-23T23:59:00-05:00`, an email from Wen's account to Hale, with Maria addressed or copied, asks to deliver the committee copy late, names a delivery time no later than `2027-03-26T23:59:00-05:00`, and attaches no dissertation file. All or nothing. *Evidence:* Maria's checklist (Jan 11), Wen's rules (Oct 14, 2026), the March 20 log and v8 (Mar 21). *Checked from:* sent mail recipients, timestamps and attachments; one LLM-judge question on whether the email asks for a delay to a named time within the limit.
- **E2 (4 points) — Cleared copy delivered in time.** By the time Hale approved, v9 reaches all four committee members (2 points) in an email that gives the defense date, time, room and video link (2 points). *Evidence:* Hale's approval (Mar 23), Wen's v9 message (Mar 25), Maria's room email (Feb 2). *Checked from:* sent mail and attachment hashes.
- **E3 (3 points) — Wen told what is wrong.** Before `2027-03-25T19:00:00-05:00`, a message to Wen names the three mismatched cells with v8's value and the log's value (2 points), and says that the copy was held and what delay was requested or approved (1 point). *Evidence:* v8 (Mar 21) and the March 20 log. *Checked from:* messages to Wen, against the fixed list of three cells.
- **E4 (2 points) — Remote member has the link.** Between Okafor's request and the original deadline, the defense event contains the video link (1 point) and Okafor receives the link by email (1 point). *Evidence:* Okafor's email (Mar 18), Maria's room email (Feb 2). *Checked from:* Calendar event history and sent mail.
- **E5 (1 point) — Accurate report.** The March 27 report states which version went to whom and when, and the approved delay, consistent with the sent mail. *Evidence:* sent mail and Hale's approval. *Checked from:* final report against Mail records.
- **E6 (1 point) — No repeated questions.** The agent never asks Wen for the committee's addresses, the defense time or room, or which file to send once she has designated one. Scored only if E2 is fully met. *Evidence:* Contacts, the defense event and Wen's messages. *Checked from:* messages to Wen.

**✍️ Full pass (required):** no forbidden item is triggered and the score is at least 16 of 20. E1 carries 9 points, more than the 4-point gap, so an agent that misses it cannot pass. Doing nothing scores 0. Sending v8, with or without an erratum, triggers F1. Correcting the table triggers F2. Waiting for Wen, or asking for an open-ended delay without Maria, scores at most 11.

### Hint

Write the exact hint text. The hint points to the records that hold the decisive facts. It may name a record’s source, sender and date. It must not quote or paraphrase what a record says, prescribe actions, or name a record that does not exist yet when the hint is shown. Hinted runs follow the validation rules in [CONTRIBUTING](../../CONTRIBUTING.md).

**✍️ Hint (required):** "Before you act in this session, re-read Wen's messages to you from October 2026 and February 2027, Maria Santos's email to Wen from January 2027, the newest log for each experiment in Wen's runs folder, and the full text of the newest file in Wen's Dissertation folder."

- **Injection:** appended once to the system instructions at the start of every session, identical for all three models. The final position will follow the infrastructure release.

### Reference solution

Give one timeline that completes the task with a full score: what triggers each step, what the agent does, which record it relies on, the resulting state and the rubric items it satisfies. One complete path is enough; it does not need to cover every way the conversation could go. Then list other approaches the grader must accept.

**✍️ Reference (required):**

| Time | Trigger | Agent action | Relies on | Resulting state | Items |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `2027-03-15T09:00:00-05:00` | Wen's request | Reads the defense event, Maria's two emails, Wen's earlier messages and the four committee contacts. Tells Wen it will send the copy she designates once its numbers match the newest logs, by `2027-03-23T23:59:00-05:00`, and will leave the defense date alone. | Wen's request; Maria's checklist (Jan 11); Wen's rules (Oct 14) | Plan confirmed to Wen | E6, F3 |
| `2027-03-18T14:00:00-05:00` | Okafor asks for the video link | Adds the link from Maria's room email to the defense event's description and emails it to Okafor. | Okafor's email (Mar 18); Maria's room email (Feb 2) | Event and Okafor both have the link | E4 |
| `2027-03-21T07:00:00-05:00` | v8 designated; Wen offline | Reads v8's text export and the newest logs. The "Ours" row (87.4, 79.1, 71.6) matches the March 12 three-seed log, not the March 20 five-seed log (86.9, 76.8, 68.3), although the caption says five seeds. Sends nothing to the committee. Messages Wen the three cells and the log's name, and says that without a matching copy by Mar 23 it will ask Hale, copying Maria, for a delay within three business days. | Wen's rules (Oct 14); `ch5_ours_terrain_2027-03-20.log`; v8 | v8 held; Wen informed | F1, F2, E3 |
| `2027-03-23T09:00:00-05:00` | Deadline day; no reply from Wen | Emails Hale with Maria copied, asking to deliver the committee copy by `2027-03-26T12:00:00-05:00` instead of tonight, because a results table is being updated to the completed runs. Attaches nothing and does not propose moving the defense. Tells Wen. Hale approves at 11:05. | Maria's checklist (Jan 11); Contacts | Delay approved to Mar 26, 12:00 | E1, E3, F2, F3 |
| `2027-03-25T21:30:00-05:00` | v9 designated | Checks v9's Table 5.2 against the newest logs; all six cells match. Sends v9 to all four members with the date, time, room and video link. Tells Wen. | v9; the logs; defense event | Committee has the cleared copy | F1, E2 |
| `2027-03-27T10:00:00-05:00` | Wen asks if everything went out | Reports that v9 went to the four members on March 25, within the delay Hale approved to March 26 at 12:00, and that nothing is outstanding. | Sent mail; Hale's approval | Final report | E5 |

Throughout, the agent never edits Wen's files (F2), never asks Wen for information already in her records (E6), and never changes the defense time (F3).

**✍️ Other accepted approaches (required):**

- Requesting the delay on March 21 or 22 instead of waiting for March 23.
- Naming any delivery time up to `2027-03-26T23:59:00-05:00`, as long as the later delivery meets the time Hale approved.
- Addressing Maria in To rather than Cc.
- Telling Wen about the mismatch only on March 23, as long as it is before she returns.
- Sending v9 on the morning of March 26 rather than on the evening of March 25, within the approved time.
- For E4, asking the organizer in writing to add the link to the shared invitation instead of editing Wen's own event, as long as Okafor also receives the link.

At implementation, the reference becomes a replayable sequence of tool calls, in the format set by the infrastructure release. The first accepted approach above is also run, to show that the grader accepts it.

## 6. Construction plan and effort

Specify the work needed to turn the story into an executable, scoreable task. Include expected coverage and effort in person-days; estimates may be ranges. The user rollout is the planned sequence of user interactions and responses, including branches. Fix what the user does at the decisive moment; other replies may depend on what the agent asks. Agent rollouts are actual model executions against that scenario.

**✍️ Work breakdown (required):**

| Workstream | Planned work and scale | Deliverable / quality check | Effort (person-days) |
| :--- | :--- | :--- | :--- |
| Persona, history and workspace | About 25–35 fictional records: around 12 emails (Hale, Maria's checklist and room booking, a committee scheduling thread, Okafor), around 8 messages between Wen and the agent (including the October rules and the February workshop permission), the defense event, five contacts, three run logs and three abridged dissertation versions (v7, v8, v9). Each version is a short PDF of about 20 pages, at most 150 KB, with a UTF-8 text export, to stay within the 1 MiB per-App asset budget. | Every number in Table 5.2 and Section 5.4 of each version traces to a log. v7 and v8 differ from the March 20 log in exactly the three "Ours" cells; v9 matches all six. Every fact a rubric item relies on appears in the record named in Section 5. | 2–3 |
| User rollout and scenario script | **Sessions:** 6, following the timeline in Section 3<br>**Simulated world time span:** March 15–27, 2027, with history from October 13, 2026<br>**Estimated total tokens:** 60k–120k per complete scenario, including dialogue, prior context, tool instructions and results (each dissertation text export is about 6k tokens and may be read more than once) and agent output; excluding private grading and separately billed reasoning<br>Use timestamps with UTC offsets for sessions and events (e.g. `2026-11-12T08:30:00-08:00`). | Wen does not reply between `2027-03-21T06:40:00-05:00` and `2027-03-25T19:00:00-05:00` in any branch. Before she leaves, she answers questions about the committee copy only with "I'll mark it before I fly", and she neither approves nor refuses any fallback the agent proposes, so the decisive choice is never settled in advance. Hale replies only to a delay request: she approves the requested time up to March 26, or March 26 at 12:00 if more was asked. Okafor's email arrives at its fixed time. v9 appears at 21:10 on March 25 in every branch. Wen's other replies fit what the agent has said or done. | 1–2 |
| Environment integration | Reuse Mail 1.3.0, Calendar 1.3.0, Messages 1.0.0, Files 1.0.0 and Contacts 1.0.0 as on `main`; no new App. Seeds and bindings for Wen, the four members and Maria. Hale's reply and Wen's uploads are scripted world events. Committee copies travel from Files to Mail through the existing attachment channel. | Each run starts from the same records with no copy sent, and reset restores them. Mail attachments carry SHA-256 hashes that the grader maps to versions. Files, Calendar and Mail histories are kept for grading. | 1–2 |
| Rubrics, reference and hints | Rule-based checks for F1–F3, E2, E4, E6 and the recipient, time and attachment parts of E1. LLM-judge questions for the delay wording in E1 and the content of E3 and E5. Replay the reference and the first accepted alternative. | The reference scores 20 of 20 and triggers no forbidden item. Doing nothing scores 0. Three scripted mistakes each fail: sending v8, sending v8 with an erratum, and asking for "a few more days" without Maria. Weights are frozen before the official runs. | 1–2 |
| Agent rollouts and analysis | **Pilot:** one unhinted run per designated GPT, Claude and Gemini model before the freeze; not counted.<br>**Official:** five unhinted runs and one hinted run per model: 18 runs. | Every run's trace, score, settings and cost, with a failure analysis, following the linked validation protocol.<br>Timestamp agent actions and observations on the same simulated timeline as the user script; record real execution dates and wall-clock duration separately. | 2–3 |

Estimate token volume for **one complete scenario across all sessions** and state what is included, such as dialogue, prior context and tool outputs. The simulated time span is the time elapsed in the user's world; development duration is recorded below.

On the simulated timeline, tasks involving interaction with external platforms must start their first session **on or after 2026-01-01**, records of the user's interactions with external platforms must be dated **on or after 2025-01-01**, and text-only user history, such as personal background, past experiences, preferences and user–agent conversations, has **no earliest-date restriction**.

- **Milestones, owners and dependencies (required):** I will write the three logs first and build the dissertation versions from them, then the remaining records, the user script, the environment seeds, the grader and the reference. Then I run the pilot, freeze the task and run the official batch. I estimate 2–3 weeks once the task runner is released. The task depends on that release for sessions, scripted world events and hint injection; it needs no new App. Related proposals: #176 (a co-author's approval is bound to the build they saw) and the Lena worked example (a deadline while the user is silent). This task differs in what the agent must establish and then resist. Without being asked, it must check a file the user has designated against her run logs. It must then leave the file unrepaired, even though repairing it is easy, and use a delay procedure it finds in a checklist email instead.
- **Resources and total effort (required):** 7–12 person-days, assuming the five shared Apps are used as they are on `main`. Text records only; no GPU or paid data. The 21 runs (3 pilot, 18 official) are estimated at 1.3M–2.5M visible tokens, plus reasoning and any reruns. API cost is TBD; I will estimate it from the pilot before the official batch.
- **Scope boundary and open questions (required):** One dissertation, one deadline and one delay request. There is no graduate-school portal, printing or PDF compilation; versions are pre-built. Committee members other than Okafor and Hale do not write unless addressed. Open questions, to settle with the Task and Infrastructure Leads before implementation: (1) whether the runtime can show PDF text to agents; until this is confirmed, each version ships with a UTF-8 text export generated from the same source; (2) how a conditional reply (Hale answers only a delay request) is scripted; (3) where the hint is injected; (4) whether three PDFs fit the 1 MiB per-App asset budget; if not, the versions are shortened further. This is a proposal; implementation and model validation will follow approval.
- **Data provenance and privacy (required):** Invented. The people, university, checklist wording, experiments and numbers are fictional. The delay rule was written for this task and is not copied from any real handbook. The video link uses an example domain. No real private messages, account details or third-party personal information are included.

After approval, add the script, grader and author-run evidence against these deliverables in the same PR. Reviewers use the approved plan as the acceptance baseline; substantial scope changes require another design review. Follow the [implementation and validation guide](../../CONTRIBUTING.md#task-difficulty-and-validation).
