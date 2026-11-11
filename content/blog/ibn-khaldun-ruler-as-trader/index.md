---
title: "The Ruler Who Turns Trader"
summary: Ibn Khaldun's tax curve is famous. The warning he wrote two sections later, about rulers who go into business to fill their treasury, is not. An essay with an interactive model, and a look at Tunisia's 2027 finance bill.
date: 2026-11-11
authors:
  - me
tags:
  - governance
  - tunisia
  - public-finance
image:
  alt_text: "A brass balance on an old desk tips under a bundle of tied receipts against a few coins, beside a green ledger with a red wax seal, with shuttered shop fronts through the doorway"
---

Ibn Khaldun finished the first draft of his *Muqaddimah* in 1377, and one sentence from its chapter on dynasties has traveled further than the rest of the book. At the beginning of a dynasty, he wrote, taxation yields a large revenue from small assessments, and at the end, a small revenue from large ones. Six centuries later, Arthur Laffer credited him with the idea behind the curve that carries Laffer's name.

Two sections later, Ibn Khaldun wrote a warning that is quoted far less. It concerns what a ruler does once that curve has turned against him.

## The other warning

Section 38 of the third chapter carries a blunt title in Franz Rosenthal's translation: "Commercial activity on the part of the ruler is harmful to his subjects and ruinous to the tax revenue." The setting is a dynasty in financial straits, after luxury has outgrown revenue and new customs duties have been tried. At that point, he observes, the ruler himself may engage in commerce and agriculture, "from desire to increase his revenues."

The official reasoning is fiscal, and it sounds sensible. The treasury is short, and the state has both the capital and the authority to trade. In practice, according to Ibn Khaldun, the result is the opposite of the intention. The ruler has far more money than any merchant, so he competes with his subjects on terms they cannot match. He buys cheap and forces prices on those who must deal with him. He also pays no customs on his own goods. Farmers give up farming and merchants close their shops, and the revenue they paid disappears with them. His verdict on the arithmetic is a single sentence: "Were the ruler to compare the revenue from taxes with the small profits (he reaps from trading himself), he would find the latter negligible in comparison with the former."

His remedy is not clever. The finances of a ruler, he writes, can be improved "only through the revenue from taxes," and that revenue can be improved "only through the equitable treatment of people with property." A few sections later, in the chapter titled "Injustice brings about the ruin of civilization," he widens the point: attacks on people's property remove their incentive to acquire it, and the activity the treasury depends on dies away.

Read together, these sections describe a spiral rather than a single mistake. A growing court pushes taxes up. Higher taxes and visible injustice erode what modern economists would call tax morale. The shortfall pushes the ruler into the market. His presence there shrinks the base that paid the tax, which widens the shortfall.

## Putting the spiral into a model

In October I built a small model of Ibn Khaldun's dynastic cycle, in which a ruling group's cohesion (his *ʿaṣabiyya*) fades while the court grows and taxes rise to pay for it. The version below adds the three mechanisms of the spiral. The ruler can turn to trade when taxes fall well short of spending. Trust moves with what taxpayers see in return, so that fewer people pay what they owe as public works shrink and the ruler takes over the market. And the ruler can borrow, which a modern state can do far more easily than a fourteenth-century one. Each mechanism has its own switch, so its effect can be seen alone.

