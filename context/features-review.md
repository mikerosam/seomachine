# features.md — Critical Review Against Customer Profiles

**Reviewed against**: Four customer persona documents, seven customer interview transcripts (Wingcopter, Evolito, Mercedes, HAWE, Origen Carbon, Modelon, Rolls-Royce), and the Quix value proposition document (v2).

**Verdict summary**: features.md is most calibrated for the Software/Data Engineer persona. It substantially underserves R&D Directors (the economic buyer) and Systems Engineers (the primary champion). Test Engineers are well-described in isolation but misunderstood in their role in the buying journey. Seven cross-cutting structural problems affect all four personas.

---

## Persona 1: R&D Director

**Primary job** (persona doc): Fix the data and tooling infrastructure holding engineering teams back — without requiring a software team.

**What resonates:**

The competitive differentiator sections map directly to the R&D Director's known failure history. This persona has typically tried enterprise platforms (too rigid), corporate IT (too slow), and data science teams (wrong priorities) before reaching Quix. features.md addresses all three failure modes in the "Competitive Differentiators" section — that content is accurate and useful.

The Viessmann quote is the single most powerful piece of content for this persona: *"We gave you the problem. You said, okay, we have an idea. That was completely new for us — all the others did more or less what we said."* It captures the proactive expertise differentiator that every R&D Director in the interview set responded to.

"Start with one rig. Prove the value before committing budget." correctly identifies the risk-reduction logic this persona needs. Capital decisions require a credible proof point — the POC framing is right.

**What's missing or misdescribed:**

**1. The headline ROI numbers are buried.**
Viessmann's 50% faster feature development, 75% reduction in software testing time, and 2.5x cheaper testing are in the Social Proof section — the last substantive section before the objections Q&A. R&D Directors make capital budget decisions. Those numbers belong at the top of their use case section, not at the end of the document. Any R&D Director reading to justify a £4,200/month commitment needs to see the outcome evidence first.

**2. The 800,000-euro Garrett story is filed under the wrong persona.**
This is the most financially legible piece of customer evidence in the entire document. A technician left, the configuration record for a wire harness test was lost, and rerunning it would have cost 800,000 euros and 18 months. It sits in the Test Engineer use case section because a test engineer was involved in the failure. But the person who would have had to approve the 800,000-euro retest is an R&D Director. This story should anchor the R&D Director section.

**3. Multi-site coordination is invisible.**
Three interview calls surfaced this as a genuine need: Wingcopter (GDPR compliance across Azure, distributed operations), HAWE (multi-location PLM integration), Origen Carbon (remote monitoring of rigs in North Dakota from head office). This is not an edge case — it is the default reality for any engineering company with multiple test facilities, simulation environments, and geographically distributed teams. Multi-cluster support exists in the Scale plan but is listed as a technical feature, not as a leadership use case. There is no mention anywhere of "centralise test data and workflows across sites."

**4. The "data science team exhaustion" trigger is missing from the use case section.**
The persona document identifies this as a major trigger context: "We've been waiting for corporate IT or data science to deliver this for two years." This appears in the objections section ("IT has been promising us data tooling for two years") but not in the R&D Director use case section, where it belongs as an empathy signal. R&D Directors reading the use case section should recognise their situation before being presented with capabilities.

**5. The use case section lists capabilities, not outcomes.**
The four R&D Director bullets — eliminate redundant testing, reduce cycle time, start with one rig, get lab visibility — are all framed as capabilities ("Eliminate redundant testing caused by inability to find or trust historical data"). R&D Directors evaluate purchases on outcomes: R&D cycle time reduction, cost per development cycle, capital expenditure avoided. The use case section should be rewritten as an ROI argument, with the Viessmann numbers leading, not trailing.

**Prioritisation problem:**

The R&D Director use case section starts correctly (eliminate redundant testing) but immediately pivots to operational visibility features (lab utilisation, data throughput, bottleneck visibility). Interview evidence is clear: R&D Directors are triggered by vendor failure and cost/time pressure — not by a desire for better dashboards. Lab visibility is a secondary benefit that supports the primary argument; it should not share equal billing with cycle time reduction and cost elimination.

