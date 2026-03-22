# Implementation Notes

## Business objective
Measure lead generation behavior on a live small-business website.

## Key business questions
- Which pages or calls-to-action generate contact intent?
- How many site visitors submit an inquiry?
- Where does the lead funnel break down?

## Tracking design choices

### Why GTM?
GTM centralizes analytics instrumentation and avoids hardcoding individual tracking scripts across the application.

### Why use dataLayer for form submission?
The site already emits a custom `form_submit` event. Listening for that event is more reliable than relying only on generic DOM form triggers, especially in modern React/Next.js applications.

### Why these first events?
`contact_click` and `inquiry_submit` map directly to lead-intent and conversion behavior, making them useful for both business reporting and interview discussion.

## Validation workflow
1. Use GTM Preview to attach Tag Assistant to the site.
2. Trigger the user action on the website.
3. Verify the expected GTM event appears.
4. Confirm the expected tag fires.
5. Confirm the event arrives in GA4 DebugView.

## Interview talking points
- This implementation instruments upstream behavioral data capture, not just downstream reporting.
- The form submission flow uses a dataLayer-driven custom event trigger.
- The project demonstrates event design, trigger logic, debugging, and conversion measurement.
