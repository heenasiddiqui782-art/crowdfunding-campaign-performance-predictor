# Crowdfunding Campaign Performance Predictor

An Excel decision-support model that scores a reward-based crowdfunding campaign's launch readiness, projects funding under three scenarios, and gives a launch recommendation. The worked example is **GreenNest**, an illustrative smart kitchen composter startup in India.

<img width="726" height="386" alt="P2 (S2) in outputs" src="https://github.com/user-attachments/assets/d7e55df6-4013-4027-8847-fac4aeee6fa4" />
<img width="818" height="394" alt="P2 (S1) in outputs" src="https://github.com/user-attachments/assets/882b19f3-c5a1-45b6-bafe-14257f0e028a" />


## Demo


https://github.com/user-attachments/assets/56a1c1e2-7404-44c6-92c1-7b381460b79a




## What the model does

- **Campaign Performance Score** (0–100) across 10 weighted categories, plus a pre-launch readiness score.
- **Funding simulator and scenarios**: Conservative / Base / Optimistic, with break-even and net contribution.
- **Marketing funnel and channel analysis**: 10 channels, estimated backers and cost per backer.
- **Historical benchmark** of 300 campaigns by category, country, goal band, duration and more.
- **Risk register** (probability × impact) and a final recommendation.

## Example result (Base inputs)

| Metric | Value |
|---|---|
| Campaign score | 62.2 / 100 (Significant Risk) |
| Funding goal / expected funding | ₹10.0L / ₹10.4L (104%) |
| Expected backers vs. required | 400 vs. 385 (break-even: 315) |
| Pre-launch readiness | 44 / 100 |
| Recommendation | **TEST FURTHER** |

## Repository layout

```
model/    Excel workbook https://1drv.ms/x/c/d25b756fc27d4ee3/IQAwyVqcK21GTr7WEYjZK6H6AZZ_UvyRA6gEwt4KkGc2R1k?e=xikZYU
assets/   dashboard.png, demo.mp

https://github.com/user-attachments/assets/43ce6973-1d39-4647-ad12-2673e29a6fb5


scripts/  Python used to render the dashboard image and video from the workbook
```

## Regenerate the visuals

```bash
pip install -r requirements.txt   # also needs ffmpeg for the video
cd scripts
python dash.py      # writes ../assets/dashboard.png
mkdir -p ../assets && python video.py   # writes ../assets/demo.mp4
```

## Data disclosure

The 300-campaign dataset is **synthetic** (fixed random seed), not Kickstarter/Indiegogo data. GreenNest and all its inputs are illustrative assumptions. Scores and projections are educational decision-support estimates, not probabilities or guarantees.

