# SpotifyJS — Display Your Current Song on the Internet

**Contributors:** HankFordham (https://github.com/HankFordham)  
**Tags:** Spotify, HTML, JavaScript, CSS, Music  
  
## Description  
  
A JavaScript code using Spotify Developer Tools Get Currently Playing Track API to display currently playing track.

## Instructions

1. Go to the Spotify Developer Dashboard and create a new application.
2. Once you have created the application, click on it to view its details.
3. Under the "Settings" tab, add a redirect URI. This can be any valid URL that you control, but it must be entered exactly as you will use it later.
4. Note down the "Client ID" and "Client Secret" values.
5. Open a browser window and go to the following URL, replacing CLIENT_ID and REDIRECT_URI with your own values.
```
https://accounts.spotify.com/authorize?client_id=CLIENT_ID&response_type=code&redirect_uri=REDIRECT_URI&scope=user-read-playback-state%20user-read-recently-played
```
6. If done properly, this should prompt you to Authorize the app using your Spotify account, thus linking the two. The URL bar should now contain an access token in the format (https://my-domain.com/callback?code=NApCCg..BkWtQ&state=34fFs29kd09). Note the value following "code=". This is your access token and you will need it in the next step.
7. Take your Client ID and Secret ID and put them in the format "CliendID:SecretID" and Base64 encode them (I used https://www.base64encode.net/).
8. Use your Base64 encoded Client ID:Secret ID, Access Token, and Redirect URI to run this cURL command.
```
curl -X POST -H "Authorization: Basic BASE64_ENCODED_CLIENTID_CLIENTSECRET" -H "Content-Type: application/x-www-form-urlencoded" -d "grant_type=authorization_code&code=AUTHORIZATION_CODE&redirect_uri=REDIRECT_URI" https://accounts.spotify.com/api/token
```
9. If done properly, this will should give you your refresh token.
10. In the JavaScript file, replace YOUR_CLIENT_ID, YOUR_CLIENT_SECRET, and YOUR_REFRESH_TOKEN with your own.
11. You can display your widget using HTML by using something basic like:
```
<div id="song" style="display: flex; align-items: center;"></div>
```
