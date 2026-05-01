# Home Assistant Blueprints

A collection of Home Assistant automation and script blueprints for fixing common smart home annoyances.

Each blueprint solves one specific problem. Pick what you need, click the import button, and you're done.

---

## Blueprints

### 🔌 Keep Matter/Thread Device Alive

Polls one or more entities every hour to prevent them from silently disappearing from Home Assistant.

**The problem.** IKEA's Matter-over-Thread bulbs (and some other Matter devices) stop reporting state after extended inactivity, even when they're powered. After a few days of sitting idle the entity goes unavailable and disappears from the UI, requiring a manual reset to recover.

**The fix.** This blueprint calls `homeassistant.update_entity` on a schedule, forcing HA to re-poll the device. The hourly heartbeat keeps the entity registered and responsive.

**Works for.** Any entity that benefits from periodic re-polling — Matter bulbs, Thread sensors, occasionally flaky Zigbee devices.

[![Open your Home Assistant instance and show the blueprint import dialog with this blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Frogerkerse%2Fhomeassistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fkeep-alive.yaml)

Or import manually with this URL:
```
https://github.com/rogerkerse/homeassistant-blueprints/blob/main/automation/keep-alive.yaml
```

---

## How to import a blueprint

**Easy way.** Click the "Open in Home Assistant" button next to the blueprint you want. Your HA instance will open the import dialog with the URL pre-filled. Confirm and you're done.

**Manual way.** In Home Assistant, go to **Settings → Automations & Scenes → Blueprints → Import Blueprint**, paste the GitHub URL, and click Preview, then Import.

Once imported, create an automation from the blueprint via **Settings → Automations & Scenes → Create Automation → Use Blueprint**.

## Contributing

Issues and pull requests are welcome. If you have a smart home annoyance that a blueprint could fix, open an issue describing the problem — even if you're not sure how to solve it.

By submitting a contribution, you agree to license it under the same terms as this repository (MIT). Please sign off your commits with `git commit -s` to certify you have the right to contribute the code (see the [Developer Certificate of Origin](https://developercertificate.org/)).

## License

[MIT](LICENSE) — use these blueprints however you like, just keep the copyright notice.
