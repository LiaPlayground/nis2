<!--
author:   André Dietrich
email:    LiaScript@web.de
version:  1.0.0
language: en
narrator: English Female

edit:     true

logo:     assets/images/preview-card.png

comment:  Unit 3 of "NIS2 Ready" — the ten Art. 21 risk-management measures, translated into plain language and mapped onto a real IT/OT environment and your own area of responsibility.

import: https://raw.githubusercontent.com/liaScript/mermaid_template/master/README.md

@style
.measure-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
  margin: 1rem 0;
}
@media (max-width: 560px) {
  .measure-grid { grid-template-columns: 1fr; }
}
@end
-->

# The 10 Measures You Actually Need

    --{{0}}--
Welcome back. This is the unit where "comply with NIS2" stops being a slogan and becomes a list of ten concrete things. In the next fifty minutes we'll translate each of them out of legal language, watch a hospital apply a few of them for real, and then — the part that matters most — you'll mark where your own organization stands on each one.

> **NIS2 Ready — Cybersecurity Compliance for Public Administration & Critical Infrastructure**
>
> *Unit 3 of 6 · exercise · ~50 minutes · builds on Units 1–2, but stands on its own*

## Klinikum Ostheide Doesn't Know Where to Start

![Flat geometric illustration of a hospital IT and facilities team reviewing an abstract checklist against server racks and ward equipment, rendered in EU blue and gold on a neutral background.](assets/images/klinikum-compliance-review-hero.png)

    --{{0}}--
Let's meet this unit's case organization before we meet the list.

**Klinikum Ostheide** is a regional hospital network — several sites, patient-records systems, medical devices on the wards, and the building systems that keep an operating theatre running. Under NIS2 it's an in-scope health-sector entity. It has nothing to do with the Nordholm organizations from earlier units; you don't need to have met them.

    --{{1}}--
Its interim IT lead has just been handed a task that sounds simple and isn't: "get us ready for our first NIS2 compliance review." The directive says the organization must take *appropriate and proportionate* risk-management measures — ten categories of them. On paper that's four words. In practice, "ten measures, risk-appropriate" feels abstract until someone translates it into *this* hospital, with *these* systems.

      {{1}}
> [!WARNING] "Ten measures, risk-appropriate" — where do you even begin?
> The interim IT lead isn't missing knowledge. They're missing a *translation*: from a legal catalogue into "what does this actually mean I have to do here, on Monday, in this building?"

    --{{2}}--
That translation is this whole unit. And here's the first thing to get straight, because it's the single most common misread of these ten measures.

### This Is Not Just an IT Department Problem

    --{{0}}--
When people hear "ten cybersecurity measures," they picture firewalls and servers and think: *that's IT's job, not mine.* Some of the ten are indeed technical. But several are squarely organizational — who's allowed to do what, who gets trained, what happens when a supplier fails. Those aren't solved in a server room.

> [!IMPORTANT] Keep this in mind for the whole unit
> Of the ten measures, roughly half are **organizational or people-focused**, not technical: governance, training, access policies, supplier management, business continuity. If you're not in IT, this list is still about you — and the worked example below will keep flagging which measures are org-wide, not IT-only.

## What Art. 21 Actually Requires

    --{{0}}--
Before the list itself, one framing sentence — because it changes how you read all ten.

NIS2 does **not** hand you a shopping list of products to buy. It doesn't name a single tool, brand, or certificate. It requires measures that are *appropriate and proportionate* to your actual risk — sized to how big you are, how exposed you are, and how bad an incident would be.

    --{{1}}--
That word — proportionate — is doing a lot of work, and it's good news.

      {{1}}
> [!NOTE] "Appropriate and proportionate" — the legal phrase, once
> This is **Art. 21(1)**. It means a small municipal office and a large hospital network can both satisfy the *same* measure with very different implementations. Nobody expects a 40-person authority to run a 24/7 security operations centre. The obligation scales to you. *(We come back to what that looks like near the end of this unit.)*

## The Ten Measures, in Plain Language

    --{{0}}--
