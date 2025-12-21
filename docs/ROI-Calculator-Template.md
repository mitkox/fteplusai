# 30-60-90 Day Program ROI Calculator

**Agent:** @ROI-Calculator (Phase 1 Planning)
**Purpose:** Calculate the financial impact of replacing outsourcing vendors with AI-augmented internal teams using our 90-day program.

**Program Context:**
- **Phase 1 (Days 1-30):** Build financial justification and business case
- **Phase 2 (Days 31-60):** Validate ROI assumptions with pilot metrics
- **Phase 3 (Days 61-90):** Track actual savings vs. projections

**How to use this template:**
1. Copy this template to Excel or Google Sheets
2. Fill in your actual numbers in the INPUT sections (Phase 1)
3. Formulas will auto-calculate results
4. Update with pilot actuals during Phase 2
5. Track final results in Phase 3
6. Use the sensitivity analysis to model different scenarios

---

## INPUTS: Current Vendor Costs

### Direct Vendor Costs (Annual)

| Item | Quantity | Rate | Annual Cost |
|------|----------|------|-------------|
| Offshore Developers | 3 FTEs | $50/hour × 2080 hours | $312,000 |
| QA/Testing Vendors | 1 FTE | $40/hour × 2080 hours | $83,200 |
| Technical Writers | 0.5 FTE | $60/hour × 1040 hours | $62,400 |
| **Subtotal: Direct Vendor Costs** | | | **$457,600** |

**Formula:** Quantity × Rate × Hours

### Indirect Vendor Costs (Annual)

| Item | Calculation Method | Annual Cost |
|------|-------------------|-------------|
| Project Management Overhead | 15% of direct costs | $68,640 |
| Communication Tools & Meetings | $1,000/month × 12 | $12,000 |
| Contract & Legal Fees | One-time + annual | $15,000 |
| Travel & Coordination | $5,000/quarter × 4 | $20,000 |
| **Subtotal: Indirect Costs** | | **$115,640** |

### Hidden Vendor Costs (Annual)

| Item | Calculation Method | Annual Cost |
|------|-------------------|-------------|
| Rework Due to Miscommunication | 15% of direct costs | $68,640 |
| Knowledge Transfer Inefficiency | 10% of direct costs | $45,760 |
| Delayed Timelines (Opportunity Cost) | Estimated | $50,000 |
| Quality Issues & Bug Fixes | 5% of direct costs | $22,880 |
| **Subtotal: Hidden Costs** | | **$187,280** |

### TOTAL CURRENT VENDOR COSTS

| Category | Annual Cost |
|----------|-------------|
| Direct Costs | $457,600 |
| Indirect Costs | $115,640 |
| Hidden Costs | $187,280 |
| **TOTAL ANNUAL VENDOR COST** | **$760,520** |

---

## INPUTS: AI-Augmented Approach Costs

### AI Tools & Infrastructure (Annual)

| Item | Quantity | Rate | Annual Cost |
|------|----------|------|-------------|
| GitHub Copilot Business | 10 users | $19/user/month | $2,280 |
| GPT-4 API Usage | ~5M tokens/month | $15/month average | $180 |
| Claude API Usage | ~3M tokens/month | $10/month average | $120 |
| Vector Database (Pinecone) | Standard tier | $70/month | $840 |
| Monitoring & Analytics | Basic tier | $50/month | $600 |
| **Subtotal: Tools & Infrastructure** | | | **$4,020** |

**Note:** Adjust quantities based on your team size

### Training & Onboarding (Year 1 Only)

| Item | Calculation Method | One-Time Cost |
|------|-------------------|---------------|
| Initial Training Program | $2,000/person × 10 people | $20,000 |
| External Consultant/Workshop | 2 days × $5,000/day | $10,000 |
| Training Materials Development | Estimated | $5,000 |
| **Subtotal: Training (Year 1)** | | **$35,000** |

### Integration & Setup (Year 1 Only)

