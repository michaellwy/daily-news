# Polymarket Resolution Disputes: A Sourced Database (2024 to mid-2026)

Compiled as evidentiary backbone for an article on how prediction markets should write their rules. Last updated 2026-06-20.

## Read this first: method, scope, and integrity caveats

This database includes only disputes that could be corroborated across real, named sources. Nothing here is reconstructed from memory. Where a field could not be verified, it is marked UNVERIFIED with a pointer to where it can be confirmed.

Two limitations you must know before citing any of this in print:

1. Page-fetch was blocked. The research tooling could load search-engine result summaries (which quote and extract text from the listed outlets), but direct full-page fetch returned HTTP 403 across essentially every domain this session (Polymarket, UMA, WSJ, The Block, CoinDesk, The Defiant, Decrypt, Wikipedia, LessWrong). Consequence: every verbatim resolution-criteria quote and every exact UMA vote tally below comes from outlet text reproduced in search summaries, cross-checked across multiple independent outlets, not from a live page loaded character by character. Before publication, re-pull the exact rules text from each Polymarket event page and the exact vote splits from the UMA oracle Data Verification Mechanism (DVM) record.

2. Highest-value primary sources not yet read in full. Two sources almost certainly contain a larger, more precise case inventory and should be opened directly: the LessWrong post "Ambiguity in Prediction Market Resolution is Still Harmful," and an arXiv paper, "Can LLMs Help Decentralized Dispute Arbitration? A Case Study of UMA-Resolved Markets on Polymarket" (arxiv.org/abs/2604.15674). Both were inaccessible this session.

Coverage is therefore partial but solid: ten individually sourced disputes plus a verified structural layer. This is a starting spine, not a claimed-complete census. A fuller census requires the UMA DVM voting log and Polymarket's disputed-markets list, neither of which could be enumerated here.

## How resolution and disputes work (context for the table)

Polymarket outsources resolution to UMA's Optimistic Oracle. A whitelisted proposer posts an outcome with a bond (reported at about 750 USDC.e). There is a short challenge window (about 2 hours). A disputer must match the bond. A disputed assertion escalates to UMA's Data Verification Mechanism, where UMA token stakers vote through a commit-and-reveal cycle, typically resolving in roughly 48 to 96 hours. Voters in the majority earn rewards; dissenters lose a small fraction of staked UMA. This token-weighted vote is the mechanism at the center of most disputes below.

Sources for mechanics: UMA docs (docs.uma.xyz/faqs); startpolymarket.com/learn/how-markets-resolve; chainup.com/blog/settling-the-wagers-inside-polymarkets-decentralized-oracle-and-resolution-engine.

## Ordering choice

The table is ordered chronologically rather than by category. Reason: the most important pattern for a rules-design article is the escalation over time, from isolated wording fights in 2024 to systemic oracle-capture and retroactive-rule disputes in 2025 to 2026, alongside the governance reforms (UMIP-189, Chainlink) that the disputes forced. Category grouping is preserved in the root-cause analysis layer below.

## Summary table

| # | Date | Market (short) | Category | Final resolution | Who decided | Seen as correct? | Root-cause tag |
|---|------|----------------|----------|------------------|-------------|------------------|----------------|
| 1 | Jul to Aug 2024 | Venezuela 2024 presidential election (Maduro vs Gonzalez) | Election | Gonzalez (Maduro sub-market to No/zero) | UMA token vote | Contested on process | Conflicting resolution sources (official vs credible reporting) |
| 2 | Jun 2024 | Barron Trump involved in creating $DJT token? | Current events / crypto | UMA voted No; Polymarket called it wrong, refunded Yes | UMA voted, Polymarket overrode in spirit | Contested | Platform-vs-oracle conflict over evidence standard |
| 3 | Jan 2025 | TikTok banned in the US before May 2025? | Current events | Yes | Polymarket/UMA process | Contested | Literal wording vs real-world enforcement |
| 4 | Mar 2025 | Ukraine agrees to Trump mineral deal before April? | Geopolitics | Yes (premature) | UMA token vote (whale) | Widely seen as wrong | Oracle governance attack (whale voting) |
| 5 | Jun to Jul 2025 | Will Zelenskyy wear a suit before July? | Current events | No | UMA token vote | Heavily contested | Subjective/ambiguous criteria + token voting |
| 6 | Dec 2025 | Trump declassifies UFO files in 2025? | Current events / politics | Yes (no documents clearly released) | UMA token vote (whales) | Strongly contested | Undefined key term ("declassify") + whale capture |
| 7 | Mar 2026 | Who will Trump talk to in March? (Trump-Xi call) | Current events | No (on Trump-Xi) | UMA voters pushed Yes; Polymarket overrode | Outcome seen as correct, process not | Oracle capture vs unverified principal claim |
| 8 | Feb 2026 | Cardi B performs at Super Bowl LX halftime? | Sports / prop | Yes (Polymarket); Kalshi settled differently | Polymarket discretion | Contested | Undefined key term ("perform") |
| 9 | May to Jun 2026 | Strategy (MicroStrategy) sold any Bitcoin by May 31? | Crypto / corporate action | No for May, Yes for June | UMA token vote (98.6%) | Heavily contested | Occurrence-date vs disclosure-date + alleged retroactive rules |
| 10 | Jun 2026 | US x Iran permanent peace deal by deadline? | Geopolitics / war | Yes | Polymarket/UMA process | Contested on merits | Ambiguous threshold ("permanent" vs interim ceasefire) |

