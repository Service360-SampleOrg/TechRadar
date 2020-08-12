# TechRadar

This repo contains Service360 TechRadar.

|Type|
|---|
|Support|

## What is the Tech Radar?
The Tech Radar is a list of technologies, complemented by an 
assessment result, called ring assignment. 

### Assessment rings 

We use four rings with the following semantics:

- ADOPT — Technologies we have high confidence in to serve our purpose, 
also in large scale. Technologies with a usage culture in our 
production environment, low risk and recommended to be widely used.
- TRIAL — Technologies that we have seen work with success in project 
work to solve a real problem; first serious usage experience that 
confirm benefits and can uncover limitations. TRIAL technologies are 
slightly more risky; some engineers in our organization walked 
this path and will share knowledge and experiences.
- ASSESS — Technologies that are promising and have clear potential 
value-add for us; technologies worth to invest some research and 
prototyping efforts in to see if it has impact. ASSESS technologies 
have higher risks; they are often brand new and highly unproven 
in our organisation. You will find some engineers that have knowledge 
in the technology and promote it, you may even find teams that have
started a prototyping effort.
- HOLD — Technologies not recommended to be used for new projects. 
Technologies that we think are not (yet) worth to (further) invest in. 
HOLD technologies should not be used for new projects, but 
usually can be continued for existing projects.

### Quadrants / Technology type

Original ThoughtWorks TechRadar assess techologies in 4 "quadrants":
- Techniques
- Platforms
- Tools
- Languages & Frameworks

Thou this approach is great for a map of industry-wide technologies it 
might be too high-level for a company to apply.

Service360 TechRadar does not define tech types and leaves it
completely up to you.

Thou we recommend to have a look at Zalando's approach:
- Frameworks
- Infrastructure
- Data management
- Languages

## How to

Service360 suggests to use repository for storing tech radar data.
Quadrants are implemented as folders on the root level of the repository.
Tech radar entry is a markdown file inside of any root level folder.
Folders on the second level from the root of the repo are ignored and 
can be used for whatever purposes (for example for archive/images/
supporting materials). 

### Tech radar entry

Each tech radar entry keeps track of a history of one tech in your 
landscape.

Tech radar entry must follow a special file semantics to be recognised
as a tech radar entry.

Tech radar entry may (and we suggest to do so) contain a historical 
track of status of the technology separated by the `---` delimiter.
While you of course can keep only the latest state of the tech in the
tech radar entry and use git history to track the changes, we would 
recommend against it. History of the tech inside of the landscape 
is a very important and relevant piece of information helping to 
see how tech was assessed (and possibly open space for reassessment).   

Example:

```markdown
# Technology name

- Status: ADOPT|TRIAL|ASSESS|HOLD
- Date: 26.07.2020
- Alias: Tech1, Tech2, Tech3

Here goes free text describing application of the technology in your
tech landscape. Possible use-cases, caveats, etc.

---

- Status: ADOPT|TRIAL|ASSESS|HOLD
- Date: 26.07.2020 

Here goes free text describing application of the technology in your
tech landscape. Possible use-cases, caveats, etc.

---

... 

``` 

Technically there are only 2 mandatory fields for tech radar entry: 
technology name and status. Date, alias and description are completely 
optional, thou we would recommend to fill those also. 

Purpose of all fields except of the "Alias" speaks for themselves.
Alias field is used to specify technology alias names in case the same
technology is specified with the different names in different service
passports. For example: AWS SQS, SQS. Or for merging tech 
versions: Golang, Go, Golang1.12, Golang1.11.

While parsing service passport technologies are compared against 
tech radar in case insensitive manner, so there is no need to specify 
different aliases which differ only by the letter case. Service360 
treats `SQS` and `sqs` (or `Golang` and `golang`) as one thing. 