Here they are — all ten, from Art. 21(2), points (a) to (j). For each one: the everyday meaning first, then the formal name in brackets so you recognize it later. Read down the "What it means for you" column; the bracketed terms are there for reference, not for memorizing.

| #  | What it means for you (plain language)                                                   | Formal category (Art. 21(2))                                    | Mostly…        |
|----|------------------------------------------------------------------------------------------|-----------------------------------------------------------------|----------------|
| 1  | Know what could go wrong, and write down the rules for keeping systems safe              | Risk analysis & information-system security policies (a)        | Organizational |
| 2  | Have a plan for *when* something goes wrong — not just *if*                              | Incident handling (b)                                           | Both           |
| 3  | Be able to keep running (and recover) after a disruption — backups, disaster recovery    | Business continuity & crisis management (c)                     | Both           |
| 4  | Make sure the suppliers and services you depend on aren't your weak link                 | Supply-chain security (d)                                       | Organizational |
| 5  | Build and buy systems securely, and deal with vulnerabilities when they surface          | Security in acquisition, development & maintenance (e)          | Technical      |
| 6  | Check that your measures actually work — don't just assume they do                       | Assessing the effectiveness of measures (f)                     | Organizational |
| 7  | Teach people basic cyber hygiene, and train them                                         | Cyber hygiene & security training (g)                           | People         |
| 8  | Use encryption where it makes sense, with clear rules for it                             | Cryptography & encryption policies (h)                          | Technical      |
| 9  | Control who has access to what — staff security, access rights, knowing your assets      | HR security, access control & asset management (i)              | Both           |
| 10 | Make logins hard to fake, and keep a communication channel that survives an emergency    | Multi-factor authentication & secured emergency comms (j)       | Technical      |

![Flat geometric infographic showing a 2x5 grid of ten abstract icons representing NIS2 Article 21 risk-management measures, split into two color-coded groups for organizational and technical measures, in EU blue and gold on a neutral background.](assets/images/ten-measures-icon-grid.png)

    --{{1}}--
Notice the last column. Count the ones that aren't purely technical — risk rules, supplier management, effectiveness checks, training, access policies. That's most of the list. This is exactly why "hand it to IT and forget it" fails a compliance review.

      {{1}}
> [!TIP] The one-line test for whether a measure is "yours"
> Ask: *could this fail because of a decision, a habit, or a gap in responsibility — rather than a missing piece of technology?* If yes, it's at least partly an organizational measure, and it needs an owner outside IT.

## A Quick Feel for Where You Stand

    --{{0}}--
Before the worked example, a thirty-second interactive aside — and your first taste of something you'll do properly in Unit 6. Don't overthink it: of the ten measures, roughly how many are genuinely **in place**, how many are only **partial** (started, or untested), and let the rest fall into **missing**. Move the two sliders and watch your picture take shape.

<section>

> [!TIP] 👉 This one is interactive — drag the sliders
> The two sliders below are live. As you move them, the bar chart underneath recomputes and recolors instantly, and "missing" fills in the remainder for you. Try it — nothing here is saved or graded.

Measures genuinely **in place** (working, and you could show evidence):

<script input="range" value="3" min="0" max="10" step="1" output="InPlace">@input</script> in place

Measures only **partial** (started, incomplete, or untested):

<script input="range" value="2" min="0" max="10" step="1" output="Partial">@input</script> partial

<script style="display: inline-block; width: 100%">
let inplace = @input(`InPlace`)
let partial = @input(`Partial`)
// keep the two sliders honest: they can't sum to more than ten
let capped_partial = Math.min(partial, 10 - inplace)
let missing = Math.max(0, 10 - inplace - capped_partial)
let option = {
  title: {
    text: "Your ten NIS2 measures, right now",
    left: "center",
    textStyle: { fontSize: 15 }
  },
  tooltip: { trigger: "axis" },
  xAxis: { type: "category", data: ["In place", "Partial", "Missing"] },
  yAxis: { type: "value", max: 10, minInterval: 1, name: "measures" },
  series: [{
    type: "bar",
    barWidth: "55%",
    data: [
      { value: inplace,        itemStyle: { color: "#1B7A44" } },
      { value: capped_partial, itemStyle: { color: "#E6A700" } },
      { value: missing,        itemStyle: { color: "#C0392B" } }
    ],
    label: { show: true, position: "top", fontWeight: "bold" }
  }]
}
"HTML: <lia-chart style='width:100%;height:320px' option='" + JSON.stringify(option) + "'></lia-chart>"
</script>

    --{{1}}--
