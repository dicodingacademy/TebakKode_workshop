# Sample Final App for tebakkode LINE bot

## First Setup

- clone/download & extract project
- place on your localhost
- open file htdocs/.env in your project, and add some configuration:
```
CI_ENV="development"
BASE_URL="" // your online project url in bluemix
DBHOST="" // dbhost i.e. sl-us-dal-9-portal.6.dblayer.com:21476
DBNAME="compose"
DBUSER="admin"
DBPASS="" // dbpassword i.e. RZHFYPOUKYIKUEKO
CHANNEL_ACCESS_TOKEN="" // channel access token code from LINE developer page
CHANNEL_SECRET="" // channel secret code from LINE developer page
```
- run `composer install`
- open file lib/vendor/linecorp/line-bot-sdk/src/LINEBot/HTTPClient/Curl.php and update constructor method just like this:
```
public function __construct($url)
{
    $this->ch = curl_init($url);

    // add these two lines
    curl_setopt($this->ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($this->ch, CURLOPT_SSL_VERIFYHOST, false);
}
```
- Feel free to add some issue in issue page. Enjoy!