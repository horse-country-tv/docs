---
sidebar_position: 2
---

# Contents

## GET `/contents`

The **GET** `/contents` endpoint is used to retrieve contents. For example, it can be useful when retrieving search results or when displaying a set of shows, series or episodes on a rail.

#### Headers

* **Accept**: `application/json`

#### Query Parameters

* **`type`**: Used to filter the type of the content to retrieve. When it's not specified, all contents of all types will be returned. These are the possible values: `show`, `series`, `season`, `episode`, `live_event`, `live_stream`, `on_demand_live`, `rider_clip` and `tv_channel`.You can specify many comma separated types.

 ***Examples***: `show,series`, `show,series,live_event`

* **`search`**: A text to search a contents by its name, description and metadata.

 ***Examples***: `event london`, `Daisy Dines`

* **`name`**: A text to filter contents by only the content name:

 ***Examples***: `event london`, `Daisy Dines`

* **`perPage`**: The maximum number of elements to get.

 ***Examples***: `10`, `20`

 * **`page`**: The page number to get. Here are some example values:

 ***Examples***: `1`, `4`

 * **`parent_id`**: The parent entry ID. It can be useful to get the season of an episode or the live event an on demand content belongs to.

 ***Examples***: `846`, `34754`

 * **`term`**: Used to filter the entries by term ID.

 ***Examples***: `20`, `5`

 * **`terms`**: In the same way as the `term` parameter, it accepts a term ID as a value, or many comma separated term IDs.

 ***Examples***: `20`, `20,5`

* **`tags`**: Allows to filter the contents by the tags assigned. This parameter accepts a single tag name or a set of comma separated tag names.

 ***Examples***: `british dressage`, `british dressage,uk-eventing`

* **`timeZone`**: Used to inform about the timezone of the user. When this parameter is present, the start and end dates of the contents will be localised for the users via the `timezone_start_date` and `timezone_end_date` attributes.

 ***Examples***: `Europe/London`, `UTC+03:00`, `03:00`

* **`order_by`**: Used to specify the field used to order the content. If this parameter is not specified, the contents will be ordered by cration date by default.

 ***Examples***: `created_at`, `start_date`, `name`

* **`order_direction`**: Allows alter the ascending or descending ordering of the results. The default value is `DESC` and the possible values are `ASC` and `DESC`. As an example:

 ***Examples***: `ASC`, `DESC`

## GET `/contents/{contentId}`

The **GET** `/contents/{contentId}` endpoint is used to retrieve a single content. For example, it can be useful when showing a video or a stream.

#### Route Parameters

* **contentId**: The content ID to retrieve.

  ***Examples***: `2`, `2400`