---

## Persona 2: Systems Engineer

**Primary job** (persona doc): Quickly figure out configuration, trustworthiness, and meaning of test results — so I can make engineering decisions.

**What resonates:**

Configuration Context Linking (Core VP #1) leads the document and is exactly the right feature to lead with for this persona. The configuration-data gap is the #1 stated pain in the persona document, confirmed across every interview where a systems or development engineer was involved (Evolito, Viessmann, Rolls-Royce, Garrett).

"No black box, no lock-in" resonates. Systems Engineers who have been burned by enterprise platforms are deeply averse to any solution that obscures what's happening with their data.

The use case section covers the right territory: find historical test runs, determine whether an anomaly is a sensor fault or real system behaviour, compare against baselines. These directly mirror the persona's stated job.

**What's missing or misdescribed:**

**1. "Works alongside existing tools" is never stated.**
The persona document is explicit: not forcing changes to existing processes is a critical requirement. Systems Engineers use Dewesoft, LabVIEW, National Instruments, their own DACQ setups — and they will not adopt a platform that requires them to change any of it. The integrations section lists connectors accurately, but it frames them as Quix capabilities ("here's what Quix supports") rather than reassurance ("Quix works with what you already have — nothing changes for the people running tests"). This is a primary sales objection that features.md does not address. It should be a named benefit, not a connector list.

**2. The tribal knowledge pain is filed under the wrong persona.**
The Garrett wire harness example — "what was the hardware state on test run 47?" has an answer, even after the technician who ran it has left — is in the Test Engineer use case section. Systems Engineers are the primary victims of tribal knowledge loss. They are the ones making engineering decisions that depend on historical test data, and they are the ones blocked when a departing technician takes the configuration record with them. This story belongs in the Systems Engineer section first.

**3. Maintenance and duty cycle blindness is named but not explained.**
Configuration Context Linking mentions "maintenance history linked at ingestion" but the benefit description doesn't connect to the specific failure mode that matters to a Systems Engineer: *"I can't trust this sensor reading because I don't know whether the equipment was recently serviced or is operating at the edge of its duty cycle."* The feature exists. The pain connection is missing.

**4. The natural language SQL agent signposting is absent from this section.**
The upcoming natural language query capability is the single most compelling upcoming feature for Systems Engineers — they understand the engineering problem fluently but do not write SQL. It is correctly flagged as upcoming in the Upcoming Features section. However, the Systems Engineer use case section contains no forward-reference to it. A Systems Engineer reading the use case section will not know this capability is coming unless they read through the entire document to the Upcoming Features section.

**5. Supplier validation data quality is absent entirely.**
The persona document identifies this as a named pain: Systems Engineers receive test and simulation data from external suppliers and need to validate its integrity before relying on it. There is no mention of this use case — "can I trust data from a supplier?" — anywhere in features.md.

**Prioritisation problem:**

The 9 core value propositions are listed in a fixed order that does not vary by persona. For Systems Engineers, VPs #2 (Managed Infrastructure), #3 (Python-Native), #5 (Git Integration), and #6 (Environment Isolation) are largely irrelevant — they do not build or manage pipelines. Their relevant VPs are #1 (configuration linking), #4 (data warehouse/query), #7 (self-service), and #8 (open architecture). A Systems Engineer reading features.md from the top encounters four consecutive sections of content that has no bearing on their job before reaching anything useful.

---

## Persona 3: Software/Data Engineer

**Primary job** (persona doc): Get domain engineers data capabilities — without spending months building infrastructure.

**What resonates:**

This is the persona the document is most accurately calibrated for. Core VPs #2 (Managed Infrastructure), #3 (Python-Native), #5 (Git Integration), #6 (Environment Isolation), #8 (Open Architecture), and #9 (BYOC) are all strong matches for how this persona thinks about buying decisions.

The benefit description for Managed Infrastructure — "a single software or data engineer can stand up what would normally require a team of three to five, without opening an IT ticket" — directly addresses the solo-under-pressure experience named in the persona document.

The integrations section (Sources/Sinks APIs, AI-built connectors for anything) addresses the API normalisation burden that consumes engineering time.

**What's missing or misdescribed:**

**1. The "stakeholder credibility" problem is unaddressed.**
Software engineers in this role are typically the internal platform advocate. They must build the case upward (to the R&D Director for budget) and across (to Systems Engineers for adoption). features.md doesn't frame any feature as "makes your internal business case easier." The Viessmann quote and ROI numbers are present but positioned as Quix differentiators rather than as evidence this engineer can use in an internal budget conversation. A software engineer who needs to get their R&D Director to approve £4,200/month needs ammunition, not just feature descriptions.

**2. Schemaless ingestion has no benefit statement.**
Rapidly changing data schemas is listed as a major pain in the persona document. Engineers who have spent weeks writing schema migrations, dealing with test rigs that change output formats, and maintaining compatibility across firmware versions will immediately recognise this problem. Schemaless ingestion is listed as a bullet under Data Management ("Write data without a predefined table structure; schema evolves with the data") with no benefit framing. This deserves: *"Test rig outputs change with firmware updates and hardware swaps. Quix ingests data without requiring a predefined schema — no migration scripts, no breaking changes, no maintenance window."*

**3. "Stop being the data query gatekeeper" framing is absent.**
The natural language SQL agent (upcoming) directly addresses one of the Software/Data Engineer's most frustrating recurring tasks: being asked to run ad hoc queries on behalf of domain engineers who can't write SQL. The feature is described as a benefit for Systems Engineers but is not framed as relief for Software Engineers who are currently fielding every query request. Both framings are true and both should be present.

**4. Pricing doesn't support a business case.**
The pricing section shows plan tiers but not capacity. Interview evidence shows this matters operationally: the Wingcopter call discussed node-based pricing in detail; the Modelon call negotiated per-node licensing terms. The software engineer writing the internal business case needs to know what £4,200/month actually provides in operational terms — nodes, data volume, number of concurrent deployments. The pricing section as written reads as a menu, not a justification.

**5. The framing goal is wrong.**
The document consistently frames the Software/Data Engineer's goal as "build infrastructure." The persona document is explicit: their primary job is enabling domain engineers to be self-sufficient. The document should be reoriented from "here's what you can build" to "here's how domain engineers get what they need without coming back to you, and here's what you no longer have to maintain." These are different stories.

**Prioritisation problem:**

The core VP list inadvertently deprioritises what this persona actually cares about. The most important feature for a Software Engineer enabling domain engineers is arguably #7 (Self-Service) — the thing that gets Systems Engineers off their backlog — followed by #4 (Data Warehouse with natural language query, coming). But #7 is listed sixth, after two pipeline management features (#5, #6) that are internal engineering concerns rather than stakeholder-facing capabilities.

---

## Persona 4: Test Engineer

**Primary job** (persona doc): Complete tests accurately and efficiently. Relationship to Quix: data source and end user, not a decision-maker.

**What resonates:**

The Test Engineer use case section is the most specific and evidence-rich section in the document. Live data monitoring (the Garrett USB connector example), automatic upstream flow, configuration retroactive answerability, high-volume/high-frequency data handling (Fifer Vacuum 100kHz, Garrett 10 points × 25 channels × 3 months) — all directly address real, named pains from customer evidence.

The specificity of the evidence is appropriate for the audience: Test Engineers are concrete thinkers who respond to operational examples more than abstract value propositions.

**What's missing or misdescribed:**

**1. The persona's buying role is misunderstood.**
Test Engineers are not buyers. They are end users who can be internal champions or opponents. The use case section is written as if its purpose is to convert a Test Engineer reading it — but Test Engineers do not approve procurement decisions. The section's actual function should be to give Systems Engineers and R&D Directors evidence about what their Test Engineers will experience. The framing should shift: *"What changes for Test Engineers"* rather than *"What Test Engineers can do with Quix."*

**2. "Invisible by design" is never stated.**
Test Engineers are under pressure to run tests, not manage data infrastructure. The most important reassurance for this persona is: *"You don't have to change how you work. Quix runs in the background and captures everything automatically."* This is implied by several feature descriptions but never said directly. Test Engineers who perceive Quix as something they have to learn or maintain will become internal blockers, not champions.

**3. The format list reads as a spec, not as relief.**
MDF4, BLF, TDMS, HDF5, MAT, Parquet, CSV — these formats are listed correctly and the file listener description is accurate. But the benefit for a Test Engineer isn't "Quix supports these formats." It is: *"Whatever file format your rig or DAQ system outputs, it goes in automatically — no export step, no format conversion, no manual transfer."* The current description is written for a software engineer who is evaluating integration compatibility, not for a test engineer who is tired of manually copying files to SharePoint.

**4. The Garrett and Fifer Vacuum examples are edge cases.**
800,000 euros and 100kHz are exceptional scenarios. Most Test Engineers work in companies where the stakes are lower and the data volumes are smaller. A simpler, more relatable story — the test engineer who spent 20 minutes at the end of every test run manually uploading files, labelling them in a spreadsheet, and emailing the team — would land for the majority of this audience. The existing examples are appropriate for the R&D Director and Systems Engineer sections; the Test Engineer section needs a story about an ordinary day.

**Prioritisation problem:**

The Test Engineer section is appropriately placed last in the use cases hierarchy, reflecting their position in the buying journey. However, several of the Test Engineer-specific benefits — tribal knowledge protection, live monitoring, automatic configuration capture — are more useful as evidence in the Systems Engineer and R&D Director sections. The evidence is in the right section for completeness but in the wrong sections for persuasion.

---

## Cross-Cutting Issues

### 1. The flat VP list serves no persona cleanly

Nine core value propositions are presented in a fixed order: Config → Infrastructure → Python → Data Warehouse → Git → Environments → Self-Service → Open Architecture → BYOC. Reading order implies priority. This sequence is optimised for a Software/Data Engineer but makes R&D Directors and Systems Engineers wade through four or five irrelevant sections before reaching content relevant to them. There is no entry point by role.

The fix is not to duplicate the VPs but to add a "by role" navigation at the top — a short table or set of callouts that says: *"If you're an R&D Director, start with #1, #4, #7. If you're a Systems Engineer, start with #1, #4, #7, #8. If you're a Software/Data Engineer, read all. If you're a Test Engineer, start with #1, #7."*

### 2. "Proactive expertise" appears once but is the defining differentiator

Every customer call confirmed this. Viessmann named it explicitly. Evolito referenced it in how they described the demo experience. Rolls-Royce and Mercedes both arrived at Quix after vendor relationships that were purely order-taking. HAWE described previous vendors as "doing what we asked without proposing anything." This is not a competitive differentiator bullet — it is Quix's most consistently cited identity in the customer record. It should be a named core value proposition, positioned as: *"Quix proposes solutions your engineers haven't thought to ask for yet."*

### 3. The POC model is underweighted for its conversion importance

"Start with one rig. Prove the value before committing budget." appears twice in the document. Every customer interview (7/7) converged on the POC model as the actual path to purchase. Wingcopter discussed a £5k/month POC structure. Evolito committed to a 1-3 month POC with their CTO. HAWE requested a small POC first due to resource constraints. Origen Carbon agreed to a consultation and professional services engagement before any platform commitment. The POC model is not a pricing note — it is the primary mechanism by which every prospect in the interview set became a customer. It needs its own named section explaining: what a POC engagement looks like, how long it typically takes, what it costs, and what outcome it produces.

### 4. The 800,000-euro Garrett story is in the wrong place

This is the most financially legible piece of customer evidence in the entire document. It belongs in the R&D Director section as the lead evidence for "eliminate redundant testing," cross-referenced in the Test Engineer section. Its current placement in the Test Engineer section means the audience most likely to act on it — R&D Directors making budget decisions — will never encounter it in their natural reading path.

### 5. Pricing doesn't describe a buying journey

The four plan tiers are accurately described. What's missing is the journey: most buyers start with a POC (outside the listed plans), then move to Professional or Scale based on data sovereignty requirements and deployment environment. The interview evidence is consistent on this — no prospect went from "first contact" to "Scale plan" without an intermediate evaluation step. The pricing section should describe the evaluation path, not just the destination tiers.

### 6. The document violates its own content guidelines

The Content Creation Guidelines at the bottom of features.md state: *"Lead with the engineering problem, not the feature name."* The core VP section does the opposite — every VP is headed by a feature name (Configuration Context Linking, Managed Production Infrastructure, Python-Native Development). The conversion angle — the problem-first framing — is buried as a sub-bullet. The document's structure contradicts its own stated principle. Either the section headers should be rewritten to lead with the problem, or the conversion angles should be promoted to the heading level.

### 7. Multi-site coordination has no named use case

Wingcopter, HAWE, and Origen Carbon all involved geographically distributed operations needing coordinated data infrastructure. This is not an edge case — the majority of engineering organisations with serious R&D programmes operate across multiple facilities. Multi-cluster support is listed in the Scale plan features. There is no use case framing anywhere in the document for: *"Centralise test data, configuration, and workflows from multiple sites, without moving data across jurisdictions or requiring engineers at each site to adopt new tooling."* This is a named trigger for R&D Directors and should be a named use case.

---

## Priority Change List

All changes implemented in commit `10f4bb9` (March 2026).

| Priority | Change | Primary Persona | Status |
|----------|--------|-----------------|--------|
| High | Move 800k Garrett story to R&D Director section; cross-reference in Test Engineer section | R&D Director | ✓ Done |
| High | Move Viessmann ROI stats (50%/75%/2.5x) to R&D Director use case section | R&D Director | ✓ Done |
| High | Add "works alongside existing tools, nothing changes for test operators" as an explicit feature/benefit | Systems Engineer | ✓ Done |
| High | Move tribal knowledge/config loss pain to Systems Engineer section | Systems Engineer | ✓ Done |
| High | Reframe Software/Data Engineer section around "domain engineers become self-sufficient" not "build infrastructure" | Software/Data Engineer | ✓ Done |
| High | Add "proactive expertise" as a named core VP, not a competitive differentiator footnote | All | ✓ Done |
| High | Add POC model as a named section with structure, timeline, cost, and typical outcome | All | ✓ Done |
| Medium | Add multi-site coordination as a named use case in R&D Director section | R&D Director | ✓ Done |
| Medium | Rewrite schemaless ingestion with a benefit statement for engineers dealing with changing schemas | Software/Data Engineer | ✓ Done |
| Medium | Add by-role navigation at top of document | All | ✓ Done |
| Medium | Add maintenance/duty cycle blindness benefit to Configuration Context Linking description | Systems Engineer | ✓ Done |
| Medium | Add forward-reference to natural language SQL agent in Systems Engineer use case section | Systems Engineer | ✓ Done |
| Medium | Add "stop being the data query gatekeeper" framing for natural language SQL agent | Software/Data Engineer | ✓ Done |
| Medium | Add "invisible by design — nothing changes for test operators" framing to Test Engineer section | Test Engineer | ✓ Done |
| Medium | Add a typical (non-exceptional) Test Engineer workflow story alongside Garrett/Fifer Vacuum examples | Test Engineer | ✓ Done |
| Low | Add capacity/operational detail to pricing section (nodes, data volume, deployments per tier) | Software/Data Engineer | Not implemented |
| Low | Add supplier validation data quality use case | Systems Engineer | ✓ Done |
| Low | Connect pricing tiers to buying journey (POC → Professional → Scale) | All | ✓ Done |
| Low | Rewrite core VP section headers to lead with the problem, not the feature name | All | ✓ Done |

---

*Review based on: features.md (as of March 2026), persona documents for all four customer profiles, seven customer interview transcripts (Wingcopter Oct 7, Evolito Oct 6, Mercedes Oct 10, HAWE Sep 17, Origen Carbon Sep 12, Modelon Sep 29, Rolls-Royce Oct 15), and value proposition document v2.*
