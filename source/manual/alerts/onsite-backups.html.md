---
owner_slack: "#govuk-infrastructure"
title: Onsite backups
parent: "/manual.html"
layout: manual_layout
section: Icinga alerts
last_reviewed_on: 2017-05-16
review_in: 6 months
---

The backup machine (e.g. backup-1.management.integration) collects
backups from the various data stores.

The location of the backups is defined in
[govuk-puppet](https://github.com/alphagov/govuk-puppet/blob/master/modules/govuk/manifests/node/s_backup.pp)
