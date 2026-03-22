# Implementation Notes

## Business objective
The goal of this setup was to measure real lead behavior on a live small-business website. I wanted to understand how visitors move from browsing the site to showing intent and submitting an inquiry.

## Key business questions
Which pages or calls to action are getting people to reach out?
How many visitors are actually submitting an inquiry?
Where are people dropping off in the lead funnel?

## Tracking design choices

### Why GTM?
I used Google Tag Manager to centralize the tracking setup instead of hardcoding separate scripts throughout the site. That makes it easier to manage events, test changes, and keep the implementation organized.

### Why use dataLayer for form submission?
The site was already pushing a custom form_submit event. Since that event is generated directly by the application, it felt more reliable than depending only on generic DOM-based form triggers. That approach is especially useful in React/Next.js environments where UI behavior is often handled dynamically.

### Why these first events?
I started with contact_click and inquiry_submit because they map directly to lead intent and conversion behavior. They were the clearest first signals to track and made the project useful both from a business standpoint and as an analytics implementation example.

## Validation workflow
1. Use GTM Preview to attach Tag Assistant to the site.
2. Trigger the user action on the website.
3. Verify the expected GTM event appears.
4. Confirm the expected tag fires.
5. Confirm the event arrives in GA4 DebugView.

### Results 

Established a clear lead funnel from contact interaction to inquiry submission

Enabled measurement of conversion events in GA4

Created a foundation for future tracking, such as attribution (UTMs) and CRM integration

Improved visibility into where users drop off before converting
