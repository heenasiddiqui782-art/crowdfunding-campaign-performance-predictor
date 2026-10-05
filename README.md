# Crowdfunding Campaign Performance Predictor

> An Excel decision-support model that scores a reward-based crowdfunding campaign's launch readiness, simulates funding outcomes, and recommends whether to launch, test further, or rework.

## Quick links

| | |
|---|---|
| 🎬 **Demo video** | 



https://github.com/user-attachments/assets/bfefd581-a102-40ad-bbd3-ab586cee0fce





 |
| 📊 **Dashboard image** | <img width="726" height="386" alt="P2 (S2) in outputs" src="https://github.com/user-attachments/assets/d7af6ae9-82c9-4e3c-bb5d-8b575d707e0a" />
<img width="818" height="394" alt="P2 (S1) in outputs" src="https://github.com/user-attachments/assets/f06841a8-8adb-437a-9aa5-4f1b3253a0b2" />
 |
| 📘 **Excel model** | https://1drv.ms/x/c/d25b756fc27d4ee3/IQAwyVqcK21GTr7WEYjZK6H6AZZ_UvyRA6gEwt4KkGc2R1k?e=cveYEV |



## Demo





https://github.com/user-attachments/assets/dd7a6f01-c119-46a9-ad2d-6ceb72db7de4





▶ [Watch the full 54-second walkthrough (1080p)](assets/demo.mp4)

## Why this project

Most crowdfunding campaigns fail because of audience and traffic shortfalls, not because the product is bad. This model makes those gaps visible *before* launch: how many visitors and backers are needed, what the current audience can realistically deliver, and what happens to the money after product, shipping, fees and marketing costs.

The worked example is **GreenNest**, an illustrative smart kitchen composter startup in India with a ₹10,00,000 goal.

## Key findings (Base inputs)

| Metric | Result |
|---|---|
| Campaign Performance Score | **62.2 / 100** (Significant Risk) |
| Funding goal vs. Base projection | ₹10.0L vs. ₹10.4L (104% of goal) |
| Backers: expected / required / break-even | 400 / 385 / 315 |
| Pre-launch readiness | **44 / 100** (audience = 14% of required visitors) |
| Final recommendation | **TEST FURTHER** |

**Scenarios**

| | Conservative | Base | Optimistic |
|---|---|---|---|
| Amount raised | ₹4.8L (48%) | ₹10.4L (104%) | ₹21.2L (212%) |
| Goal reached? | No | Yes | Yes |
| Net campaign contribution | −₹1.1L | +₹0.7L | +₹4.2L |

**Top risks:** Low Funding (20, Critical) and Marketing Failure (16, Critical).

**Historical benchmark (synthetic, 300 campaigns):** overall success rate 40%. Campaigns with a video succeeded 49.5% of the time vs. 19.8% without. Success rose from 31.5% (audience under 1,000) to 57.1% (8,000+). These are associations in the dataset, not causal claims.

## What's inside the workbook

| Area | Sheets |
|---|---|
| Start & summary | `Start_Here`, `Dashboard`, `KPI_Summary` |
| Historical data | `Historical_Campaigns` (raw), `Cleaned_Data`, `Campaign_Benchmark` |
| Goal & backers | `Funding_Goal`, `Funding_Simulator`, `Backer_Analysis` |
| Rewards & economics | `Reward_Strategy`, `Break_Even` |
| Marketing | `Marketing_Funnel`, `Channel_Analysis` |
| Scoring & decisions | `Campaign_Score`, `Scenario_Analysis`, `Risk_Register` |

**Scoring model (100 points):** Problem & Product Appeal 15 · Funding Goal Feasibility 15 · Pre-Launch Audience 15 · Campaign Page Quality 10 · Reward Strategy 10 · Pricing/Economics 10 · Marketing Readiness 10 · Founder Credibility 5 · Early Momentum 5 · Operational Readiness 5.

**Decision rule:** 80–100 Ready · 65–79 Launch after improvements · 50–64 Test further · under 50 Major rework.

## How to use it

1. Download and open [`model/Crowdfunding_Campaign_Performance_Predictor.xlsx`]https://1drv.ms/x/c/d25b756fc27d4ee3/IQAwyVqcK21GTr7WEYjZK6H6AZZ_UvyRA6gEwt4KkGc2R1k?e=dIoHIp in Excel.
2. Read `Start_Here`, then edit the **blue input cells** (funding goal, visitors, conversion, rewards, channel assumptions, score inputs). Black cells are formulas.
3. Review `Dashboard` for the score, scenarios and recommendation. Use the filters to explore the historical benchmark.
4. To use your own project, replace GreenNest's inputs. For real benchmarks, replace the synthetic dataset with a cited source such as public Kickstarter data.

## Repository structure

```
├── assets/
│   ├── dashboard.png        # dashboard image (2400×1350)
│   ├── demo.mp4             # 54-second walkthrough
│   └── demo_preview.gif     # inline preview for this README
├── model/
│   └── Crowdfunding_Campaign_Performance_Predictor.xlsx
├──                  # Python used to render the image and video  
└── README.md
```

## Regenerate the dashboard image and video

The visuals are rendered from the workbook's calculated values, so the workbook must have been saved in Excel at least once.

```bash
pip install -r requirements.txt     # the video step also needs ffmpeg
cd scripts
python dash.py                      # writes ../assets/dashboard.png
python video.py                     # writes ../assets/demo.mp4
```

## Data disclosure and limitations

- The 300-campaign dataset is **synthetic**, generated with a fixed random seed. It is not Kickstarter or Indiegogo data.
- GreenNest is an illustrative startup. All its inputs (audience, costs, conversion) are assumptions.
- The score is an educational framework, **not a statistical probability of success**. Projections are estimates from stated assumptions, not guarantees.
- Channel attribution is estimated; validate with UTM links once a campaign is live.