<style>
.kh-embed { margin: 1.5rem 0 0.75rem; }
.kh-embed iframe { display: block; width: 100%; height: 880px; border: 1px solid rgba(127,127,127,0.35); border-radius: 10px; background: #f5f4ee; }
@media (max-width: 700px) { .kh-embed { display: none; } }
</style>
<div class="kh-embed">
<iframe src="/models/ibn-khaldun-tax-curve/" title="Interactive model: Ibn Khaldun's Tax Curve" loading="lazy"></iframe>
</div>

{{< button url="/models/ibn-khaldun-tax-curve/" new_tab="true" >}}Open the model full screen{{< /button >}}

With its starting settings, the model gives dynasties of 85 to 89 years. In the first one, taxes fall more than 5% short of spending in year 46, and the ruler starts trading. By the end he holds 60% of the market, trust has fallen from 0.80 to 0.16, and revenue has dropped to less than half its best year. Over that dynasty, the tax his trade displaces is about four times what it earns him. Ibn Khaldun's comparison holds, even when the trade turns a profit.

The switches tell the rest of the story. A ruler who never trades keeps the same dynasty for 113 to 114 years, about a generation longer. If his trade runs at a loss that the treasury covers, the dynasties shorten further. Borrowing behaves differently, and more deceptively. With 80% of each shortfall borrowed, the tax rate stays under 20% until year 41 instead of year 63, but once lenders stop, interest grows to a quarter of all spending, and the rate passes 50% in year 52 instead of year 83. Borrowing buys a longer quiet period and a steeper fall.

One result matters more than the others. With a frugal court, dynasties last 139 years and the ruler never needs to trade at all. In the model, trading and borrowing are responses to a shortfall, and both deepen it. The root is spending that outgrows a base people are willing to pay into.

## Tunis, 2027

Ibn Khaldun wrote in Tunis, and the parallel with the present is hard to ignore, though it should be drawn with care.

Tunisia's parliament is examining the finance bill (projet de loi de finances, PLF) for 2027. Its official line, repeated since September, is that it adds no new tax pressure, and the text bears this out: the main rates are unchanged, and the headline measures are reliefs. New firms that declare investments between 2027 and 2030 would be exempt from income or corporate tax for four years, the state would cover the employer social contributions on their new hires for three years on a sliding scale, and registration duties on a first home would fall from 5% to 1%. One measure goes the other way in a quiet sense, by asking delivery firms to report online sellers' sales to the tax authority. That widens the base without touching a rate. Tax revenue is still forecast to grow 4.7%, to 49.6 billion dinars. The deficit, however, reaches 14.6 billion dinars, and its financing rests heavily on borrowing at home: about 19.9 billion dinars of domestic borrowing is planned, and the Central Bank of Tunisia is to advance the Treasury 9.8 billion dinars interest-free.

The state is also an owner of firms, and that is where Ibn Khaldun's chapter becomes directly relevant. The report on public enterprises annexed to the 2024 finance law covered 88 of them, with a consolidated net loss of 2.98 billion dinars in 2020 and 1.13 billion in 2021. Programmed transfers from the state budget reached 17.08 billion dinars in 2022 and 14.51 billion in 2023. In 2022, 43 enterprises owed the state about 19.7 billion dinars, while the state owed them more than 7 billion. Where losses are routinely covered by transfers and debts run in both directions, economists since János Kornai speak of a soft budget constraint: an enterprise that expects its owner to cover its losses has little reason to avoid them.

The parallel has limits, and they are worth stating. Most Tunisian state-owned enterprises (SOEs) are not a ruler trading for profit. Many run electricity, water, transport or the supply of basic goods, where a public owner can have good reasons to be present and where losses often reflect prices the state itself keeps low. Ibn Khaldun's ruler goes into commerce to raise money, in markets where his subjects were already active. The model speaks to that narrower case, and to the question behind it: what happens to a state that relies on its own commercial activity, or on borrowing, in place of a broad tax base that people trust.

## What the warning asks of an owner

International practice has arrived at principles that read almost as a gloss on section 38. The Organisation for Economic Co-operation and Development (OECD) revised its Guidelines on Corporate Governance of State-Owned Enterprises in 2024. The state is expected to set out why it owns each enterprise and to review that reason regularly. Its role as owner should stay separate from its roles as regulator and policymaker, because a state that both owns a firm and writes the rules of its market is the ruler setting the prices his competitors must accept. Public and private firms should compete on equal terms, without hidden advantages in tax, credit or regulation, and any public-service obligation should be costed and paid for openly instead of accumulating as losses that the budget covers years later.

None of this requires a view on how large the public sector should be. It requires that each holding answer a question Ibn Khaldun would have recognized: does this activity add to what the economy produces and pays, or does it displace activity that would have paid the treasury more? Where the answer is the second, the profit, if there is one, is the small number in his comparison.

The tax base, in the end, is a relationship. Ibn Khaldun understood it as one six centuries before tax morale became a research field. A ruler can widen it by treating people with property fairly, or shrink it by competing with them. The second path brings money in faster, and that is precisely its danger.

## Notes on the model

The model is stylized. Its numbers show how Ibn Khaldun's mechanisms behave together, not the history of any real dynasty or the finances of any modern state. It is not calibrated to Tunisia, its revenue peak of 31% follows from assumed growth rates, and nothing in it says whether any Tunisian tax or enterprise is above or below any peak. Every assumed value, from the size of the court to how quickly trust moves, is listed with its basis on the model's page under "Why these numbers?", and the model has no randomness, so the same settings always give the same result. This is the model's third version. The first two followed the tax curve alone.

## References

- Ibn Khaldun, *The Muqaddimah: An Introduction to History*, translated by Franz Rosenthal (Princeton: Princeton University Press, 1958; abridged edition 1967), chapter 3, sections 36, 38 and 41. Quotations from section 38 follow the Rosenthal translation as excerpted in the [Aspen Institute's selections](https://aspeninstitute.org/wp-content/uploads/files/content/docs/KHALDUN_MUQADDIMAH_SELECTIONS_(AS08).PDF).
- Arthur B. Laffer, "[The Laffer Curve: Past, Present, and Future](https://www.heritage.org/node/17781)," Heritage Foundation, 2004.
- János Kornai, "The Soft Budget Constraint," *Kyklos* 39, no. 1 (1986): 3–30.
- Erzo F. P. Luttmer and Monica Singhal, "[Tax Morale](https://doi.org/10.1257/jep.28.4.149)," *Journal of Economic Perspectives* 28, no. 4 (2014): 149–168.
- OECD, *[OECD Guidelines on Corporate Governance of State-Owned Enterprises 2024](https://www.oecd.org/en/publications/oecd-guidelines-on-corporate-governance-of-state-owned-enterprises-2024_18a24f43-en/full-report/component-14.html)* (Paris: OECD Publishing, 2024).
- "[PLF 2027 : pas de hausse d'impôts et cap sur l'État social](https://www.leconomistemaghrebin.com/2026/09/29/plf-2027-pas-de-hausse-dimpots-et-cap-sur-letat-social/)," *L'Economiste Maghrébin*, September 29, 2026.
- Business News, interview with tax adviser Mohamed Salah Ayari on the provisions of the 2027 finance bill, [November 4, 2026](https://businessnews.com.tn/?p=1427049).
- "[Tunisie : plus de 91 % des recettes budgétaires proviendront des impôts en 2027](https://www.leconomistemaghrebin.com/2026/10/26/tunisie-plus-91-des-recettes-budgetaires-proviendront-impots-2027/)," *L'Economiste Maghrébin*, October 26, 2026.
- "[Tunisia is funding a 32% bigger deficit next year by leaning harder on domestic borrowing](https://enterpriseam.com/menaplus/2026/11/02/tunisia-is-funding-a-32-bigger-deficit-next-year-by-leaning-harder-on-domestic-borrowing-crowding-out-smes/)," *Enterprise*, November 2, 2026.
- Imen Nouira, "[Samir Abdelhafidh veut renforcer les ressources propres de l'État, mais les marges restent étroites](https://businessnews.com.tn/?p=1398032)," *Business News*, April 22, 2026, citing the reports on public enterprises and on state transfers and guarantees annexed to the 2024 finance law.
