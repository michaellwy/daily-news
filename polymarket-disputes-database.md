# Polymarket Resolution Disputes: A Sourced Database (2024 to mid-2026)

Compiled as evidentiary backbone for an article on how prediction markets should write their rules. Last updated 2026-06-20.

## Read this first: method, scope, and integrity caveats

This database includes only disputes that could be corroborated across real, named sources. Nothing here is reconstructed from memory. Where a field could not be verified, it is marked UNVERIFIED with a pointer to where it can be confirmed.

Two limitations you must know before citing any of this in print:

1. Page-fetch was blocked. The research tooling could load search-engine result summaries (which quote and extract text from the listed outlets), but direct full-page fetch returned HTTP 403 across essentially every domain this session (Polymarket, UMA, WSJ, The Block, CoinDesk, The Defiant, Decrypt, Wikipedia, LessWrong, GitBook). Consequence: every verbatim resolution-criteria quote and every exact UMA vote tally below comes from outlet text reproduced in search summaries, cross-checked across multiple independent outlets, not from a live page loaded character by character. Before publication, re-pull the exact rules text from each Polymarket event page and the exact vote splits from the UMA oracle Data Verification Mechanism (DVM) record.

2. Highest-value primary sources not fully read. Two sources almost certainly contain a larger, more precise case inventory and should be opened directly: the LessWrong post "Ambiguity in Prediction Market Resolution is Still Harmful," and an arXiv paper, "Can LLMs Help Decentralized Dispute Arbitration? A Case Study of UMA-Resolved Markets on Polymarket" (arxiv.org/abs/2604.15674). Both were inaccessible to direct fetch this session.

Coverage: fourteen individually sourced disputes plus a verified structural/governance layer. This is a strong evidentiary spine, not a claimed-complete census. A fuller census requires enumerating the UMA DVM voting log and Polymarket's disputed-markets list, neither of which could be loaded directly here. A batching plan to extend the dataset is at the end.

## How resolution and disputes work (context for the table)

Polymarket outsources resolution to UMA's Optimistic Oracle. A whitelisted proposer posts an outcome with a bond (reported at about 750 USDC.e). There is a short challenge window (about 2 hours). A disputer must match the bond. A disputed assertion escalates to UMA's Data Verification Mechanism, where UMA token stakers vote through a commit-and-reveal cycle, typically resolving in roughly 48 to 96 hours. If no proposal reaches the consensus threshold, the vote can "roll" and voters get another window to discuss and revote. Voters in the majority earn rewards; dissenters lose a small fraction of staked UMA. This token-weighted vote is the mechanism at the center of most disputes below.

Sources for mechanics: UMA docs (docs.uma.xyz/faqs); Polymarket help center (help.polymarket.com/en/articles/13364551-how-are-markets-disputed); startpolymarket.com/learn/how-markets-resolve.

## Ordering choice

The table is ordered chronologically rather than by category. Reason: the most important pattern for a rules-design article is the escalation over time, from isolated wording fights in 2024 to systemic oracle-capture and retroactive-rule disputes in 2025 to 2026, alongside the governance reforms (UMIP-189, Chainlink) that the disputes forced. Category grouping is preserved in the root-cause analysis layer below.

## Summary table

