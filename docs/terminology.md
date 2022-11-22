---
sidebar_position: 1
---

# Terminology

This section covers the domain language used at H&C.

## Contents

The contents are the core component of H&C. All contents can vi retrieved via the `/contents` API endpont. Contents can be of differet types, and this type is is defined by the `type` field.

Here you can find the description and hierarchy of the H&C contents:

* **Shows**: Single video assets, like the case of a movie. Use the `type=show` filter of the `/contents` endpoint to filter them.
* **Series**: Top level containers which are composed of one or more seasons. Use the `type=series` filter of the `/contents` endpoint to filter them.
* **Seasons**: Containers which are composed of one or more episodes. Use the `type=season` filter of the `/contents` endpoint to filter them.
* **Episodes**: Single video assets belonging to a Season. Use the `type=episode` filter of the `/contents` endpoint to filter them.
* **TV Channels**: TV Channels are single live video streams. Use the `type=tv_channel` filter of the `/contents` endpoint to filter them..
* **Live Events**: On the same way as the series, Live Events are top level containers which can contain Live Streams, On Demand Live videos and Rider Clips. Use the `type=live_event` filter of the `/contents` endpoint to filter them.
* **Live Stream**: Single video streams which belong to a Live Event. Use the `type=on_demand_live` filter of the `/contents` endpoint to filter them.
* **On Demand Live**: Single video assets belonging to a Live Event. Use the `type=on_demand_live` filter of the `/contents` endpoint to filter them.
* **Rider Clips**: Single video assets belonging to a Live Event. Use the `type=rider_clip` filter of the `/contents` endpoint to filter them.

