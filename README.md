# Decision tree process flow
🎓 Gift Acknowledgement Decision Tree
An interactive, browser-based decision tree that guides gift processing staff through the correct acknowledgement letter workflow for all charitable gifts of $250 or more.

Overview
Managing donor acknowledgement letters in higher education fundraising involves layered logic — the right letter type, the right body language, and the right signature authority all depend on a combination of gift amount, gift source, delivery channel, and donor assignment. This tool makes that logic navigable for any staff member, without needing to memorize a policy manual.
Built as a fully self-contained HTML file, it runs in any browser with no backend, no login, and no dependencies.

Features

Step-by-step guided flow — one decision at a time, no overwhelming forms
Breadcrumb navigation — see where you are and jump back to any earlier step
Full signer routing — letter signature authority is determined by gift amount and whether the donor is prospect-managed
Special gift type modifiers — handles stock gifts, IRA distributions, Donor Advised Funds, event-based gifts, and tribute gifts with the correct letter body requirements for each
Tribute gift logic — automatically surfaces the two-letter requirement (one for the donor, one for the tribute acknowledgee) with the correct language rules for each
DAF flag — flags the open question about whether an acknowledgement is required at all, preventing processing errors
Mobile-friendly — responsive layout works on phones and tablets


Decision Logic Covered
Channel
ChannelUnder $250$250 or moreOnlineAuto tax receipt onlyAuto receipt + paper Tax/Ack Combo letterOfflineN/A (all receive letters)Paper Tax/Ack Combo letter
Signature Authority
Gift AmountStandard DonorProspect-Managed Donor$250 – $999Director of Donor RelationsProspect Manager or Sr. Director of Development$1,000 – $9,999AVP (mid-level officer)AVP (mid-level officer)$10,000 – $74,999Vice PresidentVice President$75,000+University PresidentUniversity President
Special Gift Type Modifiers
Gift TypeLetter TypeBody RequirementStockTax/Ack ComboMust list shares, high/low/median valueIRATax/Ack ComboMust include IRA distribution languageDAFAck Only (no tax language)Confirm if acknowledgement is requiredEvent/GalaTax/Ack ComboMust list tickets, tax-deductible amount, purchase + donation detailTribute — DonorTax/Ack ComboModified with tribute/memorial languageTribute — RecipientAck Only (no tax language)Notifies acknowledgee of gift in their honor

Note: Stock can be the vehicle for any gift type. When it is, stock body requirements layer on top of the primary gift type rules.


Tech Stack

Vanilla HTML, CSS, JavaScript — zero frameworks, zero build steps
Google Fonts (DM Serif Display + DM Sans) for typography
Fully self-contained — copy the .html file anywhere and it works


Use Case
This tool was built to support a conversation with a letter management software vendor about whether their platform could handle the full conditional logic this workflow requires. The five key capability questions surfaced were:

Can templates inject different body copy based on gift type (stock data, IRA language, event details, tribute language)?
Can one gift record automatically generate two letters with different templates and tax language (tribute scenario)?
Can the system suppress tax language for DAF gifts regardless of the standard threshold rule?
Can signer routing read a prospect assignment field to route to the correct signatory?
Can an automatic digital receipt and a separate paper letter be coordinated without duplicate tax language?


Files
FileDescriptiongift_acknowledgement_decision_tree.htmlThe interactive decision tree — open in any browsergift_acknowledgement_decision_tree.pptx7-slide PowerPoint deck covering the full workflowgift_acknowledgement_decision_tree.docxWord document with full decision tables for referencegift_acknowledgement_decision_tree.mdMermaid diagram code for import into Lucidchart or similar tools

Background
Higher education advancement offices process gifts from dozens of sources — online giving platforms, wire transfers, stock donations, donor advised funds, IRA charitable rollovers, event registrations, and more. Each source carries different tax implications, different letter requirements, and different approval chains. This project documents and operationalizes that logic in a format that's easy to share, easy to use, and easy to hand off.