Whatever shape that chart just took — a wall of red, a healthy block of green, or something in between — it's a snapshot, not a grade. The point isn't the exact numbers; it's that "compliant / not compliant" was always a false choice. Readiness is a spectrum, and you can see today where on it you sit.

      {{1}}
> [!NOTE] Look at what just happened here
> Two sliders, a live bar chart that recolors and recomputes as you drag, "missing" filling in the remainder automatically — and **all of it is about a dozen lines of plain text inside this document**. No app, no server, no plugin, no separate tool. Double-click the chart in LiaScript to see the code behind it. In Unit 6 this same idea grows into your full **NIS2 Readiness Score**.

</section>

## Worked Example: Klinikum Ostheide Applies Four of the Ten

    --{{0}}--
Let's stop listing and start applying. Here are four of the ten measures, worked through against Klinikum Ostheide's actual environment — showing the *reasoning*, not just ticking a box. Read across all four: notice how the same directive produces four completely different kinds of work — testing a backup, deliberately *not* over-securing, writing a contract clause, and training people.

<section>

<div class="measure-grid">

<div style="border: 1px solid #d7e0ea; border-top: 4px solid #1B7A44; border-radius: 8px; padding: 1rem; background: #ffffff;">

#### Measure 3 — Business continuity: the patient-records backup

Klinikum Ostheide keeps electronic patient records. If those records are encrypted by ransomware on a Friday night, can the wards still function on Saturday morning?

- **Appropriate implementation:** regular, *tested* backups kept offline or isolated, plus a recovery procedure a stressed night-shift team could actually follow.
- **Why "tested" matters:** a backup nobody has ever restored is a hope, not a plan. This is business *continuity*, not "a backup somewhere."

</div>

<div style="border: 1px solid #d7e0ea; border-top: 4px solid #003399; border-radius: 8px; padding: 1rem; background: #ffffff;">

#### Measure 10 — MFA for clinical-staff logins

Clinicians log into sensitive systems, often from shared workstations, often in a hurry.

- **Appropriate implementation:** multi-factor authentication on clinical systems — a second factor beyond a password, chosen so it doesn't slow down emergency care.
- **The proportionality tension:** security that blocks a clinician mid-resuscitation is the *wrong* security. Here "appropriate" explicitly means fast — the measure and patient safety are designed together.

</div>

<div style="border: 1px solid #d7e0ea; border-top: 4px solid #8A6D00; border-radius: 8px; padding: 1rem; background: #ffffff;">

#### Measure 4 — Supply-chain security: the device vendor

A modern hospital runs on outside equipment — imaging systems, monitoring devices, their remote-maintenance links.

- **Appropriate implementation:** know which suppliers can reach into your systems, and hold them to security expectations in the *contract* — their weak password becomes your incident.
- **Why it's organizational:** solved in procurement and contracts, not a firewall rule. Often nobody in IT even *sees* the vendor's remote-access channel until it's the entry point.

</div>

<div style="border: 1px solid #d7e0ea; border-top: 4px solid #C0392B; border-radius: 8px; padding: 1rem; background: #ffffff;">

#### Measure 7 — Cyber hygiene & training: everyone

The person who clicks the convincing phishing email is usually not in IT.

- **Appropriate implementation:** basic, recurring training for *all* staff — spotting suspicious messages, reporting fast, not reusing passwords — plus the leadership training NIS2 requires (Unit 5).
- **The point:** this measure has no server in it at all. It's the clearest proof that NIS2 compliance is an organization-wide job.

</div>

</div>

    --{{1}}--
Four measures, four very different shapes — one about testing backups, one about *not* over-securing, one about contracts, one about people. That variety is the real lesson: "ten measures" is not ten IT tasks.

      {{1}}
