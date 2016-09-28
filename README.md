# SndLatr source code

I (developer of sndlatr) no longer have the time to actively continue developing or maintaining SndLatr with the dedication it deservers.

Nathan Latka (http://nathanlatka.com/) has taken over the existing Chrome Extension item and will probably take over the existing server infrastructure and user base in a while. He intends to continue operating the service, professionalize it, and possibly commercialize/monetize it in the future.

**Update: The SndLatr extension offered by Nathan in the Chrome Web Store is NOT based on this code anymore. Please do not post issues here related to that Extension here.**

The SndLatr software itself is now publically available under the APACHE2 open source license. So anyone who likes to, can take it and host their own, autonomous version for free, or implement additional features and improvements directly. So feel free to fork it, host your own version and make it available to others, if you like.
Costs for hosting the service on Google App Engine are quite low (~$US 0,001 /user/month, or within the free quotas if you just need a few users).

My intentions for handing over the Chrome Extension to a new maintainer, while relasing the software as open source at the same time, is to give users a choice of how to continue using it. You can either do nothing, and trust Nathan continue operating it in your interest, or just roll your own version or find someone else who does.
Nathan has agreed to make any derivative work that he distributes within the next 3 months available under the same license terms.

I hope that this step will help this project to be maintained and improved properly in the future and allow anyone interested to contribute.


## Project Structure:
I did not maintain this code for quite while, many things are probably outdated.
I won't be accepting pull requests here, but am happy to link anyones fork who's willing to maintain it.

### gae/
Server-side Google Appengine Code.
Save your `client_secrets.json` from the API manager of the Google Cloud Console
here.

### client/
Client side code injected by extension into gmail ui.  Build it with `npm install &&
bower install && grunt`. The code in `gae/` is copied to the build output
(`dist/`) and is intended to be depolyed as-is to GAE.

Hosts configuration is in `client/app/scripts/sndlatr/constants\*.js`

### website/
Pure informational website. Build with grunt just like client.

### chrome-extension\* / firefox-addons-\*
Browser extensions for Chrome/Firefox

## local dev
For local development run `dev_appserver.py .` in `gae`, run `grunt server` in
`client` and start Chrome with `client/local_insecure_chrome.sh`.

### client unitt tests
Run `karma start` in `client/` to run tests in watch mode.

### gae tests
Run tests with `./run_tests.py` .
Test setup might need some fixing due to changes in gae / nosegae since I used
it the last time.