## Detailed entries

### 1. Venezuela 2024 presidential election (Maduro vs Gonzalez)

- Market title and URL: Event "Venezuela Presidential Election Winner" with candidate sub-markets including "Will Nicolas Maduro win the 2024 Venezuela presidential election?" and "Will Edmundo Gonzalez win the 2024 Venezuela presidential election?" Event: polymarket.com/event/venezuela-election-winner.
- Category: Election.
- Resolution / dispute date: Election July 28, 2024. CNE declared Maduro shortly after (Maduro odds surged to about 95%). UMA flipped to Gonzalez around August 5 to 6, 2024.
- Resolution criteria as written (reported): "The primary resolution source for this market will be official information from Venezuela, however a consensus of credible reporting will also suffice." A reported December 31, 2024 fallback-to-No clause is from a single extraction and is UNVERIFIED.
- What it intended to ask: Who would be the recognized winner of the 2024 Venezuelan presidential election.
- Source of dispute: The two clauses pointed opposite ways. The "primary" source (Venezuela's CNE) declared Maduro at about 51.2 percent. The "credible reporting" fallback pointed to Gonzalez (Edison Research exit poll roughly 65 to 31; opposition published about 24,000 voting receipts showing a large Gonzalez win; many governments recognized Gonzalez).
- How contested: Resolution escalated to UMA token-holder voting. Exact dispute-round count, bonds, and tallies are UNVERIFIED (UMA oracle page not loadable).
- Final resolution and who decided: Resolved for Gonzalez (Maduro sub-market to zero). Per rekt.news, "On August 5, UMA dropped its bombshell. Gonzalez was declared the winner by the UMA community." Decided by UMA token holders, against the market's own stated primary source.
- Seen as correct or contested: Strongly contested on process grounds. Critics (Frank Muci, "Polymarket Settles Bet Against its Own Rules"; LessWrong) argued UMA resolved against the written rules. Defenders noted Maduro's official win was almost certainly fraudulent. So arguably the correct real-world outcome reached by violating the stated rule hierarchy.
- Root-cause tag: Conflict between a market's two named resolution sources, resolved by UMA discretion against the stated primary source.
- Sources: rekt.news/hedging-bets; lesswrong.com/posts/d4YjM6RWEoT3rBEHe/ambiguity-in-prediction-market-resolution-is-still-harmful; frankmuci.substack.com/p/polymarket-settles-bet-against-its; blog.overlap.fi/polymarket-and-the-venezuela-election-another-case-of-dispute-resolution-gone-wrong; polymarket.com/event/venezuela-election-winner.

### 2. Barron Trump involvement in $DJT Solana token

- Market title and URL: Whether Barron Trump was involved in creating the Solana token $DJT. Exact slug not isolated.
- Category: Current events / crypto.
- Dispute date: Late June 2024 (articles June 27 to 28, 2024). An October 2024 date seen elsewhere could not be confirmed; June 2024 is corroborated.
- Resolution criteria as written (reported): "This market will resolve to 'Yes' if a preponderance of evidence suggests that Barron Trump was involved in the creation of the Solana token $DJT. Otherwise this market will resolve to 'No.'"
- What it intended to ask: Whether Barron Trump helped create the $DJT memecoin.
- Source of dispute: UMA voters settled the market No. Polymarket publicly disagreed, saying its own oracle's resolution was wrong and that a preponderance of evidence showed Barron was involved in some way. About 1 million dollars-plus wagered.
- How contested: Rare public split. Polymarket contradicted UMA's settlement and said it would refund Yes holders; allegations of undue influence by large UMA holders.
- Final resolution and who decided: UMA voted No; Polymarket overrode in spirit by declaring the oracle wrong and committing to refund Yes holders.
- Seen as correct or contested: Still cited as contested and as an early precedent for Polymarket-versus-UMA conflict.
- Root-cause tag: Platform-versus-oracle conflict over a soft evidence standard ("preponderance of evidence").
- Sources: theblock.co/post/302171/polymarket-contradicts-umas-resolution-on-barron-trumps-involvement-with-djt-token; dlnews.com/articles/defi/polymarket-slams-vote-on-barron-trump-and-djt-token; finance.yahoo.com/news/polymarket-contradicts-oracle-rarity-prediction-022105806.html.

### 3. TikTok banned in the US before May 2025

- Market title and URL: "TikTok banned in the US before May 2025?" Related: polymarket.com/event/will-supreme-court-delay-the-tiktok-ban.
- Category: Current events ("did X happen by date").
- Dispute date: January 18 to 20, 2025.
- Resolution criteria as written (reported): Resolves Yes if TikTok is banned in the US within the window. Turned on whether the SCOTUS ruling plus a brief service outage constituted a ban. Resolved Yes on January 20 after SCOTUS upheld the divest-or-ban law. Exact verbatim text UNVERIFIED.
- What it intended to ask: Whether TikTok would actually be banned and effectively disappear in the US.
- Source of dispute: TikTok went dark for US users Saturday evening (citing an enacted ban), but the law was not set to take effect until Sunday, and the app returned Sunday citing assurances from incoming President Trump. Critics argued enforcement was paused or never truly took effect, so a temporary outage should not resolve Yes.
- How contested: A change.org petition alleging manipulation was filed (under 100 signatures); users alleged the UMA DVM process was bypassed and the market resolved directly to Yes.
- Final resolution and who decided: Resolved Yes. Contested as an over-literal resolution given enforcement was paused.
- Seen as correct or contested: Still contested by Yes-skeptics.
- Root-cause tag: Literal wording ("banned"/"enacted") versus real-world enforcement reality.
- Sources: cointelegraph.com/news/polymarket-faces-backlash-over-tik-tok-ban-prediction-resolution; dlnews.com/articles/markets/tiktok-disappearance-sparks-polymarket-petition; change.org/p/demand-accountability-for-suspected-manipulation-on-polymarket-tiktok-ban-vote; cryptonews.com/news/polymarket-faces-backlash-over-tiktok-ban-prediction-market-resolution.

### 4. Ukraine agrees to Trump mineral deal before April?

- Market title and URL: "Ukraine agrees to Trump mineral deal before April?" Slug "ukraine-agrees-to-give-trump-rare-earth-metals-before-april." polymarket.com/event/ukraine-agrees-to-give-trump-rare-earth-metals-before-april.
- Category: Geopolitics / current events.
- Resolution / dispute date: Settled Yes March 25, 2025; manipulation March 24 to 25; Polymarket's "unprecedented" statement around March 26 to 27, 2025. The deal itself was reportedly not signed until April 30, 2025.
- Resolution criteria as written: Not obtained verbatim (UNVERIFIED). Intended condition: resolve Yes only if Ukraine and the US reached an official agreement before April. Polymarket itself argued it was "too early to resolve" since the two countries had not reached a mutual agreement.
- What it intended to ask: Whether Ukraine would formally agree to the US minerals deal before April 2025.
- Source of dispute: The Yes probability spiked from about 9 percent to about 100 percent on March 24 to 25 despite no agreement. Cause was an oracle governance manipulation, not a real-world event.
- How contested: A single whale reportedly controlled about 5 million UMA tokens across three accounts, casting roughly 25 percent of the total vote to force a premature Yes. The 5M-tokens / 3-accounts / 25 percent figures trace to one researcher's on-X analysis amplified by outlets, not an independent on-chain audit. One wallet, BornTooLate.eth (about 1.3M UMA), is single-source and UNVERIFIED.
- Final resolution and who decided: Settled Yes via the UMA token vote, against Polymarket's stated view. Polymarket declined refunds: "Unfortunately, because this wasn't a market failure, we are not able to issue refunds." A Polymarket team member called it "an unprecedented situation" (the "unprecedented" framing came from Polymarket, not UMA).
- Seen as correct or contested: Widely viewed as an incorrect, manipulated resolution and a governance failure. This case directly motivated UMIP-189 (see structural layer).
- Volume: about 7 million dollars.
- Root-cause tag: Oracle governance attack via token-weighted whale voting.
- Sources: theblock.co/post/348171/polymarket-says-governance-attack-by-uma-whale-to-hijack-a-bets-resolution-is-unprecedented; coindesk.com/markets/2025/03/27/polymarket-uma-communities-lock-horns-after-usd7m-ukraine-bet-resolves; thedefiant.io/news/defi/polymarket-s-usd7m-ukraine-mineral-deal-debacle-traced-to-oracle-whale; cointelegraph.com/news/polymarket-trump-ukraine-bet-whale-governance-attack.

### 5. Will Zelenskyy wear a suit before July?

- Market title and URL: "Will Zelenskyy wear a suit before July?" polymarket.com/event/will-zelenskyy-wear-a-suit-before-july. Note sibling markets exist ("before June," "before Friday," "next Trump meeting"); do not conflate.
- Category: Current events (novelty market with geopolitical subject).
- Resolution / dispute date: Triggering event June 24, 2025 (NATO summit, The Hague). Polymarket clarification July 1, 2025. Final No finalized the evening of Tuesday around July 8, 2025.
- Resolution criteria as written (reported): "This market will resolve to 'Yes' if Volodymyr Zelenskyy is photographed or videotaped wearing a suit between May 22 and June 30, 2025 ET. Otherwise, this market will resolve to 'No'." Supplementary: imagery must be authentic (not AI or edited); "The resolution source will be a consensus of credible reporting." FLAG: window start reported as May 22, not the March 22 in the original brief; confirm on the live page.
- What it intended to ask: Whether Zelenskyy, who had worn military/casual attire since the war began, would appear in a conventional suit within the window.
- Source of dispute: At the June 24 NATO event Zelenskyy wore a black blazer, collared shirt, and matching trousers, described by many outlets (BBC, Reuters, New York Post) as a suit, but ambiguous (no tie; jacket arguably a blazer). The criterion "consensus of credible reporting" was itself contested.
- How contested: The market was initially proposed/resolved Yes, disputed, and overturned to No across what reporting frames as multiple dispute rounds over about nine days. UMA cited a lack of "consensus of credible reporting." Exact round count, bonds, and tallies UNVERIFIED.
- Final resolution and who decided: Final outcome No, decided through the UMA oracle process. Polymarket's July 1 clarification defended it: "a consensus of credible reporting has not confirmed that Zelenskyy has worn a suit."
- Seen as correct or contested: Heavily contested. A prominent power user reportedly said "this isn't decentralized." Martin Shkreli reportedly called it a "scam" and threatened legal action.
- Volume: about 237 million dollars (some outlets cite about 240M total, about 160M at stake).
- Root-cause tag: Subjective, ambiguous resolution criterion ("is it a suit?") colliding with token-weighted oracle voting.
- Sources: decrypt.co/329210/polymarket-rules-no-237m-bet-zelenskyys; coindesk.com/markets/2025/07/07/polymarket-embroiled-in-usd160m-controversy-over-whether-zelensky-wore-a-suit-at-nato; coindesk.com/markets/2025/07/09/this-isnt-decentralized-says-polymarket-power-user-as-zelenskyys-suit-controversy-unfolds; dlnews.com/articles/markets/polymarket-bettors-clash-over-zelenskyy-suit-dispute.

### 6. Trump declassifies UFO files in 2025?

- Market title and URL: "Trump declassifies UFO files in 2025?" slug "trump-declassifies-ufo-files-in-2025." polymarket.com/event/trump-declassifies-ufo-files-in-2025.
- Category: Current events / politics.
- Resolution / dispute date: Odds about 5.5 percent on December 6, 2025; spiked toward about 90 percent on December 7 after a December 4 Pentagon/AARO video release. Market closed just after midnight UTC on December 10, 2025 following two disputes.
- Resolution criteria as written (reported paraphrase): Pays Yes only if the administration "declassifies previously classified files on extraterrestrial life or unidentified aerial phenomena by 11:59 p.m. ET on Dec. 31, 2025," with primary source "official US government information" and "consensus of credible reporting" as fallback. Exact verbatim text UNVERIFIED.
- Market size: about 16 million dollars (a related AARO-release market at about 33M is distinct; keep separate).
- What it intended to ask: Whether the administration would formally declassify previously classified UFO/UAP files in 2025.
- Source of dispute: The trigger was a December 4 AARO "Official UAP Imagery" video plus items added December 9 via routine DoD publication. Critics: these were a DoD media release, not a White House declassification order, and the National Archives UAP hub contained no December 2025 declassification bulletin.
- How contested: Multiple disputes routed to the UMA oracle (about 2-hour challenge window, then commit-reveal vote, proposer/disputer bonds about 750 dollars). Late-session buying near 99 to 99.9 cents preceded finalization. Exact final vote split UNVERIFIED (check the UMA oracle voting record for the assertion ID).
- Final resolution and who decided: Resolved YES by UMA token holders despite no documents clearly meeting the criteria. Widely characterized as whales forcing a Yes.
- Seen as correct or contested: Strongly contested; labeled a "scam" and "proof-of-whales," cited as a credibility crisis.
- Root-cause tag: Undefined key term ("declassify") satisfied by a routine media release, plus token-weighted whale capture.
- Sources: cryptoslate.com/polymarket-faces-major-credibility-crisis-after-whales-forced-a-yes-ufo-vote-without-evidence; ainvest.com/news/decentralized-oracles-market-manipulation-polymarket-ufo-contract-case-study-2512; cryptoslate.com/how-a-jellyfish-ufo-video-and-pdf-fueled-the-controversial-1700-polymarket-explosion; finance.yahoo.com/markets/crypto/articles/pentagon-drops-first-ever-alien-160618372.html.

### 7. Who will Trump talk to in March? (Trump-Xi call)

- Market title and URL: "Who will Trump talk to in March?" polymarket.com/event/who-will-trump-talk-to-in-march. Contested sub-outcome: whether Trump spoke with Xi Jinping.
- Category: Current events / political statement.
- Dispute date: Late March 2026 (around March 30).
- Resolution criteria as written (reported): Resolution source is "a consensus of credible reporting." Polymarket's clarifying statement: "there is not a consensus of credible reporting that Trump has spoken to Xi in March."
- What it intended to ask: Whether Trump actually held a call with Xi during March, verified by credible reporting.
- Source of dispute: Trump announced he had spoken with Xi over the weekend, but China never confirmed. Odds swung from about 24 to about 79 percent on Trump's claim, fell to about 16 percent, then a large UMA token voter switched No to Yes, dragging price back to about 94 percent.
- How contested: A single large UMA holder pushed toward Yes; Polymarket publicly refuted its own oracle's voters.
- Final resolution and who decided: Resolved No on the Trump-Xi question; Polymarket effectively overrode the UMA whale's direction by clarifying intent (the Xi odds collapsed from about 70 to about 2 percent).
- Seen as correct or contested: The No outcome is seen as substantively correct, but the episode is cited as evidence a single whale can hijack a vote and that Polymarket must override its own oracle.
- Root-cause tag: Oracle capture by a large UMA holder versus an unverified principal claim.
- Sources: predictionnews.com/news/polymarket-overrules-uma-voters-in-trump-xi-call-market; polymarket.com/event/who-will-trump-talk-to-in-march.

### 8. Cardi B performs at the Super Bowl LX halftime show?

- Market title and URL: Polymarket contract on whether Cardi B would perform at the Super Bowl LX halftime show (Bad Bunny's set). Exact slug not isolated; about 10 million dollars volume.
- Category: Sports / current-events prop.
- Dispute date: February 8 to 12, 2026.
- Resolution criteria as written (reported): Polymarket's rule resolves Yes if Cardi B "performs live and in person." Kalshi's parallel rule, per a Kalshi spokeswoman: "singing and dancing counted as a performance, but just dancing in the background did not."
- What it intended to ask: Whether Cardi B would actually perform (not merely cameo) during the halftime show.
- Source of dispute: Cardi B appeared in the set alongside Karol G, Pedro Pascal and Jessica Alba, danced and mouthed words, but never sang or took a microphone. Whether a dancing-only cameo is a "performance" was ambiguous.
- How contested: Heavy trader pushback ("There's no way that you would count a cameo as a performance"). A Kalshi Yes-backer filed a CFTC complaint alleging a Commodity Exchange Act violation, seeking 3,700 dollars in damages.
- Final resolution and who decided: Polymarket resolved Yes (Cardi B performed). Kalshi diverged: it cited ambiguity, paused trading, and settled at the last traded price (0.74 No / 0.26 Yes), refunding users. Same footage, opposite resolutions across platforms.
- Seen as correct or contested: Still contested; a textbook "same event, opposite resolutions" case.
- Root-cause tag: Undefined key term ("perform") plus platform discretion.
- Sources: nbcnews.com/business/business-news/cardi-b-cameo-bad-bunnys-super-bowl-halftime-show-leads-dispute-predi-rcna258553; cbsnews.com/news/cardi-b-super-bowl-prediction-market-dispute; foxsports.com/articles/nfl/cardi-bs-cameo-in-bad-bunnys-super-bowl-halftime-show-leads-to-dispute-on-prediction-markets; readwrite.com/cftc-complaint-filed-kalshi-cardi-b-super-bowl-event-decision.

### 9. Strategy (MicroStrategy) sold any Bitcoin by May 31, 2026?

- Market title and URL: Reported as "MicroStrategy sells any Bitcoin by May 31, 2026?" (paired companion contract for June 30). Exact on-platform title UNVERIFIED; confirm on the Polymarket event page.
- Category: Crypto / corporate action (Bitcoin-adjacent).
- Dispute / resolution dates: Strategy's 8-K filed June 1, 2026. Market disputed twice, escalated to a token-weighted DVM vote; CoinDesk "No for May, Yes for June" coverage dated June 4, 2026.
- Resolution criteria as written (reported paraphrase): "Yes" holders win if the bitcoin activity is "presented as of May 31, 2026, 4:00 p.m. Eastern Time"; original rules pointed to "SEC filings, on-chain data, and credible reporting." Treat fragments as reported quotes, not confirmed against the live page. Exact full text UNVERIFIED.
- What it intended to ask: Whether Strategy sold any BTC during the period ending May 31, 2026.
- Underlying facts: Strategy sold 32 BTC (about 2.5 million dollars) between May 26 and 31, 2026, its first sale since December 2022, disclosed via an 8-K on June 1, 2026.
- Source of dispute: Ambiguity between when the sale occurred (on-chain/8-K table shows before May 31) and when it was publicly disclosed (June 1, after the deadline). Critics (CryptoTimes) allege Polymarket added a "post-deadline announcements do not count" interpretation only after the market closed, i.e., retroactive rule-making.
- How contested: Two proposed No resolutions were challenged, sending it to a UMA token vote. Final UMA review backed No with 98.6 percent of voting power. Reported as the largest UMA dispute since the Zelenskyy suit market. Volume figure is INCONSISTENT across outlets (The Defiant headline about 85M, The Block/CoinDesk above 60M, one outlet 130M); treat the exact dollar figure as UNVERIFIED.
- Final resolution and who decided: May contract No; June contract Yes. Decided by UMA token holders, upheld by Polymarket. May "Yes" price collapsed below 1 cent.
- Seen as correct or contested: Heavily contested. The WSJ May 2026 investigation and others note vote concentration among the ten largest wallets and voters with stakes; critics call it "proof-of-whales" and allege retroactive rules.
- Root-cause tag: Occurrence-date versus public-disclosure-date ambiguity, plus alleged retroactive rule clarification.
- Sources: theblock.co/post/403600/polymarket-upholds-no-outcome-strategy-bitcoin-sale-market; coindesk.com/markets/2026/06/04/polymarket-says-no-for-may-yes-for-june-after-strategy-s-recent-bitcoin-sale; coindesk.com/markets/2026/06/01/strategy-s-bitcoin-sale-sparks-a-usd14-million-crypto-betting-chaos-on-a-major-prediction-market; cryptotimes.io/2026/06/02/polymarket-accused-of-retroactive-rule-changes-in-strategys-bitcoin-sell-market; thedefiant.io/news/markets/usd85m-polymarket-dispute-over-strategy-s-may-bitcoin-sale-puts-uma-s-token-voting-oracle-on.

### 10. US x Iran permanent peace deal by deadline?

- Market title and URL: "US x Iran permanent peace deal by...?" polymarket.com/event/us-x-iran-permanent-peace-deal-by.
- Category: Geopolitics / war.
- Dispute date: Mid-June 2026 (around the June 15 deadline; deal text released June 17).
- Resolution criteria as written (reported): A qualifying agreement must "explicitly indicate that military hostilities between the two countries have ended or will permanently cease," or otherwise clearly signal a "lasting end to hostilities."
- What it intended to ask: Whether the US and Iran reach a genuine permanent peace deal (not a temporary ceasefire) by the deadline.
- Source of dispute: The announced framework included only a 60-day ceasefire, with Iran's nuclear program and sanctions left open. Trump publicly called it "a memorandum of understanding" / interim measure (per Reuters) after the deadline. No holders argued this fell short of "permanent." Related Iran contracts reportedly carried about 120 million to about 354 million dollars in volume (figures vary by outlet/grouping).
- How contested: Entered Polymarket's formal dispute process; UMA token holders debated then voted. Covered as one of Polymarket's largest-ever resolution disputes.
- Final resolution and who decided: Reported as resolving Yes after the US released the full MOU text on June 17, 2026, which markets treated as meeting the criteria (prices surged to 100 percent). Resolution flowed through the Polymarket/UMA process.
- Seen as correct or contested: The Yes outcome was disputed by No holders who maintain a 60-day ceasefire is not "permanent"; seen as contested on the merits.
- Root-cause tag: Ambiguous threshold ("permanent" versus interim ceasefire) compounded by conflicting principal (Trump) statements.
- Sources: theblock.co/post/405117/trump-comments-fuel-dispute-over-polymarkets-120-million-permanent-iran-peace-deal-market; cryptobriefing.com/polymarket-iran-deal-dispute-trump; finance.yahoo.com/markets/crypto/articles/polymarket-traders-clash-over-345-190234396.html; polymarket.com/event/us-x-iran-permanent-peace-deal-by.

## Structural / governance layer (the system, not a single market)

This layer is the backbone for arguing that the problem is the rulebook and the resolver design, not just individual market wording.

### A. The Wall Street Journal investigation (May 2026)

- Article: "The Mysterious Crypto Judges Who Settle Polymarket Disputes," WSJ, around May 17, 2026 (re-posted by Securities Docket May 18, 2026). Note: this is May 2026, not 2025; the original brief's "May 2025" date appears to be off by a year.
- Verified findings (corroborated across aggregators reproducing the WSJ text):
  - In most disputed markets, more than 50 percent of voting power is concentrated in the ten largest wallets.
  - At least 60 percent of active UMA voters over the prior year could be linked to live Polymarket accounts.
  - In nearly one in five disputes, at least one voter had a financial stake in the outcome.
  - Polymarket told the WSJ that only 0.2 percent of contracts trigger UMA votes.
  - An anonymous voter ("Scout") reportedly said: "You can either have traders with a conflict of interest, or morons with no conflict of interest." (Confirm verbatim against WSJ.)
  - Contrast: rival Kalshi resolves disputes internally rather than via a token oracle.
- Sources: securitiesdocket.com/2026/05/18/the-mysterious-crypto-judges-who-settle-polymarket-disputes-wsj; gate.com/news/detail/the-wall-street-journal-investigates-polymarket-arbitration-system-21183884.

### B. Bloomberg "nine whales" investigation (May 2026)

- Article: "Crypto Whales Dominate Polymarket Disputes Worth $5 Billion," Bloomberg, May 26, 2026.
- Verified findings: about nine anonymous wallets control roughly half of total UMA voting power on Polymarket and can determine outcomes when voting as a bloc; disputes cover bets worth about 5 billion dollars; nearly 2,000 contracts were disputed over the prior year; in April 2026 alone, 230 contracts attracting more than 1 billion dollars were decided, up from 79 contracts six months earlier. Polymarket's revamp of the voting process (efforts by Risk Labs and Eigen Labs) has reportedly stalled.
- Sources: bloomberg.com/news/articles/2026-05-26/crypto-whales-dominate-polymarket-disputes-worth-5-billion; cryptobriefing.com/polymarket-whale-voting-dispute-delays; cryptotimes.io/2026/05/27/only-9-wallets-control-nearly-half-of-uma-voting-power-on-polymarket-bloomberg.

### C. UMIP-189 / "MOOV2" governance reform (August 2025)

- Proposal: UMIP-189, "Approve new ManagedOptimisticOracleV2 Deployment." discourse.uma.xyz/t/umip-189-approve-new-managedoptimisticoraclev2-deployment/2229. Reported passed around August 6, 2025.
- What changed: transitions Polymarket from Optimistic Oracle V2 to Managed Optimistic Oracle V2; creates a whitelist (about 37 vetted addresses) as the only parties who can directly submit resolution proposals. Disputing remains open to anyone. Eligibility tied to a proposal track record (sources conflict: "20+ proposals at 95 percent accuracy" versus "minimum 5 proposals, 95 percent over a rolling 6-month window"; confirm on Discourse). Whitelist reportedly grew from 37 to about 177 by November 2025.
- Motivation: improve proposal quality and reduce disputes, especially after the March 2025 Ukraine governance attack.
- Sources: theblock.co/post/366507/polymarket-uma-oracle-update; cryptotimes.io/2025/08/12/uma-limits-polymarket-resolutions-to-whitelisted-parties-only; ainvest.com/news/uma-restricts-resolution-proposers-37-whitelisted-addresses-polymarket-2508.

### D. Chainlink integration (September 2025)

- Polymarket announced a Chainlink partnership September 12, 2025 to automate resolution of asset-price-related markets (Chainlink Data Streams plus Automation, live on Polygon), reducing reliance on manual UMA dispute resolution for price markets. Scoped to price markets, not a wholesale replacement of UMA for subjective/event markets.
- Sources: prnewswire.com/news-releases/polymarket-partners-with-chainlink-to-enhance-accuracy-of-prediction-market-resolutions-302555123.html; coindesk.com/web3/2025/09/12/polymarket-connects-to-chainlink-to-cut-tampering-risks-in-price-bets.

### E. "Whale Hunters" and vote-consolidation tooling

- A Discord group of losing traders ("Whale Hunters") formed to denounce suspected backroom dealing by top UMA voters, directing attention at UMA.rocks, a tool that lets holders consolidate and delegate voting power. A named trader, Garrick Wilhelm (British Columbia), reportedly bet 567 dollars that Israel and Hezbollah would not reach a ceasefire; about 87 percent of UMA voters ruled the Israel-Lebanon ceasefire applied, so he lost. Confidence MEDIUM (aggregators reproducing WSJ/Decrypt). This is a candidate eleventh micro-case (the Israel-Hezbollah ceasefire wager) but the market-level detail is too thin to promote to the main table; verify via the WSJ original and decrypt.co/311634.
- Sources: kucoin.com/news/flash/polymarket-dispute-resolution-system-under-scrutiny-as-uma-voting-raises-fraud-concerns; decrypt.co/311634/polymarket-allegations-oracle-manipulation.

## Analysis layer: root causes by frequency and consequence

Each case is tagged with a primary cause and, where relevant, contributing causes. Several disputes are multi-cause; the most consequential ones combine ambiguous wording with token-weighted voting.

| Root cause | Cases (primary) | Cases (contributing) | Frequency |
|------------|-----------------|----------------------|-----------|
| Ambiguous wording / undefined key terms | Zelenskyy suit (5), UFO (6), Cardi B (8), US-Iran (10), TikTok (3) | Strategy (9) | Most frequent (5 primary) |
| Oracle manipulation / whale voting | Ukraine mineral (4), Trump-Xi (7) | UFO (6), Strategy (9) | High and most consequential by dollars |
| Conflicting or unnamed data sources | Venezuela (1) | US-Iran (10) | Low count, high stakes |
| Timing / cutoff ambiguity + retroactive rules | Strategy (9) | Ukraine mineral (4) | Low count, growing |
| Platform-vs-oracle conflict / title-vs-rules mismatch | Barron Trump (2), Trump-Xi (7) | UFO (6) | Recurring |
| Unforeseen real-world edge case | (contributes across) TikTok (3), Cardi B (8), US-Iran (10) | n/a | Pervasive as a trigger |

Most frequent cause: ambiguous wording and undefined key terms. Five of ten markets turned primarily on a word the rules never pinned down: "suit," "declassify," "perform," "permanent," "banned." These are not exotic edge cases; they are ordinary words that the writers assumed were self-evident.

Most consequential cause: oracle manipulation and whale voting, measured by dollars at stake and by reputational damage. The Ukraine mineral deal (about 7M, premature Yes), the UFO market (about 16M, Yes with no documents), and the Strategy market (tens of millions, 98.6 percent of voting power for No) are the cases that turned "the rules were fuzzy" into "the resolver itself is capturable." The WSJ and Bloomberg investigations show this is structural, not anecdotal: roughly half of voting power sits in about nine to ten wallets, and roughly one in five disputes has a conflicted voter.

The two interact. Ambiguous wording is what creates a disputable market in the first place; whale voting is what decides the dispute once it exists. A market with airtight wording rarely reaches the oracle (Polymarket says only 0.2 percent of contracts trigger a vote). So the rules-design lesson is twofold: tighten the wording to keep markets out of the oracle, and fix the oracle for the residual that still gets there.

## Written summary of the patterns

1. The recurring failure is definitional, not factual. In almost every case the underlying facts were not in serious dispute (Zelenskyy wore a blazer; Cardi B danced without singing; Strategy sold 32 BTC and disclosed a day late). What was in dispute was whether those agreed facts satisfied an underspecified word. Rules that define the key term, name the exact evidentiary threshold, and pre-commit the resolution source would have prevented most of these.

2. "Consensus of credible reporting" is the single most dangerous phrase in the dataset. It appears in the Zelenskyy, UFO, Trump-Xi, and (as a fallback) Venezuela markets, and it converts a factual question into a subjective vote about whether enough outlets agreed. It is the clause most often left to whale discretion.

3. Source hierarchies that can point two ways are a structural trap. Venezuela is the cleanest example: naming both "official information" and "credible reporting" guaranteed a conflict the moment the official count and the observed count diverged. A rule must say which source wins when they disagree.

4. Timing and disclosure are under-specified almost everywhere. The Strategy market shows that "by date X" is ambiguous between when an event occurs and when it becomes public. Markets need to fix the clock explicitly: occurrence time or disclosure time, and in which time zone, with what evidentiary cutoff.

5. The resolver design is now the story. Through 2024 the disputes read as wording fights; by 2025 to 2026 the dominant narrative is oracle capture, because token-weighted voting lets concentrated holders decide outcomes, sometimes with a direct financial stake. Polymarket has had to publicly override its own oracle (Barron Trump, Trump-Xi), which undercuts the "decentralized resolution" claim. The reforms (UMIP-189 whitelist, Chainlink for price markets) are an admission that the original design did not hold.

6. Cross-platform divergence (Cardi B: Polymarket Yes, Kalshi refund) is strong evidence for the article's thesis: identical facts produce opposite payouts purely because of how each venue wrote and adjudicated its rule. That is the clearest possible demonstration that rule-writing, not reality, is doing the work.

## Where the record is incomplete or uncertain (flagged explicitly)

- Verbatim criteria and exact vote tallies. No live Polymarket event page or UMA DVM record could be loaded this session (HTTP 403 environment-wide). All quoted criteria are reproduced from outlet text in search summaries. Re-pull from the source pages before printing any quotation as exact.
- Date and attribution corrections already applied: WSJ investigation is May 2026 (not 2025); the "nine whales" finding is Bloomberg (May 2026); the "unprecedented" quote came from Polymarket, not UMA; the Zelenskyy window appears to be May 22 to June 30 (not March 22).
- Single-sourced figures to re-confirm: the Ukraine whale's 5M tokens / 3 accounts / 25 percent (one researcher's analysis); BornTooLate.eth at about 1.3M UMA; the Strategy market dollar volume (ranges 60M to 130M across outlets); UMIP-189 eligibility thresholds (two conflicting versions) and the August 6, 2025 pass date.
- Null results, reported honestly rather than padded: no verifiable contested UMA resolution was found for a crypto price-target market (the XRP 15-minute case was deterministic spot-price manipulation, not a dispute) or for an economic-data market (Fed, CPI, jobs, recession markets use well-specified named sources and produced no sourceable dispute). If these categories matter to the article, the place to look is the UMA DVM voting log for specific FOMC/CPI/NFP assertion IDs.
- Leads found but not verified as actual disputes (do not cite as disputes without confirmation): "Did Thailand strike Cambodia?" clarification; Russia-Ukraine ceasefire-deadline markets; Gaza/Israel-Hamas ceasefire markets (Oct 2025); Trump-Greenland markets; TIME Person of the Year markets; Biden dropout and "what day will the AP call the election" markets; the Fort Knox gold audit market (named as a 2025 controversial resolution but not detailed here). Each has clear criteria but no confirmed contested resolution event in the sources reached.
- Highest-value unread primary sources: the LessWrong post (lesswrong.com/posts/d4YjM6RWEoT3rBEHe) and the arXiv paper "Can LLMs Help Decentralized Dispute Arbitration? A Case Study of UMA-Resolved Markets on Polymarket" (arxiv.org/abs/2604.15674). Both likely contain a larger itemized case list and should be opened directly to extend this database.

## Recommended batching to extend the dataset

This first pass covers the most significant and best-documented cases. To complete a fuller census without padding, batch as follows, most valuable first:

1. Primary-source hardening of these 10 (highest priority): open each Polymarket event page and the matching UMA DVM assertion to capture verbatim rules and exact vote splits.
2. The two unread meta-sources (LessWrong, arXiv paper) to harvest any additional itemized disputes.
3. By category, the under-covered buckets: sports (beyond Cardi B), and the geopolitics ceasefire/deadline family (Russia-Ukraine, Gaza, Iran sub-markets), using the UMA dispute log around each deadline.
4. By quarter, a systematic sweep of the UMA DVM voting history for 2024 Q3 through 2026 Q2 to catch lower-profile disputes that never made the press.