> [!NOTE] Proportionality in one sentence
> A large hospital network tests backups across many sites and audits dozens of vendors; a 40-person municipal office might test one backup and manage three suppliers. **Same measures, sized to the organization** — that's Art. 21 working as intended.

</section>

## Now Map the Ten Against Your Own Area

    --{{0}}--
Here's the exercise this unit is built around. For each of the ten measures, mark where your organization — or the part of it you're responsible for — actually stands today. Be honest: a wall of "missing" is a *useful* result, not a failure. It's a to-do list you didn't have five minutes ago.

    --{{1}}--
Use the three columns: **In place** (working, and you could show evidence), **Partial** (started, incomplete, or untested), **Missing** (not really there yet).

      {{1}}
<section>

[( In place )( Partial )( Missing )]
[                                  ] 1 — Risk rules & security policies written down
[                                  ] 2 — A plan for handling incidents when they happen
[                                  ] 3 — Tested backups & a recovery / continuity plan
[                                  ] 4 — Supplier / supply-chain security in contracts
[                                  ] 5 — Secure system acquisition & vulnerability handling
[                                  ] 6 — Checking that the measures actually work
[                                  ] 7 — Cyber-hygiene basics & staff training
[                                  ] 8 — Encryption used where it makes sense
[                                  ] 9 — Access control, HR security & asset inventory
[                                  ] 10 — Multi-factor logins & emergency communications

    --{{0}}--
Now the two follow-ups that turn the grid into action.

Pick **one** measure you marked "Missing" or "Partial". What is the single smallest next step that would move it forward — and who would own it?

[[___ ___ ___]]

Which of the ten surprised you by being more *organizational* than technical — something you'd previously have assumed was "IT's problem"?

[[___ ___ ___]]

> [!NOTE] Not graded, not filed anywhere
> This worksheet is a private self-diagnosis. Nothing here is scored or stored beyond your own browser — it exists to give you a starting map, not a report card.

</section>

## Wrap-Up & Self-Check

    --{{0}}--
Three quick questions, not graded — a gut-check on how the ten measures actually work.

**1. What does "appropriate and proportionate" mean for the Art. 21 measures?**

- [( )] Every organization must implement all ten to the same technical standard
- [(X)] The measures scale to your organization's size, exposure, and risk
- [( )] Small organizations are exempt from the measures entirely
******

> Proportionality is the whole point: same ten categories, implementation sized to you. It's neither "one identical standard for all" nor "small = exempt."

******

**2. Which of these is *not* primarily an IT-department task?**

- [( )] Multi-factor authentication on system logins
- [( )] Encryption of sensitive data
- [(X)] Supply-chain security in supplier contracts
******

> Supply-chain security lives in procurement and contracts — a classic organizational measure. It's the kind of item that quietly fails a review because "IT will handle it," when IT never sees the contract.

******

**3. True or false: buying the right security product is enough to satisfy Art. 21.**

- [( )] True
- [(X)] False
******

> False — Art. 21 names no products at all. Several measures (risk rules, training, supplier management, effectiveness checks) can't be bought; they have to be organized and owned.

******

### Before You Go: One Quick Reflection

Look back at your self-assessment grid. If a compliance review happened next month, which single measure would you least want them to look at closely — and what's stopping you from fixing it first?

[[___ ___ ___]]

### Up Next

**Unit 4 — Handling & Reporting Incidents.** We'll stay with Klinikum Ostheide — but this time the incident is real, not a drill. When the Monday-morning moment *isn't* a false alarm, NIS2 puts a clock on you: 24 hours, 72 hours, one month. Unit 4 shows exactly what's due, and when.

**References:**

1. Directive (EU) 2022/2555 (NIS2), Art. 21 (cybersecurity risk-management measures, incl. points a–j) — `data/cybersichert.pdf`
2. Directive (EU) 2022/2555 (NIS2), Art. 20 (governance — management-body approval/oversight, expanded in Unit 5) — `data/cybersichert.pdf`
3. Course Agenda — `journal.md` → `## Agenda`
