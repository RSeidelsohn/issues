# Issues

Issues come in many flavors, for example feature requests, bug reports, customer complaints, security alerts, team retrospectives, etc.; this page describes how our team uses issues, and how we communicate about them.

* [What is an issue?](#what-is-an-issue)
* [Public or private?](#public-or-private)
* [Score](#score)
  * [Score by priority](#score-by-priority)
  * [Score by severity](#score-by-severity)
  * [Score by category](#score-by-category)
  * [Score by combination](#score-by-combination)
* [Score discussion](#score-discussion)
  * [Score priority 0 (PO)](#score-priority-0-po)
  * [Score severity 0 (S0)](#score-severity-0-s0)
  * [Score frequency 0 (F0)](#score-frequency-0-f0)
  * [Score priority vs severity vs frequency](#score-priority-vs-severity-vs-frequency)
* [Issue template](#issue-template)
* [Postmortem triggers](#postmortem-triggers)
* [Blameless postmortems](#blameless-postmortems)


## What is an issue?

For our teams the word "issue" is a generic term such as:

Examples:

* A feature request
* A bug report
* A customer complaint
* A security alert
* A team retrospective


## Public or private?

For many of our projects we use a public issue and a private issue.

For a public issue:

* Emphasize summarization.

* Highlight actionable information.

* Omit/redact all confidential information.

For a private issue:

* Emphasize thoroughness.

* Highlight exploratory information; this helps find patterns across issues.

* Include confidential information as approriate.


## Score

We score each issue in ways that help us compare them, to know what we want to work on. There are a variety of ways to score, and here are some we've seen work well in practice.


### Score by priority

Score by a priority rank:

  * Example: "Priority 1" means do this first, "Priority 2" means do this second, "Priority 3" means do this third, etc.

  * Analogy: a todo list where priority 1 is your highest priority.

  * Pros: easy to understand what the team will work on and in what order; compatible with many bug trackers, todo list apps, and task management tools.

 
### Score by severity

Score by a severity scale:

  * Example: "Severity 1" means minimum impact, "Severity 5" means maximum impact.

  * Analogy: a severe weather warning scale, which ranges from 1 (minimum impact) to 5 (maximum impact), or an earthquake Richter scale, which ranges from magnitude 1 (trivial damage) to 9 (extreme damage), or a hospital pain numerical rating scale, which ranges from 0 (hurts the least) to 10 (hurts the most).

  * Pros: easy to understand the impact; can use many real world analogies; different evaluators can assess severity in each of their own perspectives, independent of what to work on first.


### Score by category

Score by a category name:

  * Example: The category mnemonic "MoSCoW" which we describe as "must have", "should have", "could have", "would have". Each "must have" issue is critical to the current delivery in order for it to be a success, and if even one "must have" issue is not complete, then the delivery is a failure. We like to use the phrase "would have" (instead of the usual "won't have") because in our experience with stakeholders, using "would have" wording shows that an issue is still possible to be included in a release and/or roadmap.

  * An analogy is a conversation about something you want.

  * Pros: the plain English wording of the categories has value in getting stakeholders to better understand the impact of setting a priority, compared to alternatives like High, Medium, Low.


### Score by combination

Score by a combination of priority and/or severity and/or category and/or tag:

* Example: an important customer is coming into the office in an hour to sign a contract, and the team finds a misspelling in the customer's company name on the website. 

* The sales team may score this issue as Priority 1 meaning work on it first.

* The programmer may score this issue as Severity 1 meaning the software impact is not at all severe.

* The product manager may score this issue as Category "could have" meaning the app could have the issue fixed or not because the issue doesn't actually affect the usability of the software.


## Score discussion

This section has score discussion notes. The quotes are excerpted, synthesized, and sometimes anonymized.


### Score priority 0 (PO)

Some teams choose to score by priority, and use Priority 0 (P0) as the most-important priority.

* For some teams, Priority 0 means emergency drop-everything else immediately.
  
* For some teams, Priority 0 means a release blocker that must be fixed before the next release delivery.

Our opinion is don't use P0 because many stakeholders don't understand it easily, and it does not work at all with ordinal analogies - people do say "This is my first priority" but do not say "This is my zeroth priority". 


### Score severity 0 (S0)

Some teams choose to score by severity, and use Severity 0 (S0) as the most-impactful severity. 

Our opinion is that S0 is the opposite of analogies to real-world severity systems, such as the weather storm severity score, earthquake damage severity score, and medical pain severity score.


### Score frequency 0 (F0)

Some teams score issues in terms of frequency, and use Frequency 0 (F0) as the most-often frequency, meaning the issue happens very-often and/or to very-many users.

Quotes:

* "Usually the other orthogonal assessment in addition to severity is frequency. If the bug is unlikely to be seen during regular use, then even if severity is high, the priority might be lowered. This is usually how risk is managed in my experience."

* "A developer or tester might be good at specifying how severe a bug is, but doesn't know if everyone hits the issue or just some users hit the issue. The frequency is a different dimension. The severity can then be multiplied by frequency to calculate the priority."

* "I think the formula should be: severity * frequency - ease of workaround = priority. So if any of those measures change (e.g. an easy workaround is discovered, or it's determined that the web page that is crashing is also almost never viewed) then the priority should be adjusted. Having just severity without a measure of 'how many people does this impact?' and 'just how badly does this impact them?' seems like it's missing part of the picture."

Our opinion is this approach sounds good, yet we've never seen a team use it much in practice and stick to it. We have seen teams that use this very well within the issue notes.


### Score priority vs severity vs frequency

Some teams distinguish priority and severity and frequency this way: 

  * the priority is set by the product manager's work plan for responding to an issue
  
  * the severity is a assessment of an issue's impact to one user based on the harm done.

  * the frequency is a measure of how often any user is affected.

Opinions:

  * "The QA engineer sets the severity during the initial investigation based on technical criteria. This is then one of the data points that the product manager uses during triage to set the priority, which is the controlling value from that point in the process onward."

  * "One user sometimes suffers a total crash, which then loses all their work, which makes them angry. The user would score the issue as highest severity. But if it's just one user experiencing the issue, and it's intermittent, and the user has a workaround such as saving more often, then the product manager would score the issue as low priority."

  * "Severity is how the reporter sees the problem: if it interferes with their particular use case, it's of the highest severity. Priority is how the project management team sees the bug: highest priority bugs are there because of the most valuable vocal complainers such as high-paying customers, an inconvenienced CEO, etc. Don't use the severity of the bug to rank the priority, because they're not strongly correlated."

 Our opinion is this approach sounds great in theory yet we've never seen a team use it much in practice - what we've seen happen is that a team decides to try this, then focuses solely on the priority (not severity) because the priority determines work order.
  
Quotes:

  * "My experience with priority and severity is that, while the distinction may exist academically, the reality is that most people don't understand it. The result being that the words are so frequently misused that, in practice, they are indistinguishable dimensions."

  * "Google's internal bug tracker has both priority and severity. P0 S0 is most urgent. P2 S2 is standard. P4 S4 is least urgent. It's kind of a running joke that severity is meaningless (because it isn't meaningfully different from priority). On my team for example we leave it at its default value and ignore it completely."

  * "We use a single priority field. The tester uses a heuristic to assign an initial priority (e.g., crashes are P1, cosmetic are P5). The developer uses this to prioritize which bugs to triage first, and when they've determined a new priority based on customer experience combined with app behaviour, they replace the old priority score with the new priority score. If we really needed to go back and check what the tester assigned, then we use the "history" or "revision" feature in our bug tracking app."


## Issue template

An issue template can help a team cover important areas efficiently and succinctly.

Our issue template uses:

  * Chief Complaint (CC): summarize the problem as reported by the affected person.

  * Participants (Pt): who is involved, such as users, employees, partners, specific people, etc.

  * Symptoms (Sx): what is going wrong on the surface, such as the users' perspectives, or triggers, or alerts, etc.

  * History (Hx): relevant background information, such as prior similar issues, or reports, or references, etc.

  * Diagnosis (Dx): what is going wrong under the surface, such as the root causes, or cascading causes, etc.

  * Prognosis (Px): what is the prediction, such as a forecast, potential outcomes, changes in effects, etc.

  * Fracture (Fx): what is broken, such as a failed part, or crashed application, or stuck process, etc.

  * Treatment (Tx): what we're doing to make it better, such as action items, to do lists, mitigations, etc.

Our issue template is this file: [TEMPLATE.md](TEMPLATE.md)


## Postmortem triggers

Postmortem triggers can make it easy and fast for a team to know when to do a postmortem writeup.

Postmortem triggers can include:

 * Any user-visible issues, such as unexpected outages or errors.

 * Any on-demand intervention, such as by engineers or executives.

 * Any manual incident discovery, because this shows we need monitoring.

 * Any request by a stakeholder for a postmortem, or review, or mitigation.


## Blameless postmortems

Blameless postmortems focus on the incident's symptoms, causes, and treatments, rather than focus on blaming a person or a group of people.

Blameless postmortems start by affirming that everyone has good intentions, and does their best they can at the time, with the information they have at the time.

# Posts about issues, incidents, postmortems, etc.

* [Post-Mortem Meeting Template and Tips by Brett Harned at TeamGannt on 2017-09-05](https://www.teamgantt.com/blog/post-mortem-meeting-template-and-tips)