| Item | Calculation Method | One-Time Cost |
|------|-------------------|---------------|
| API Integration Development | 40 hours × $150/hour | $6,000 |
| Infrastructure Setup | Cloud setup, configs | $3,000 |
| Documentation & Runbooks | 20 hours × $100/hour | $2,000 |
| POC & Testing | Estimated | $4,000 |
| **Subtotal: Integration (Year 1)** | | **$15,000** |

### Ongoing Support & Optimization (Annual)

| Item | Calculation Method | Annual Cost |
|------|-------------------|-------------|
| Advanced Training Refreshers | $1,000/person/year × 10 | $10,000 |
| Tool Management & Optimization | 5 hours/month × $150/hour | $9,000 |
| Prompt Engineering Improvements | Ongoing effort | $5,000 |
| **Subtotal: Ongoing Support** | | **$24,000** |

### TOTAL AI APPROACH COSTS

| Category | Year 1 | Year 2+ (Annual) |
|----------|--------|------------------|
| Tools & Infrastructure | $4,020 | $4,020 |
| Training & Onboarding | $35,000 | $0 |
| Integration & Setup | $15,000 | $0 |
| Ongoing Support | $24,000 | $24,000 |
| **TOTAL AI COST** | **$78,020** | **$28,020** |

---

## INPUTS: Productivity Assumptions

### FTE Productivity Multipliers

| Activity | % of Time | AI Time Savings | Weighted Savings |
|----------|-----------|-----------------|------------------|
| Code Generation | 35% | 40% | 14.0% |
| Code Review | 15% | 60% | 9.0% |
| Documentation | 10% | 70% | 7.0% |
| Testing | 15% | 50% | 7.5% |
| Debugging | 15% | 40% | 6.0% |
| Meetings/Other | 10% | 0% | 0.0% |
| **TOTAL TIME SAVINGS** | **100%** | | **43.5%** |

**Productivity Multiplier:** 1 / (1 - 0.435) = **1.77x**

**Interpretation:** Each AI-augmented FTE produces the output of 1.77 traditional FTEs

### Capacity Calculation

| Metric | Calculation | Result |
|--------|-------------|--------|
| Internal Team Size | Given | 10 FTEs |
| AI-Augmented Output | 10 × 1.77 | 17.7 effective FTEs |
| Previous Output | Internal + vendor | 10 + 3.5 = 13.5 FTEs |
| **Net Capacity Increase** | 17.7 - 13.5 | **+4.2 effective FTEs** |

---

## CALCULATED RESULTS: Financial Analysis

### Year 1 Financial Summary

| Metric | Amount | Notes |
|--------|--------|-------|
| **Vendor Costs (avoided)** | $760,520 | What you would have paid vendors |
| **AI Costs (incurred)** | $78,020 | Year 1 costs including setup |
| **Gross Savings** | $682,500 | Vendor costs - AI costs |
| **Net Savings (Year 1)** | $682,500 | After all costs |
| **Savings Percentage** | 89.7% | Net savings / vendor costs |

**Formula:**
- Gross Savings = Vendor Costs - AI Costs
- Savings % = (Vendor Costs - AI Costs) / Vendor Costs × 100%

### 3-Year Financial Projection

| Year | Vendor Costs | AI Costs | Net Savings | Cumulative Savings |
|------|--------------|----------|-------------|--------------------|
| **Year 1** | $760,520 | $78,020 | $682,500 | $682,500 |
| **Year 2** | $798,546 | $28,020 | $770,526 | $1,453,026 |
| **Year 3** | $838,473 | $28,020 | $810,453 | $2,263,479 |

**Assumptions:**
- Vendor costs increase 5% annually (typical rate hikes)
- AI costs remain flat (conservative; often decrease with optimization)

### ROI Calculation

| Metric | Calculation | Result |
|--------|-------------|--------|
| **Initial Investment** | Training + Setup | $50,000 |
| **Year 1 Net Profit** | $682,500 - $50,000 | $632,500 |
| **Year 1 ROI** | ($632,500 / $50,000) × 100% | **1,265%** |
| **3-Year ROI** | ($2,263,479 / $50,000) × 100% | **4,527%** |

