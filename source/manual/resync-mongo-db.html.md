---
owner_slack: "#2ndline"
title: Resync a MongoDB database
section: Databases
layout: manual_layout
parent: "/manual.html"
old_path_in_opsmanual: "../opsmanual/infrastructure/howto/resync-mongo-db.md"
last_reviewed_on: 2017-05-30
review_in: 6 months
---

To
[resync](https://docs.mongodb.org/v2.4/tutorial/resync-replica-set-member/)
a member of a MongoDB cluster, run our force\_resync
[Fabric](https://github.com/alphagov/fabric-scripts) script:

    fab {env name} -H {host name} mongo.force_resync

The mongo.force\_resync command checks that you are not trying to
perform a resync on the primary member.

If you need to resync the
[primary](https://docs.mongodb.org/manual/core/replica-set-members/#replica-set-primary-member)
member, first resync all of the secondary members that require a resync,
then:

1.  Run mongo.step\_down\_primary:

        fab {env name} -H {host name} mongo.step_down_primary

2.  Run mongo.force\_resync against the former primary member

You can run mongo.status at any time to see the status of the cluster:

    fab {env name} -H {host name} mongo.status
