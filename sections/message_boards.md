Message Boards
==============

All messages under a Basecamp are children of a Message Board resource. If you'd like to browse through messages in a Basecamp, this is a good place to start!

Endpoints:

- [Get message boards](#get-message-boards)
- [Get message board](#get-message-board)
- [Hide message board tool](#hide-message-board)

Get message boards
------------------

* `GET /buckets/1/message_boards.json` will return an array, with the first entry being the message board for the Basecamp with an ID of `1`.

This payload includes the most recent 10 messages in the `messages` key. To retrieve more, see the [Get messages][1] endpoint.

###### Example JSON Response

``` json
[
   {
      "bucket" : {
         "account_id" : 31989850,
         "created_at" : "2015-10-27T12:00:28.313-05:00",
         "description" : "Let's talk about the company!",
         "client_company_id" : null,
         "id" : 1042979250,
         "creator_id" : 1007299144,
         "updated_at" : "2015-10-27T12:00:28.313-05:00",
         "name" : "Honcho Design Newsroom"
      },
      "bucket_path" : "/195539477/buckets/2085958496",
      "comments_count" : 0,
      "created_at" : "2016-01-27T11:00:28.446-06:00",
      "creator" : {
         "name" : "Victor Cooper",
         "avatar_url" : "https://3.basecamp-static.com/195539477/people/BAhpBEgqCjw=--8266bb0507508f3d46050d57b65924d5e2a005f3/avatar-64-x4",
         "id" : 1007299144,
         "email_address" : "victor@honchodesign.com"
      },
      "messages" : [
        ...
      ],
      "id" : 9007199254741044,
      "messages_count" : 16,
      "status" : "active",
      "title" : "Message Board",
      "type" : "Message::Board",
      "updated_at" : "2016-02-03T15:40:39.036-06:00",
      "url" : "https://3.basecamp.com/195539477/buckets/2085958496/message_boards/9007199254741044",
   }
]
```

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/message_boards.json
```


Get message board
------------------

* `GET /buckets/1/message_boards/2.json` will return the message board for the Basecamp with an ID of `1`.

The payload returned is the same as the [Get message boards](#get-message-boards) endpoint, just not inside of an array.

###### Copy as cURL

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://3.basecamp.com/$ACCOUNT_ID/buckets/1/message_boards/2.json
```


Hide message board tool
-----------------------

If you'd like to remove the message board from the list of active tools for a Basecamp, use the [Trash a recording][2] endpoint with the ID of the message board as the recording ID.


[1]: https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#get-messages
[2]: https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#trash-a-recording