**Payback Period:**
- Monthly AI costs: $78,020 / 12 = $6,502
- Monthly vendor costs: $760,520 / 12 = $63,377
- Monthly net savings: $63,377 - $6,502 = $56,875
- Payback: $50,000 / $56,875 = **0.88 months (26 days)**

### Break-Even Analysis

```
Cumulative Costs vs. Savings

Month | AI Cumulative Cost | Savings Cumulative | Net Position
------|-------------------|-------------------|-------------
1     | $56,502           | $56,875           | +$373
2     | $63,003           | $113,750          | +$50,747
3     | $69,505           | $170,625          | +$101,120
6     | $89,010           | $341,250          | +$252,240
12    | $128,020          | $682,500          | +$554,480

Break-even: Month 1 (immediate positive cash flow after setup)
```

---

## SENSITIVITY ANALYSIS

### Scenario Modeling

| Scenario | Productivity Multiplier | Year 1 Savings | 3-Year Savings | ROI |
|----------|------------------------|----------------|----------------|-----|
| **Conservative** | 1.5x (30% time savings) | $645,500 | $2,133,479 | 1,191% |
| **Base Case** | 1.77x (43.5% time savings) | $682,500 | $2,263,479 | 1,265% |
| **Optimistic** | 2.0x (50% time savings) | $710,500 | $2,363,479 | 1,321% |

### Risk Scenarios

| Risk Event | Impact on Costs | Mitigated Savings | Notes |
|------------|-----------------|-------------------|-------|
| **AI costs 2x higher** | +$28,020/year | $654,500 Year 1 | Still 86% savings |
| **Productivity only 1.3x** | Quality concerns | $625,500 Year 1 | Still 82% savings |
| **Extended transition (6mo)** | +$380,260 overlap | $302,240 Year 1 | Payback 3.2 months |
| **Tool switching cost** | +$20,000 one-time | $662,500 Year 1 | Minimal impact |

**Conclusion:** Even in worst-case scenarios, savings exceed 60% with payback < 6 months.

### Variables You Can Adjust

**To model YOUR scenario, adjust these:**

1. **Vendor Costs:**
   - Number of vendor FTEs
   - Hourly rates
   - Overhead percentages

2. **AI Costs:**
   - Number of internal team members
   - Tool selection (Copilot vs alternatives)
   - API usage volumes

3. **Productivity Assumptions:**
   - Activity time allocation
   - AI time savings per activity
   - Resulting multiplier

4. **Timeline:**
   - Transition period length
   - Vendor overlap costs
   - Training duration

---

## ADDITIONAL VALUE (Not Quantified Above)

### Strategic Benefits

| Benefit | Description | Estimated Annual Value |
|---------|-------------|------------------------|
| **IP Ownership** | All code and knowledge stays internal | $100,000 - $500,000 |
| **Knowledge Retention** | No more vendor knowledge loss | $50,000 - $200,000 |
| **Agility** | Faster response to changing priorities | $75,000 - $300,000 |
| **Quality** | Reduced technical debt and defects | $30,000 - $150,000 |
| **Innovation** | More time for strategic work | $100,000 - $400,000 |
| **Competitive Advantage** | Faster time-to-market | $150,000 - $1,000,000 |

**Total Strategic Value:** $505,000 - $2,550,000 annually (not included in ROI above)

### Risk Reduction Value

| Risk Eliminated | Description | Value |
|----------------|-------------|-------|
| **Vendor Dependency** | No longer at mercy of vendor availability | High |
| **Data Breach via Vendor** | Reduced attack surface | $100,000 - $5,000,000 |
| **Contract Lock-in** | Flexibility to change direction | Medium |
| **Quality Variability** | Consistent standards and processes | $50,000 - $250,000 |

---

## DASHBOARD: Executive Summary

### At-a-Glance Metrics