| # | Date | Market (short) | Category | Final resolution | Who decided | Seen as correct? | Root-cause tag |
|---|------|----------------|----------|------------------|-------------|------------------|----------------|
| 1 | Jun 2024 | Barron Trump involved in creating $DJT token? | Current events / crypto | UMA voted No; Polymarket called it wrong, refunded Yes | UMA voted, Polymarket overrode | Contested | Platform-vs-oracle conflict over evidence standard |
| 2 | Jul to Aug 2024 | Venezuela 2024 presidential election (Maduro vs Gonzalez) | Election | Gonzalez (Maduro sub-market to zero) | UMA token vote | Contested on process | Conflicting resolution sources (official vs credible reporting) |
| 3 | Nov 2024 | Israel x Hezbollah ceasefire in 2024? | Geopolitics | Yes (ceasefire applied) | UMA token vote (about 87%) | Heavily contested | Entity-scope ambiguity (Hezbollah vs Lebanese government) |
| 4 | Jan 2025 | TikTok banned in the US before May 2025? | Current events | Yes | Polymarket/UMA process | Contested | Literal wording vs real-world enforcement |
| 5 | Mar 2025 | Gold missing from Fort Knox? | Geopolitics / US govt | No | UMA token vote (whale-capture alleged) | Strongly contested | Oracle manipulation / whale voting |
| 6 | Mar 2025 | Ukraine agrees to Trump mineral deal before April? | Geopolitics | Yes (premature) | UMA token vote (whale) | Widely seen as wrong | Oracle governance attack (whale voting) |
| 7 | Jun to Jul 2025 | Will Zelenskyy wear a suit before July? | Current events | No | UMA token vote | Heavily contested | Subjective/ambiguous criteria + token voting |
| 8 | Jul 2025 | Thailand strikes Cambodia by [date]? | Geopolitics / war | Yes (95.89% after rolled vote) | UMA token vote (rolled) | Outcome correct, process contested | Timing criterion ("Too Early") + whale distortion |
| 9 | Dec 2025 | Trump declassifies UFO files in 2025? | Current events / politics | Yes (no documents clearly released) | UMA token vote (whales) | Strongly contested | Undefined key term ("declassify") + whale capture |
| 10 | Feb 2026 | Cardi B performs at Super Bowl LX halftime? | Sports / prop | Yes (Polymarket); Kalshi settled differently | Polymarket discretion | Contested | Undefined key term ("perform") |
| 11 | Mar 2026 | Who will Trump talk to in March? (Trump-Xi call) | Current events | No (on Trump-Xi) | UMA voters pushed Yes; Polymarket overrode | Outcome correct, process contested | Oracle capture vs unverified principal claim |
| 12 | May to Jun 2026 | Strategy (MicroStrategy) sold any Bitcoin by May 31? | Crypto / corporate action | No for May, Yes for June | UMA token vote (98.6%) | Heavily contested | Occurrence-date vs disclosure-date + alleged retroactive rules |
| 13 | Jun 2026 | US x Iran permanent peace deal by deadline? | Geopolitics / war | Yes | Polymarket/UMA process | Contested on merits | Ambiguous threshold ("permanent" vs interim ceasefire) |
| 14 | 2024 to 2025 (year UNVERIFIED) | Astros vs Dodgers MLB game winner | Sports (baseball) | Wrong outcome (Dodgers) finalized; Astros traders refunded | UMA proposal finalized unchallenged; Polymarket refunded off-protocol | Universally seen as a wrong resolution, corrected | Optimistic-oracle challenge-window gap |

## Detailed entries

### 1. Barron Trump involvement in $DJT Solana token

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

### 2. Venezuela 2024 presidential election (Maduro vs Gonzalez)

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

### 3. Israel x Hezbollah ceasefire in 2024?

