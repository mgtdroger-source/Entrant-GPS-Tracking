TD6 Entrant Tracker TEST v0.04

Change from v0.03:
- Offline queue recovery now submits up to 5 reports concurrently.
- Each report still uses the proven trackingSubmit endpoint.
- Reports are removed from local storage only after Google accepts them.
- Failed reports remain queued for retry.
- 15-second test interval retained for comparison testing.

Test:
1. Clear Tracking sheet rows, retaining the header.
2. Start online and confirm normal sends.
3. Use flight mode long enough to queue at least 15-20 reports.
4. Restore connection and time how long the queue takes to reach zero.
5. Confirm every sequence appears once in the sheet.
