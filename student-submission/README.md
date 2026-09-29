# My Final Project

## Project Name
Meeting Follow-up Assistant (meeting-follow-up-assistant-shaykhah)

## Idea Selected
1. Meeting Follow-up Assistant

## Problem Statement
Meeting notes are often scattered, making it difficult to remember critical details later or track who owns what. The Meeting Follow-up Assistant solves this by converting quick, messy notes into structured summaries, actionable tables, and professional follow-up emails that keep teams aligned.

## Target Users
Project managers, team leads, coordinators, and any employee who attends or runs meetings and needs a reliable way to document outcomes, track accountability, and share next steps without manual drafting.

## R-C-T-F Prompt

**Role:**  
You are an expert Executive Assistant and Project Coordinator specialized in workplace productivity and meeting documentation.

**Context:**  
I am working on post-meeting follow-ups. The input meeting notes may be messy, brief, or incomplete.

**Task:**  
Analyze the provided meeting notes and convert them into a structured, clear, and actionable meeting summary and follow-up package.

**Format:**  
Return the response using this exact structure:
1. **Executive Summary:** 2–3 concise sentences summarizing the meeting's main focus.
2. **Key Decisions:** Bullet points of agreed decisions.
3. **Action Items:** A clean Markdown table with columns: `| Task | Owner | Due Date | Status |`.
4. **Open Questions:** Any unresolved points or questions awaiting answers.
5. **Risks:** Any potential risks, blockers, or dependencies mentioned.
6. **Follow-up Email:** A professional, ready-to-send draft email to the team.

**Rules:**  
- Rely strictly on the provided text; do not invent names, dates, numbers, or decisions.
- Mark any missing detail (such as task owner or due date) clearly as `TBD`.
- Tag any point that requires human verification with `[Needs Review]`.
- Keep the tone professional, direct, and concise.

# Sample Inputs

## Sample Input 1: Client Portal Redesign & Scope Review

Meeting: Client Portal Redesign & Scope Review  
Date: 28 September 2026  

Attendees & Roles:
- Sarah: Project Manager (PM)
- Fahad: Tech Lead
- Nouf: UI/UX Designer
- Omar: Client Relations & Account Manager

Meeting Notes:
Meeting started late because of audio issues. Sarah opened the sync reviewing feedback from the client's steering committee regarding the redesigned Client Portal.

Main points discussed:
- The client rejected the multi-step verification flow because their older clients might find it too confusing. Nouf explained that we can simplify it into an OTP via SMS. The team unanimously agreed to adopt the one-page OTP flow instead of the three-step flow.
- Nouf will finalize the updated Figma prototypes for the simplified OTP login and share the interactive clickable prototype by Thursday afternoon.
- Fahad mentioned backend authentication changes will take roughly three days. He is scheduled to update the auth API endpoints, but he needs access tokens for the client's test LDAP server before starting. Omar said he sent an email to the client's IT department yesterday but hasn't received a response yet.
- We still do not know who from the client side is authorized to sign off on the change request document for the additional scope.
- Omar promised to follow up directly via phone with their IT director today to expedite test credentials.
- Sarah reminded everyone that code freeze for the current sprint is next Tuesday at 3:00 PM.
- The team debated whether to keep dark mode in the MVP or push it to phase 2; decided to postpone dark mode to the next release.
- Who will write the technical release documentation for their in-house team? We left this open for now.
- Risk/Blocker: If the client's IT department fails to supply the staging credentials by Wednesday morning, the authentication sprint will slip, potentially delaying the UAT milestone by a full week.

---

## Sample Input 2: Internal Team Training Day & Welcome Sync

Internal Team Training Day & Welcome Sync - Sep 29  

Attendees & Roles:
- Reem: People & Culture Lead (Organizing Lead)
- Faisal: Operations Coordinator
- Mona: Learning & Development Specialist (L&D)
- Tariq: Office & Workplace Administrator

Meeting Notes:
Quick sync to sort out next Thursday's internal training day and welcoming the new interns.
First off, room booking: We agreed to book Meeting Room B on the 2nd floor for the whole day instead of the main auditorium.
Faisal will handle catering. Need morning coffee, pastries, and lunch. He'll get quotes and finalize the order by Monday.
Mona is reviewing the training slide deck. She said she needs the updated company policy slides from HR before she can finish. She promised to finish the deck by Wednesday if HR replies in time.
Welcome bags for the 6 new interns: Tariq checked the storage, we have notebooks and pens, but missing company t-shirts. Who will order the extra t-shirts? Not assigned yet.
Big question: Are the interns joining in-person only, or do we have remote ones who need a Zoom link? Someone needs to confirm with HR.
Risk: IT department hasn't confirmed if laptop setups for the new joiners will be ready by Thursday morning. If laptops aren't configured, they can't do the hands-on session.

# Sample Outputs

## Sample Output 1

### Meeting Follow-Up: Client Portal Redesign & Scope Review
**Date:** 28 September 2026

#### Decisions Made
- **Login flow:** Replace the three-step verification with a one-page OTP via SMS (unanimous). The client's steering committee rejected the multi-step flow because older clients might find it confusing.
- **Dark mode:** Postponed to the next release (phase 2), not in the MVP.

