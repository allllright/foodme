Here is a polished, more logical, and more structured version of your Section 3.
I kept it concise and professional while improving flow, clarity, and reasoning.


---

3. Comparison with Existing Scaling Strategies

AWS provides multiple scaling approaches, each designed for different workload patterns. Predictive scaling does not replace other policies; rather, it complements them. This section provides a structured comparison to clarify when predictive scaling is the right fit.


---

3.1 High-Level Positioning

Scaling strategies fall into two categories:

Reactive scaling – responds to load after it increases

Proactive scaling – prepares capacity before load arrives


Predictive scaling is unique because it brings automation and adaptability to proactive scaling, something scheduled scaling cannot achieve.


---

3.2 Comparison Table

Strategy	Category	How It Works	Strengths	Limitations

Predictive Scaling	Proactive (ML-driven)	Learns recurring patterns and adjusts capacity ahead of time	Removes scale-out lag; ideal for workloads with warm-up time; adapts automatically as patterns evolve	Needs consistent patterns; no predictive scale-in; may over-provision if forecast is conservative
Target Tracking	Reactive	Adjusts capacity to maintain a target metric (e.g., 50% CPU)	Simple; covers unpredictable spikes; essential safety net for scale-in	Reactive by nature; may lag during sudden increases or long instance warm-ups
Step Scaling	Reactive	Scales in steps when CloudWatch alarms breach thresholds	Highly tunable responses; can react aggressively	Harder to maintain; prone to oscillation; less adaptive to changing workloads
Scheduled Scaling	Proactive (manual)	Sets capacity changes at fixed times	Precise for known events (e.g., business hours)	Completely static; requires frequent updates; cannot react to pattern shifts



---

3.3 Interpretation and Practical Guidance

Predictive scaling ≈ automated scheduled scaling with machine learning.
It removes the manual overhead of maintaining schedules while still preparing capacity before peaks.

Target tracking remains mandatory.
Predictive scaling only performs scale-out; all scale-in decisions must be handled by a reactive policy.
It also protects the workload during unpredictable traffic bursts.

Predictive scaling should not operate alone.
It excels at handling recurring load, while target tracking ensures coverage for unpredictable spikes.

Scheduled scaling is now a fallback tool.
Use it only for workloads with fixed, non-changing demand cycles. Predictive scaling is superior when patterns evolve over time.

Step scaling is for specialised cases.
Only use it when a workload requires very aggressive or manually tuned reactions.



---

3.4 Summary

Predictive scaling is most valuable when workloads have recurring demand and non-trivial warm-up times. It should be combined with target tracking to create a robust, hybrid scaling strategy that handles both predictable and unpredictable behaviour.


---

If you want, we can now proceed to Section 4: Cost, Scaling Impact, and Limitations, keeping the same structure and tone.
