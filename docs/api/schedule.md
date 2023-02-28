---
sidebar_position: 3
---

# Schedule

## GET `/schedule`

The **GET** `/schedule` endpoint is used to retrieve the streams schedule, providing information about the status of the streams of the differnt events. For example, you can check if a stream is live or not. 

#### Headers

* **Accept**: `application/json`

#### Query Parameters

* **`live`**: If this paramter is present and set to `1`, only the scheduled elements which are currently live will be retrieved.

* **`upcoming`**: If this paramter is present and set to `1`, only the upcoming scheduled elements will be retrieved.

* **`days`**: When the `upcoming` parameter is set to `1`, the `days` parameter can be used to delimit the number of days in the future for the scheduled elements.

* **`content_id`**: used to filter the scheduled elements by the content or live event they belong to.

 ***Examples***: `24864`

* **`perPage`**: The maximum number of elements to get.

 ***Examples***: `10`, `20`

 * **`page`**: The page number to get. Here are some example values:

 ***Examples***: `1`, `4`

* **`timeZone`**: Used to inform about the timezone of the user. When this parameter is present, the start and end dates of the contents will be localised for the users via the `timezone_start_date` and `timezone_end_date` attributes.

 ***Examples***: `Europe/London`, `UTC+03:00`, `03:00`

* **`order_by`**: Used to specify the field used to order the content. If this parameter is not specified, the contents will be ordered by cration date by default.

 ***Examples***: `created_at`

* **`order_direction`**: Allows alter the ascending or descending ordering of the results. The default value is `DESC` and the possible values are `ASC` and `DESC`. As an example:

 ***Examples***: `ASC`, `DESC`