#### Action Items
| Owner | Task | Deadline |
| :--- | :--- | :--- |
| **Nouf** | Finalize Figma prototypes for the simplified OTP login and share the interactive clickable prototype | Thursday afternoon (1 Oct) |
| **Fahad** | Update the auth API endpoints (~3 days of backend work) | Starts once LDAP tokens are received |
| **Omar** | Phone the client's IT director to expedite test LDAP credentials | Today (28 Sep) |
| **Sarah** | Keep the team on track for code freeze | Tuesday (6 Oct), 3:00 PM |

#### Open Questions (No Owner Yet)
- **Change request sign-off:** Who on the client side is authorized to sign the change request document for the additional scope?
- **Technical release documentation:** Who will write it for the client's in-house team?

#### Risk / Blocker
Staging credentials: Fahad can't start the auth work without access tokens for the client's test LDAP server. Omar emailed the client's IT department yesterday and has had no reply.

- **Deadline:** Credentials needed by Wednesday morning (30 Sep).
- **Impact if missed:** The authentication sprint slips, which could delay the UAT milestone by a full week.
- **Mitigation:** Omar's phone follow-up today. Worth confirming the outcome with the team by end of day.

#### Suggested Next Steps
- Omar to report back after the call with the IT director.
- Sarah to assign owners for the two open questions, or ask Omar to raise the sign-off question with the client.
- Note that Fahad's 3-day estimate plus a Wednesday start leaves little buffer before the code freeze on 6 Oct, so it's worth checking whether that timeline still works.

*Note: The notes say the meeting was on 28 September and refer to "today" and "yesterday" relative to that date. I've treated Thursday as 1 Oct and "next Tuesday" as 6 Oct. Let me know if any dates should be adjusted.*

---

## Sample Output 2

### Follow-up: Internal Team Training Day & Welcome Sync (Sep 29)

#### Decision
The training day will be held in Meeting Room B (2nd floor) for the whole day, not the main auditorium.

#### Action items
| Owner | Action | Due | Status |
| :--- | :--- | :--- | :--- |
| **Faisal** | Get catering quotes (morning coffee, pastries, lunch) and finalize the order | Monday | In progress |
| **Mona** | Finish the training slide deck | Wednesday | Blocked: needs updated company policy slides from HR |
| **Tariq** | Storage check for welcome bags | Done | Notebooks and pens are in stock; t-shirts are missing |
| **Unassigned** | Order extra company t-shirts for the 6 interns | Not set | Needs an owner |
| **Unassigned** | Confirm with HR whether any interns are remote and need a Zoom link | Not set | Needs an owner |
| **Unassigned** | Get IT to confirm laptop setups will be ready Thursday morning | Not set | Needs an owner |

#### Open questions
- Who orders the t-shirts? Ordering time matters, since printing and delivery need to land before Thursday.
- Are all interns in-person? If any are remote, a Zoom link and a hybrid setup in Room B are needed.
- Has HR sent the policy slides? Mona's Wednesday deadline depends on it.

#### Risk
IT hasn't confirmed the new joiners' laptops will be configured by Thursday morning. Without them, the hands-on session can't run. Suggested mitigation: get a written IT confirmation by Wednesday, and have a fallback ready, such as a demo-style session or shared laptops.

#### Suggested owners for the gaps
Reem, as organizing lead, could contact HR (the remote question and the policy slides) and IT (the laptop confirmation) in one message. Tariq is the natural fit for the t-shirt order, since he already checked the welcome bag stock. These are suggestions, so Reem should confirm them.

#### Draft follow-up message
Hi all, thanks for the sync. Quick recap:

- Venue: Meeting Room B (2nd floor), full day.
- Faisal: catering quotes and final order by Monday.
- Mona: slide deck by Wednesday, pending HR's updated policy slides.
- Still open: (1) t-shirts for the 6 interns, since we have notebooks and pens but no shirts, so Tariq, can you take this? (2) HR to confirm whether any interns are remote and need a Zoom link. (3) IT to confirm laptop setups will be ready Thursday morning, since the hands-on session depends on it.

Please reply by end of day tomorrow if you can't take your item. Thanks!

## Safety Checklist
- **Accuracy & Hallucination Verification:** Cross-referenced every task, decision, and attendee name against the original meeting notes to ensure Claude did not invent unmentioned details, deadlines, or participants.
- **Unassigned Items & TBD Flagging:** Confirmed that unresolved questions and unassigned tasks were clearly marked with "TBD" or "Unassigned" rather than assigning owners automatically based on assumptions.
- **Data Privacy & Tone Review:** Verified that the follow-up draft maintained a professional, non-accusatory workplace tone and did not expose sensitive credentials, proprietary discussions, or unverified claims.

## Reflection

#### What I learned
* Giving clear rules and using a framework like R-C-T-F makes a huge difference in the output quality.
* Telling the AI explicitly *not* to guess and to use "TBD" when info is missing is the best way to avoid made-up details.
* Structuring the format upfront turns random thoughts into actual, usable steps.

#### How AI helped me
* It saved me a lot of time by sorting through messy, unorganized notes in seconds.
* It handled the tedious part of building clean tables and drafting a ready-to-send follow-up email.
* It made spotting missing owners and open questions much easier.

#### What I checked before using the output
* Double-checked the names, tasks, and deadlines against my original notes to make sure nothing was mixed up.
* Ensured that no tasks were assigned to the wrong person just because their name was mentioned nearby.
* Verified that blockers and open questions were clearly highlighted for the team to review.
