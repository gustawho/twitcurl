## twitcurl
**twitcurl** is a pure C++ library for twitter APIs. twitcurl uses cURL for handling HTTPS requests and responses & OAuth authentication methods.
  * v1.1 Twitter REST APIs
  * JSON
  * SSL

### APIs
Currently **twitcurl** has wrappers for following twitter REST APIs:

<b>Timeline methods:</b><br>
statuses/public_timeline<br>
statuses/friends_timeline<br>
statuses/user_timeline<br>
statuses/mentions<br>

<b>Status methods:</b><br>
statuses/show<br>
statuses/update<br>
statuses/destroy<br>

<b>User methods:</b><br>
users/show<br>
statuses/friends<br>
statuses/followers<br>

<b>Direct Message methods:</b><br>
direct_messages<br>
direct_messages/sent<br>
direct_messages/new<br>
direct_messages/destroy<br>

<b>Friendship methods:</b><br>
friendships/create<br>
friendships/destroy<br>
friendships/show<br>

<b>Social Graph methods:</b><br>
friends/ids<br>
followers/ids<br>

<b>Account methods:</b><br>
account/rate_limit_status<br>

<b>Favorite methods:</b><br>
favorites<br>
favorites/create<br>
favorites/destroy<br>

<b>Block methods:</b><br>
blocks/create<br>
blocks/destroy<br>
blocks/list<br>
blocks/ids<br>

<b>Saved Search methods:</b><br>
saved_searches<br>
saved_searches/show<br>
saved_searches/create<br>
saved_searches/destroy<br>

<b>Trends methods:</b><br>
trends<br>
trends/current<br>
trends/daily<br>
trends/weekly<br>
trends/available<br>


### Notes
* twitcurl returns JSON responses from twitter.com as it is. You need to have a JSON parser to parse the responses.
* twitcurl uses HMAC_SHA1  from <a href='http://www.codeproject.com/KB/recipes/HMACSHA1class.aspx'>http://www.codeproject.com/KB/recipes/HMACSHA1class.aspx</a>
* twitcurl uses base64 from <a href='http://www.adp-gmbh.ch/cpp/common/base64.html'>http://www.adp-gmbh.ch/cpp/common/base64.html</a>
*Check out <a href='http://www.json.org/'>http://www.json.org/</a> for C/C++ parsers.