- Market title and URL: "Israel x Hezbollah Ceasefire in 2024?" polymarket.com/event/israel-x-hezbollah-ceasefire-in-2024.
- Category: Geopolitics / ceasefire.
- Resolution / dispute date: Late November 2024. The Israel-Lebanon ceasefire was signed November 26, 2024, effective November 27, 2024. The case resurfaced prominently in 2025 to 2026 coverage (WSJ investigation, cryptonews, The Currency).
- Resolution criteria as written (reported, NOT confirmed verbatim): Resolves Yes if Israel and Hezbollah both officially announce an armistice, ceasefire, or negotiated settlement effective by December 31, 2024, 11:59 PM ET; must pertain to all theaters of conflict; declared through official channels by both parties; humanitarian pauses excluded; one party alone insufficient.
- What it intended to ask: Whether Israel and Hezbollah would officially reach a ceasefire by the end of 2024.
- Source of dispute: The actual deal was between Israel and the Lebanese government, not nominally "Hezbollah." A trader, Garrick Wilhelm (British Columbia), bet 567 dollars on No, arguing that under the rules a Lebanon deal was not a Hezbollah deal. Other traders argued it counted.
- How contested: Escalated to the UMA oracle. About 87 percent of UMA token voters ruled that the Israel-Lebanon ceasefire applied (resolving against Wilhelm's No). The ruling could not be overturned.
- Final resolution and who decided: Resolved effectively Yes (the ceasefire applied), decided by UMA token holders (about 87 percent).
- Seen as correct or contested: Heavily contested; became an emblem case in UMA structural-risk and CFTC-scrutiny coverage (it is one of the human-interest anchors of the WSJ May 2026 investigation).
- Root-cause tag: Entity-scope ambiguity (Hezbollah versus the Lebanese government) in the resolution language.
- Sources: cryptonews.com/news/polymarket-oracle-risk-cftc-regulatory-scrutiny; finance.yahoo.com/markets/crypto/articles/polymarket-crisis-oracle-risk-regulatory-073158778.html; kucoin.com/news/flash/polymarket-disputes-ruled-by-mysterious-uma-token-holders; thecurrency.news/articles/227498/the-mysterious-crypto-judges-who-settle-polymarket-disputes; en.wikipedia.org/wiki/2024_Israel-Lebanon_ceasefire_agreement.

### 4. TikTok banned in the US before May 2025

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

### 5. Gold missing from Fort Knox?

- Market title and URL: "Gold missing from Fort Knox?" polymarket.com/event/gold-missing-from-fort-knox. A market created in the ZeroHedge orbit asking whether the US Government would confirm Fort Knox holds less gold than recorded. NOTE: distinct from a separate "Will DOGE audit Fort Knox before May?" market; the documented dispute is this "missing gold" market.
- Category: Geopolitics / US government.
- Resolution / dispute date: Early to mid March 2025 (analyst flag around March 11, 2025).
- Resolution criteria as written: NOT confirmed verbatim. Search summaries paraphrase it as resolving on whether the US Government would confirm Fort Knox holds less gold than previously recorded. Verify on the live page.
- What it intended to ask: Whether an official confirmation would emerge that Fort Knox's gold holdings were short of the recorded amount.
- Source of dispute: The market resolved No. A Norway-based equity analyst, Folke Hermansen, publicly flagged it (X thread) as manipulated by UMA whales, alleging two addresses controlled over half the votes and one whale cast about 25 percent of the votes in that market. About 3.5 million dollars in value was implicated.
- How contested: The UMA oracle vote was alleged to be captured by whales. Polymarket apologized on its Discord, reportedly calling it an "unprecedented situation." No clean record was found of formal multi-round DVM re-proposals overturning the result; the No outcome stood.
- Final resolution and who decided: No, decided via UMA token-holder vote; not reversed.
- Seen as correct or contested: Strongly contested (manipulation allegations). Grouped by industry guides with the Ukraine minerals deal and UFO markets as part of more than 30 million dollars in 2025 controversial resolutions (that aggregate is a secondary-guide claim).
- Root-cause tag: UMA voting-power concentration (whale capture).
- Sources: decrypt.co/311634/polymarket-allegations-oracle-manipulation; polymarket.com/event/gold-missing-from-fort-knox; en.cryptonomist.ch/2025/02/18/polymarket-bets-on-the-audit-of-fort-knox-while-the-debate-on-gold-reserves-grows.

### 6. Ukraine agrees to Trump mineral deal before April?

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

### 7. Will Zelenskyy wear a suit before July?

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

### 8. Thailand strikes Cambodia by [date]?

- Market title and URL: "Thailand strikes Cambodia by [date]?" a dated series (for example polymarket.com/event/thailand-strikes-cambodia-by-july-31). Documented as a case study on the PolymarketGuide Archive (GitBook).
- Category: Geopolitics / military conflict.
- Resolution / dispute date: Late July 2025; rolled-vote resolution reported around July 30, 2025. Real-world basis: Thailand launched airstrikes on Cambodian military targets around July 24, 2025 amid the border crisis.
- Resolution criteria as written: NOT confirmed verbatim (not surfaced in search). The dispute hinged on whether confirmed strikes met the bar versus "Too Early."
- What it intended to ask: Whether Thailand conducted a military strike on Cambodia by the deadline.
- Source of dispute: A timing/standard ambiguity between Yes and "Too Early," combined with whale voting power temporarily inflating the "Too Early" option.
- How contested (the strongest-documented dispute mechanics in this dataset):
  - Dispute vote 1: P2 (Yes) 57.8%, P4 (Too Early) 30.8%, others about 12.4%.
  - Dispute vote 2: P2 (Yes) 65.2%, P4 (Too Early) 34.8%.
  - "Too Early" share was attributed to a few top UMA whales (P4 was backed by under about 6 percent of voters by count). No consensus threshold was met, so the vote rolled and users got 24 hours to discuss and revote.
  - Rolled vote: P2 (Yes) 95.89%, P4 (Too Early) 3.69%, P1 (No) 0.41%.
- Final resolution and who decided: Resolved Yes via UMA token-holder vote after the roll.
- Seen as correct or contested: The Yes outcome is widely seen as correct on the facts, but the process was contested because whale voting power temporarily propped up "Too Early."
- Root-cause tag: Timing-criterion ambiguity ("Too Early" versus Yes) amplified by whale vote distortion.
- Sources: polymarketguide.gitbook.io/polymarketguide-archive/case-studies/did-thailand-strike-cambodia/market-resolution; en.wikipedia.org/wiki/2025_Cambodian-Thai_border_crisis; polymarket.com/event/thailand-strikes-cambodia-by-july-31.

### 9. Trump declassifies UFO files in 2025?

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

### 10. Cardi B performs at the Super Bowl LX halftime show?

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

### 11. Who will Trump talk to in March? (Trump-Xi call)

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

### 12. Strategy (MicroStrategy) sold any Bitcoin by May 31, 2026?

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

### 13. US x Iran permanent peace deal by deadline?

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

### 14. Astros vs Dodgers MLB game winner

- Market title and URL: A single-game MLB winner market on an Astros vs Dodgers game. Exact slug and URL NOT verified. Documented via the PolymarketGuide Archive "Refunds" and "Market Clarifications" precedent pages (which could not be loaded, 403) and secondary write-ups.
- Category: Sports (baseball), single-game winner.
- Resolution / dispute date: The game was an Astros 18-1 win reported as a July 4 game; the YEAR is UNVERIFIED (context points to 2024 or 2025). Flag: date incomplete.
- Resolution criteria as written: NOT verified. Standard Polymarket single-game form (resolves to the official MLB winning team), but verbatim text was not seen.
- What it intended to ask: Which team won the Astros vs Dodgers game (the Astros won 18-1).
- Source of dispute: A proposer posted the wrong outcome (Dodgers) to UMA's Optimistic Oracle despite the Astros winning decisively. No one challenged it within the roughly 2-hour window, so the incorrect proposal was accepted and finalized on-chain.
- How contested: This is the key failure mode and it is different from the others. It did NOT go to a DVM token vote. The error slipped through precisely because the optimistic-oracle challenge window expired with no dispute filed. The "dispute" was after the fact (community outcry and Polymarket intervention), not an on-chain UMA dispute round.
- Final resolution and who decided: Polymarket stepped in off-protocol and refunded the affected (Astros) traders at 1 dollar per share for trades made before the erroneous announcement. UMA's on-chain result itself was not reversed (it cannot be); Polymarket covered users separately.
- Seen as correct or contested: Universally described as an incorrect resolution that Polymarket corrected via refund. Cited as a leading argument for reforming or replacing the optimistic-oracle model.
- Root-cause tag: Optimistic-oracle challenge-window gap (a wrong proposal finalized because the short challenge window lapsed unchallenged).
- Sources: predictionnews.com/news/six-burning-questions-as-polymarket-eyes-us-comeback; polymarketguide.gitbook.io/polymarketguide-archive/precedents/polymarket/refunds; polymarketguide.gitbook.io/polymarketguide-archive/precedents/polymarket/market-clarifications; fraudwalrus.substack.com/p/poly.
- Integrity note: This case is corroborated across secondary write-ups but the exact market URL, the year, and the verbatim criteria remain UNVERIFIED. Confirm via the PolymarketGuide precedent pages and the on-chain UMA assertion.

## Structural / governance layer (the system, not a single market)

This layer is the backbone for arguing that the problem is the rulebook and the resolver design, not just individual market wording.

### A. The Wall Street Journal investigation (May 2026)

- Article: "The Mysterious Crypto Judges Who Settle Polymarket Disputes," WSJ, around May 17, 2026 (re-posted by Securities Docket May 18, 2026). Note: this is May 2026, not 2025; the original brief's "May 2025" date appears to be off by a year.
- Verified findings (corroborated across aggregators reproducing the WSJ text):
  - In most disputed markets, more than 50 percent of voting power is concentrated in the ten largest wallets.
  - At least 60 percent of active UMA voters over the prior year could be linked to live Polymarket accounts.
  - In nearly one in five disputes, at least one voter had a financial stake in the outcome (other coverage cites "more than 300 disputes" with voters holding direct financial interests).
  - Polymarket told the WSJ that only 0.2 percent of contracts trigger UMA votes.
  - An anonymous voter ("Scout") reportedly said: "You can either have traders with a conflict of interest, or morons with no conflict of interest." (Confirm verbatim against WSJ.)
  - The Israel-Hezbollah / Garrick Wilhelm case (entry 3) is one of the human-interest anchors of this investigation.
  - Contrast: rival Kalshi resolves disputes internally rather than via a token oracle.
- Sources: securitiesdocket.com/2026/05/18/the-mysterious-crypto-judges-who-settle-polymarket-disputes-wsj; thecurrency.news/articles/227498/the-mysterious-crypto-judges-who-settle-polymarket-disputes; gate.com/news/detail/the-wall-street-journal-investigates-polymarket-arbitration-system-21183884.

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

- A Discord group of losing traders ("Whale Hunters") formed to denounce suspected backroom dealing by top UMA voters, directing attention at UMA.rocks, a tool that lets holders consolidate and delegate voting power. Confidence MEDIUM (aggregators reproducing WSJ/Decrypt). Verify via the WSJ original and decrypt.co/311634.
- Sources: kucoin.com/news/flash/polymarket-dispute-resolution-system-under-scrutiny-as-uma-voting-raises-fraud-concerns; decrypt.co/311634/polymarket-allegations-oracle-manipulation.

### F. Academic and analytical sources on the dispute population

- arXiv paper "Can LLMs Help Decentralized Dispute Arbitration? A Case Study of UMA-Resolved Markets on Polymarket" (arxiv.org/abs/2604.15674, submitted April 17, 2026). Full text could not be loaded (403); figures below are from the abstract via search.
  - Category distribution of disputed events: Sports about 31.5 percent, Politics about 20.4 percent, Crypto about 16.7 percent (the three largest categories).
  - Disputed-event trading volume on Polymarket cited at about 972 million dollars.
  - Web-enabled LLMs reproduce UMA's final resolution about 89.58 percent of the time once a dispute is raised; top models (DeepSeek V3.1, Qwen Max, Claude 4.5 Sonnet) reach about 88 to 90 percent, with the latter two above 95 percent stability.
  - The paper attributes dispute formation mainly to external real-world factors (evolving facts, unstable or incomplete evidence, conflicting reports, media dynamics, delays) and finds that text cues alone cannot reliably predict in advance which events will be disputed.
  - IMPORTANT sampling implication for this database: the academic distribution says SPORTS is the single largest dispute category, but press coverage (and therefore this hand-built list) heavily over-samples politics, geopolitics, and novelty markets and under-samples sports. Only two sports cases (Cardi B, entry 10, and Astros-Dodgers, entry 14) are captured here, and Astros-Dodgers surfaced only through secondary write-ups. The true population of disputes is larger and more sports-weighted than the press-driven sample below suggests.
- LessWrong, "Ambiguity in Prediction Market Resolution is Still Harmful" (lesswrong.com/posts/d4YjM6RWEoT3rBEHe; follow-up to lesswrong.com/posts/DpDnXHcPejd9tn8R5). Core argument: ambiguity adds risk to arbitrage, because two markets on the same event can resolve their ambiguity inconsistently, which discourages the trading that makes markets accurate. Names the Venezuela, Zelenskyy suit, TikTok, and Barron Trump cases (all already in this database); no new named markets surfaced. Full text not loadable (403).

## Analysis layer: root causes by frequency and consequence

Each case is tagged with a primary cause and, where relevant, contributing causes. Several disputes are multi-cause; the most consequential ones combine ambiguous wording with token-weighted voting.

| Root cause | Cases where it is the PRIMARY driver | Cases where it CONTRIBUTES | Primary count |
|------------|--------------------------------------|----------------------------|---------------|
| Ambiguous wording / undefined key terms | Israel-Hezbollah (3), TikTok (4), Zelenskyy (7), UFO (9), Cardi B (10), US-Iran (13) | Strategy (12), Thailand (8) | 6 |
| Oracle manipulation / whale voting | Fort Knox (5), Ukraine mineral (6), Trump-Xi (11) | Israel-Hezbollah (3), Zelenskyy (7), Thailand (8), UFO (9), Strategy (12) | 3 |
| Conflicting or unnamed data sources | Venezuela (2) | US-Iran (13) | 1 |
| Timing / cutoff ambiguity (and retroactive rules) | Thailand (8), Strategy (12) | Ukraine mineral (6) | 2 |
| Platform-vs-oracle conflict / title-vs-rules mismatch | Barron Trump (1) | Trump-Xi (11), UFO (9) | 1 |
| Optimistic-oracle challenge-window gap (wrong proposal finalized unchallenged) | Astros-Dodgers (14) | (the same gap enables whale captures generally) | 1 |
| Unforeseen real-world edge case (trigger, not root) | (none alone) | TikTok (4), Cardi B (10), US-Iran (13), Strategy (12) | 0 |

Most frequent primary cause: ambiguous wording and undefined key terms (6 of 14). Markets turned primarily on a word the rules never pinned down: "suit," "declassify," "perform," "permanent," "banned," and "Hezbollah" (as an entity). These are not exotic edge cases; they are ordinary words the writers assumed were self-evident.

Most consequential and most pervasive cause: oracle manipulation and whale voting. It is the PRIMARY driver in 3 cases but a CONTRIBUTING factor in at least 5 more, so token-weighted voting touches 8 of 13 disputes (about 60 percent). It is also the most consequential by dollars and by reputational damage: the Ukraine mineral deal (premature Yes), Fort Knox (No with manipulation alleged), UFO (Yes with no documents), and Strategy (98.6 percent of voting power) are the cases that turned "the rules were fuzzy" into "the resolver itself is capturable." The WSJ and Bloomberg investigations confirm this is structural: roughly half of voting power sits in about nine to ten wallets, and roughly one in five disputes has a conflicted voter.

The two interact, and that interaction is the core finding. Ambiguous wording is what creates a disputable market in the first place; whale voting is what decides the dispute once it exists. A market with airtight wording rarely reaches the oracle (Polymarket says only 0.2 percent of contracts trigger a vote). So the rules-design lesson is twofold: tighten the wording to keep markets out of the oracle, and fix the oracle for the residual that still gets there.

A third, separate failure mode deserves its own line: the optimistic-oracle challenge-window gap (Astros-Dodgers, entry 14). Here nothing was ambiguous and no whale was needed. A wrong answer was simply posted and nobody disputed it inside the roughly 2-hour window, so it finalized on-chain and Polymarket had to refund users off-protocol. This is the design's quiet baseline risk: the system assumes someone is always watching, and the academic data (sports as about 31.5 percent of disputes, mostly resolved quietly at the oracle layer) suggests these low-salience markets are exactly where unchallenged errors are most likely. The same lapsed-window mechanic is also what lets a whale's proposal stand in the higher-profile cases, so fixing the watcher problem (more proposers, longer or staked challenge windows, automated cross-checks) addresses both.

## Written summary of the patterns

1. The recurring failure is definitional, not factual. In almost every case the underlying facts were not in serious dispute (Zelenskyy wore a blazer; Cardi B danced without singing; Strategy sold 32 BTC and disclosed a day late; the ceasefire was with Lebanon's government). What was disputed was whether those agreed facts satisfied an underspecified word. Rules that define the key term, name the exact evidentiary threshold, and pre-commit the resolution source would have prevented most of these.

2. "Consensus of credible reporting" is the single most dangerous phrase in the dataset. It appears in the Zelenskyy, UFO, Trump-Xi, and (as a fallback) Venezuela markets, and it converts a factual question into a subjective vote about whether enough outlets agreed. It is the clause most often left to whale discretion.

3. Source hierarchies and entity definitions that can point two ways are a structural trap. Venezuela (official versus credible reporting) and Israel-Hezbollah (Hezbollah versus the Lebanese government) both guaranteed a conflict the moment reality split the difference. A rule must say which source wins when they disagree, and must define exactly which entities or events count.

4. Timing and disclosure are under-specified almost everywhere. Strategy shows that "by date X" is ambiguous between when an event occurs and when it becomes public; Thailand shows "Too Early" is a timing judgment that whales can game. Markets need to fix the clock explicitly: occurrence time or disclosure time, in which time zone, with what evidentiary cutoff.

5. The resolver design is now the story. Through 2024 the disputes read as wording fights; by 2025 to 2026 the dominant narrative is oracle capture, because token-weighted voting lets concentrated holders decide outcomes, sometimes with a direct financial stake. Polymarket has had to publicly override its own oracle (Barron Trump, Trump-Xi), which undercuts the "decentralized resolution" claim. The reforms (UMIP-189 whitelist, Chainlink for price markets) are an admission that the original design did not hold.

6. Cross-platform divergence (Cardi B: Polymarket Yes, Kalshi refund) is strong evidence for the article's thesis: identical facts produce opposite payouts purely because of how each venue wrote and adjudicated its rule. That is the clearest possible demonstration that rule-writing, not reality, is doing the work.

7. The "morally right, procedurally wrong" pattern recurs. Venezuela (Gonzalez), Thailand (Yes), and Trump-Xi (No) all reached the outcome most observers consider correct, but by overriding stated rules or by surviving whale distortion. For a rules-design article this is the sharpest tension: a resolver that reaches the right answer the wrong way is still a broken resolver, because the next case may reach the wrong answer by the same mechanism.

## Where the record is incomplete or uncertain (flagged explicitly)

- Verbatim criteria and exact vote tallies. No live Polymarket event page or UMA DVM record could be loaded this session (HTTP 403 environment-wide). All quoted criteria are reproduced from outlet text in search summaries. Re-pull from the source pages before printing any quotation as exact. The one case with well-documented round-by-round vote shares (Thailand, entry 8) still has its criteria text UNVERIFIED.
- Date and attribution corrections already applied: WSJ investigation is May 2026 (not 2025); the "nine whales" finding is Bloomberg (May 2026); the "unprecedented" quote came from Polymarket, not UMA; the Zelenskyy window appears to be May 22 to June 30 (not March 22).
- Single-sourced figures to re-confirm: the Ukraine whale's 5M tokens / 3 accounts / 25 percent (one researcher's analysis); BornTooLate.eth at about 1.3M UMA; the Fort Knox "two addresses over half the votes / one whale 25 percent" figures (one analyst's X thread); the Strategy market dollar volume (ranges 60M to 130M across outlets); UMIP-189 eligibility thresholds (two conflicting versions) and the August 6, 2025 pass date.
- Distinct markets not to conflate: the Fort Knox dispute is the "Gold missing from Fort Knox" market, not the separate "Will DOGE audit Fort Knox before May?" market. The $7M Ukraine dispute is the "minerals/mineral deal" market, not any Russia-Ukraine ceasefire-deadline market.
- Null results, reported honestly rather than padded: no verifiable contested UMA resolution was found for a pure crypto price-target market (the XRP 15-minute case was deterministic spot-price manipulation, not a dispute). A second, dedicated crypto sweep confirmed this more rigorously: price-target markets resolve deterministically off a named single venue and candle spec (for example Binance BTCUSDT High, 1m, Candles), which removes the interpretive surface a dispute needs, and even the October 10, 2025 flash crash produced no sourceable contested price-target resolution. No verifiable contested resolution was found for an economic-data market (Fed, CPI, jobs, recession markets use well-specified named sources). Russia-Ukraine ceasefire-deadline markets and Gaza/Israel-Hamas October 2025 ceasefire markets resolved or expired cleanly. For sports, the academic data says about 31.5 percent of disputes are sports, but open press documents almost none; only the Astros-Dodgers case (entry 14) cleared the bar, which supports the thesis that most sports disputes resolve quietly at the oracle layer and rarely generate citable coverage. The definitive answer for all these lives in the UMA DVM voting log (oracle.uma.xyz) and a disputed-markets tracker such as betmoar.fun/uma.
- Leads found but not verified as actual disputes (do not cite as disputes without confirmation): an FDV / market-cap "above 4 billion dollars" token market whose dispute hinged on which venue counts as the "most liquid price source" (Upbit volume versus Coinbase liquidity score, plus USD-versus-USDC denomination), which is the single most relevant reference-price-source crypto lead but is SINGLE-SOURCED (Phemex) with the exact market unidentified, so it is not promoted; an NBA player-prop "Did Not Play" (DNP) dispute reportedly settled as a loss (an arbusers.com forum thread, around February 2026, behind a login wall, market and outcome unconfirmed); Trump-Greenland markets; TIME Person of the Year markets; Biden dropout and "what day will the AP call the election" markets (criteria confirmed, no contested resolution found); Epstein disclosure markets (market exists, no dispute confirmed). Each needs a second source or the on-chain UMA assertion before it can be entered.
- Two viral sports stories that are NOT disputes (logged so they are not miscounted): the UFC Fortune vs Tybura announcer error (March 2026, a live-event price whipsaw on a correct resolution) and the Spain vs Cape Verde 0-0 World Cup result (June 2026, a clean settlement of a losing favorite bet). Neither involved a challenged proposal, a UMA round, or a refund.
- Meta-sources mined at abstract level only: the LessWrong post (lesswrong.com/posts/d4YjM6RWEoT3rBEHe) and the arXiv paper (arxiv.org/abs/2604.15674) were both searched but could not be fully loaded (403). The LessWrong post named no markets beyond those already here. The arXiv abstract gave category percentages and aggregate figures (see structural layer F) but its abstract names no individual market; the full paper body, where any case studies would appear, remains unread. Open both with a non-blocked fetch to extract any additional itemized cases.
- Sampling bias (important): this is a press-driven sample. The arXiv category data (Sports about 31.5 percent of disputes) indicates the real dispute population is larger and far more sports-weighted than the 14 cases here, which are dominated by politics, geopolitics, and novelty markets because those are what the press covers. Treat this database as a high-significance sample, not a representative census, especially for the sports and crypto-price categories.

## Recommended batching to extend the dataset

This pass covers the most significant and best-documented cases (14 disputes plus the structural layer). To complete a fuller census without padding, batch as follows, most valuable first:

1. Primary-source hardening of these 14 (highest priority): open each Polymarket event page and the matching UMA DVM assertion to capture verbatim rules and exact vote splits. Thailand (entry 8) is the model for the level of vote-by-vote detail to capture for the others. The Astros-Dodgers case (entry 14) most needs a confirmed year, market URL, and the on-chain assertion.
2. The two meta-sources (LessWrong, arXiv paper) to harvest any additional itemized disputes.
3. By category, the under-covered buckets: sports (beyond Cardi B) and the geopolitics ceasefire/conflict family (re-check each deadline market against the UMA dispute log, since clean-looking resolutions can still have had a challenged proposal).
4. By quarter, a systematic sweep of the UMA DVM voting history for 2024 Q3 through 2026 Q2 to catch lower-profile disputes that never made the press.