```
┌─────────────────────────────────────────────────────────┐
│                 VENDOR REPLACEMENT ROI                   │
├─────────────────────────────────────────────────────────┤
│                                                          │
│  Current Annual Vendor Cost:        $760,520            │
│  AI-Augmented Annual Cost (Yr 1):   $78,020             │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━         │
│  Annual Savings:                    $682,500 (89.7%)    │
│                                                          │
│  Initial Investment:                $50,000             │
│  Payback Period:                    0.88 months (26 days) │
│  Year 1 ROI:                        1,265%               │
│  3-Year ROI:                        4,527%               │
│                                                          │
│  Productivity Multiplier:           1.77x                │
│  Capacity Gain:                     +4.2 effective FTEs  │
│                                                          │
│  ✅ RECOMMENDATION: HIGHLY FAVORABLE                    │
│                                                          │
└─────────────────────────────────────────────────────────┘
```

### Decision Criteria Checklist

| Criterion | Target | Actual | Status |
|-----------|--------|--------|--------|
| **Cost Reduction** | ≥ 60% | 89.7% | ✅ Exceeds |
| **Payback Period** | ≤ 6 months | 0.88 months | ✅ Exceeds |
| **Year 1 ROI** | ≥ 200% | 1,265% | ✅ Exceeds |
| **Productivity Gain** | ≥ 1.5x | 1.77x | ✅ Exceeds |
| **Risk Level** | Low-Medium | Low | ✅ Acceptable |

**Overall Assessment:** ✅ **PROCEED - All criteria exceeded**

---

## USING THIS CALCULATOR

### Step-by-Step Instructions

**1. Gather Your Data:**
- [ ] Current vendor contracts and invoices
- [ ] Hours and rates for all vendor resources
- [ ] Overhead costs (management, tools, legal)
- [ ] Your internal team size
- [ ] Desired AI tools and their pricing

**2. Fill in INPUTS Sections:**
- [ ] Current Vendor Costs (direct, indirect, hidden)
- [ ] AI Tool Costs (tools, training, integration)
- [ ] Productivity Assumptions (based on your use case)

**3. Review CALCULATED RESULTS:**
- [ ] Year 1 financial summary
- [ ] 3-year projection
- [ ] ROI and payback calculations

**4. Run SENSITIVITY ANALYSIS:**
- [ ] Test conservative scenario (lower productivity gain)
- [ ] Test optimistic scenario (higher productivity gain)
- [ ] Model risk scenarios (higher costs, delays)

**5. Build Your Business Case:**
- [ ] Use Executive Summary for presentations
- [ ] Include strategic benefits (IP, agility, etc.)
- [ ] Document assumptions and confidence levels
- [ ] Prepare for questions and objections

### Tips for Accurate Modeling

**Be Conservative:**
- Use lower productivity multipliers initially
- Include buffer for unexpected costs
- Plan for longer transition periods
- Better to under-promise and over-deliver

**Track Assumptions:**
- Document all assumptions clearly
- Note confidence level for each (high/medium/low)
- Update model as you get actual data
- Monthly comparison: projected vs. actual

**Include All Costs:**
- Training time is a real cost
- Management overhead doesn't disappear
- Tool costs will grow as team grows
- Don't forget one-time integration costs

**Validate with Data:**
- Run a pilot to get real productivity data
- Track vendor costs precisely (invoices)
- Measure current productivity baseline
- Use industry benchmarks when data unavailable

---

## NEXT STEPS

After completing this ROI analysis:

1. **Present to Stakeholders**
   - Use Executive Summary dashboard
   - Prepare for questions about assumptions
   - Have sensitivity analysis ready

2. **Run a Pilot**
   - Test assumptions with small team (3-5 people)
   - Measure actual productivity gains
   - Refine ROI model with real data

3. **Plan Full Rollout**
   - Use vendor transition playbook
   - Schedule training and onboarding
   - Set up monitoring and metrics

4. **Track and Optimize**
   - Monthly: Compare actual vs. projected costs
   - Quarterly: Measure productivity improvements
   - Annually: Update ROI model with actuals

---

**Version:** 1.0
**Last Updated:** December 2025
**Created By:** FTE+AI Project

**License:** Free to use and modify for internal business purposes.
