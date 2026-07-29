TD6 Entrant Tracker TEST v0.05

Focused proof bake from the tested v0.04 baseline:
- Persists the sequence number in localStorage across stop/reopen.
- Sorts queued records by sequence before each five-at-a-time replay group.
- Keeps a 15-second queue retry timer active even after Stop Tracking.
- Retains reports until Google accepts them.
- Adds optional End of Event proof logic from tracker-config.json.
- End of Event arms only after moving at least 300 m from the final waypoint.
- Returning within the 30 m final-waypoint radius queues one END_OF_EVENT report,
  stops new GPS collection, and continues replaying stored reports.

Proof config:
- Crankhandle Sunday / Route 1 / Rally No. 1
- 30-second reporting
- Final waypoint uses the last recorded position from the 29-07-2026 road test.

Test:
1. Start inside the final waypoint radius: End of Event must remain Not armed.
2. Drive beyond 300 m: status must change to Armed.
3. Use flight mode if testing offline queue.
4. Return inside 30 m of the final waypoint.
5. Confirm End of Event appears and no new positions are collected.
6. Restore internet and confirm the queue reaches zero without pressing Start again.
