# Exercise 1 · Raw AI outputs

Unedited outputs from the three Exercise 1 prompts, each run in a fresh chat. My answers are in [strategic-map.md](strategic-map.md).

## V1 · Prompt 1 (shallow)

> Create a mindmap for a water tracking app.

The mindmap follows.

I built the mindmap with "Water tracker" at the centre and six feature branches, each with three sub-features:

- **Logging:** one-tap quick add, custom amounts and units, editing past entries
- **Goals:** daily target from body data, weekly and streak goals, adjustment for activity and heat
- **Reminders:** smart nudges based on intake, quiet hours and snooze, custom schedule
- **Insights:** daily and weekly charts, trends and best-day patterns, hydration score
- **Integrations:** Apple Health and Google Fit, smart bottle connections, home screen widgets
- **Profile:** units (ml or oz), privacy and data export, themes and accessibility

These are my suggestions for a typical water tracker, so I can swap any branch for features you have in mind.

## V2 · Prompt 2 (structured)

> You are a product manager. Create a mindmap for a mobile app that helps people track daily water intake. Include features, user needs, and potential problems.

The mindmap follows: the central node is the tracker app, with three branches for features, user needs and potential problems, and four points under each.

## V3 · Prompt 3 (strategic)

> You are a senior product manager at a health-tech startup preparing for a discovery sprint. Create a structured brainstorm mindmap for a mobile water-tracking app targeting busy adults aged 25 to 40 who know they should drink more but forget. Organize branches around: (1) core user jobs-to-be-done, (2) key friction points in existing behavior, (3) feature ideas ranked by effort vs. impact, (4) monetization paths with tradeoffs, (5) retention risks and how to address them. Flag any area where there's a real strategic tension to debate.

### Water-Tracking App: Discovery Mindmap

**Root:** Busy adults (25–40) who know they should drink more but forget

#### 1. Core jobs-to-be-done

- **Remember without thinking:** get a timely prompt tied to my day, not a generic clock reminder
- **Know where I stand:** see if I'm on track at a glance, without doing arithmetic
- **Log in seconds:** record a glass in one or two taps, mid-meeting or on the move
- **Feel in control:** treat hydration as a small, low-effort habit, not a chore or a source of guilt
- **Adjust to context:** account for workouts, heat, caffeine, alcohol, and long meeting blocks

**Working job statement:** *"When I'm deep in a workday, help me take a drink without making me think about it."*

#### 2. Friction points in existing behavior

- **Forgetting is the core problem, not willpower.** Users usually intend to drink; they lose track of time.
- **Logging is a chore.** Manual entry is the first habit to lapse. (This is a hypothesis to test in discovery.)
- **Targets feel arbitrary.** A generic "2 L a day" doesn't account for body size, activity, or climate, so users don't trust it.
- **Notifications feel naggy.** Frequent pings train people to dismiss or disable them.
- **Competitors are bloated.** Heavy onboarding, calorie-tracking clutter, and ads raise the cost of a simple task.
- **Benefits are invisible.** Hydration pays off slowly and quietly, so there's little immediate feedback.

#### 3. Feature ideas: effort vs. impact

| Quadrant | Feature | Effort | Impact |
|---|---|---|---|
| **Quick wins** (do first) | One-tap logging from lock screen or home-screen widget | Low | High |
| | Progress ring widget showing today's status | Low | High |
| | Reminders that pause during calendar-blocked focus time | Low–Med | High |
| | Forgiving streaks that allow catch-up, not "broken" resets | Low | Medium |
| **Big bets** (validate before building) | Context-aware nudges using weather, workouts (via HealthKit or Google Fit), and calendar load | High | High |
| | Adaptive daily goal from body weight, activity, and temperature | Medium | High |
| | Apple Watch haptic nudges | Medium | Medium–High |
| **Fill-ins** (low priority) | Drink types with caffeine or volume weighting | Low | Low–Med |
| | Themes, custom icons, badges | Low | Low |
| **Money pits** (defer) | Smart-bottle hardware integration | High | Medium (uncertain) |
| | AI hydration coach chat | High | Unclear |
| | Team or social challenges | High | Low–Med |

**Ranked build order:** one-tap logging → widget → calendar-aware reminders → forgiving streaks → adaptive goal → context-aware nudges (after a validation sprint). Hardware and AI coaching should wait for evidence of demand.

#### 4. Monetization paths and tradeoffs

- **Freemium subscription** (advanced reminders, insights, widgets)
  - *Pro:* recurring revenue, funds ongoing development
  - *Con:* willingness to pay for water tracking has a low ceiling, and habit apps churn
- **One-time purchase**
  - *Pro:* low friction, fits a simple utility
  - *Con:* low lifetime value, no funding for upkeep
- **Ads**
  - *Pro:* revenue from free users
  - *Con:* conflicts with a calm, health-focused brand and erodes trust
- **B2B / employer wellness**
  - *Pro:* larger contracts, and the workday is the context where forgetting happens
  - *Con:* a different buyer, a long sales cycle, and privacy scrutiny. It may pull the product toward employers and away from individual users.
- **Hardware bundle** (smart bottle)
  - *Pro:* strong margins, passive logging improves accuracy
  - *Con:* inventory, support costs, and a much higher bar for adoption
- **Brand or insurer partnerships** (sparkling water, gyms, insurers)
  - *Pro:* distribution
  - *Con:* sponsored-goal conflicts can damage the trust the app depends on

#### 5. Retention risks and mitigations

- **Notification fatigue → uninstall or disabled alerts.** Mitigate with adaptive frequency, context pauses, and a hard cap on daily nudges.
- **Novelty decay after the first few weeks.** Mitigate with progressive goals and light, periodic insights rather than constant feedback.
- **Guilt spiral after a missed day → abandonment.** Mitigate with forgiving streaks and catch-up framing.
- **Logging drop-off.** Mitigate with passive logging (Apple Health, bottle sensors) and widgets that reduce taps.
- **Setup friction.** Mitigate with smart defaults and a goal that works before any personalization.
- **Platform dependency.** Health-data permissions can be revoked. Mitigate by making the core loop work without them.

#### ⚠️ Strategic tensions to debate

1. **Reminders: recall vs. nagging.** More nudges improve recall but raise uninstall risk. Where is the line, and who decides: product data or user settings?
2. **Simplicity vs. personalization.** One-tap logging is the strongest hook, but personalized goals need health-data permissions and more onboarding. Which do we lead with?
3. **Passive vs. active logging.** Sensors are more accurate but require hardware, cost more, and narrow the addressable market. Software-only keeps reach high but accepts noisier data.
4. **Monetizing the habit vs. monetizing the data.** Employer and partner deals create revenue but may conflict with users' trust about their health data. This may be the sharpest tension in the set.
5. **Wellness claims vs. medical claims.** Hydration targets can drift into health claims with regulatory implications. Decide early how far the product will go, and check with legal.
6. **Wedge or platform?** Is water a standalone product, or the entry point to a broader hydration and wellness platform? The answer changes scope, positioning, and monetization.

#### Suggested discovery hypotheses to test

- Forgetting, not motivation, is the main barrier for this segment (test with diary studies and in-context interviews)
- Calendar-aware reminders outperform fixed-time reminders on engagement (test with a prototype)
- Users would accept fewer, smarter nudges over more frequent ones (test with a notification-cadence experiment)

I can turn this into a visual mindmap widget or a shareable doc for the sprint team if you'd like.
