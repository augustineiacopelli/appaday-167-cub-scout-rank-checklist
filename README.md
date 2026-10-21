# Cub Scout Rank Checklist

**AppADay 167** | Productivity | [Live app](https://augustineiacopelli.github.io/appaday-167-cub-scout-rank-checklist/) | [Portfolio](https://augustineiacopelli.github.io/appaday/)

Cub Scout Rank Checklist tracks advancement under the Cub Scout program in effect since June 2024. It covers every adventure in all six ranks: Lion, Tiger, Wolf, Bear, Webelos, and Arrow of Light. A parent or den leader checks off requirements as a Scout finishes them. Adventures and ranks complete on their own, and a Scoutbook queue turns the weekly entry into a straight copy.

## What it does

The app handles several Scouts at once. A chip row along the top switches between them. Each Scout is assigned the den they are in this school year, such as Bear for a third grader, since the rank itself is not earned until near the end of the year.

**Summary** shows a card for every Scout. Each card has a den badge, a progress bar, a Complete stamp when the rank is earned, a count of items still waiting for Scoutbook, and a mini bar for each of the six ranks.

**Rank** opens any of the six ranks. The six required adventures are listed under their focus areas: Character and Leadership, Outdoors, Personal Fitness, Citizenship, Personal Safety, and Family and Reverence. The electives follow with progress rings. Star up to two electives to pin the ones the Scout is working on. The rank bar averages eight slots: the six required adventures plus two elective slots. Those slots fill with completed electives first, then pinned ones, then the most advanced. A rank is complete when all six required adventures and any two electives are met. Each rank links to its official scouting.org page.

**Adventure** lists the requirements as large tap targets. A tap checks a requirement and stamps it with today's date. The date chip opens a native date picker for backdating, and future dates are refused. Where Scouting America allows an alternate path, a button at the top records it with a date and completes the adventure without any requirement checked. These adventures have alternates:

* The Family and Reverence adventure in every rank: earning a Religious Emblem.
* Lion Time to Swim and Tigers in the Water: swim lessons.
* Wolf Paws for Water, Bear Salmon Run, Webelos Aquanaut, and Arrow of Light Swimming: the Scouting America swimmer test or swim lessons.

**Queue** lists every checked requirement and alternate not yet entered in Scoutbook. Items are grouped by rank and adventure in catalog order, with requirement numbers matching Scoutbook. You can mark one item or a whole adventure as entered, and an Undo toast can reverse either. Unchecking a requirement that is already marked entered asks for confirmation first.

**Settings**, behind the gear, adds, renames, and removes Scouts, and moves a Scout to a new den each fall. It also exports a backup, imports one, and resets a Scout's progress. Reset only unlocks after you type the Scout's name.

## About the requirement text

Each requirement is a plain-language summary written for this app. It is numbered to match the official requirement and Scoutbook. The official wording belongs to Scouting America and is linked from every rank screen. Check it there whenever the exact phrasing matters.

## Data and privacy

Everything stays in the browser under the localStorage key `appaday167`. The app stores no accounts and makes no network calls. Export writes `appaday167-backup-YYYY-MM-DD.json`. Import checks the file's shape, reports how many Scouts, requirements, and alternates it found, then offers Replace or Merge. Merge matches Scouts by name, keeps the earlier date for any item found in both copies, and keeps an item entered if either copy says so. If the browser blocks storage, the app keeps working in memory and shows a banner recommending an export.

## Technical notes

The app is a single `index.html` of vanilla HTML, CSS, and JavaScript with no libraries. The catalog is a frozen constant. Progress is computed from three pure functions (`requirementsMet`, `adventureProgress`, `rankProgress`) and is never stored. The adventure engine also supports group quotas, such as completing two of a set. No current adventure needs them, but they are tested. The layout is built 375px first with no horizontal scroll, uses 44px tap targets and rank colors as accents, and follows the system dark mode. The head carries the AppADay home screen icon tags (`icons/167.png`, short title Cub Ranks), the web app manifest, and the shared Save to Phone script.

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one complete web app shipped every day.
