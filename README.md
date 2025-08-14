I looked into the issue and found that the requests for the new AO page were being made over HTTP instead of HTTPS.
Since the page is loaded over HTTPS, the protocol mismatch was causing a CORS block in the browser, resulting in the AO page spinning without loading data.

I manually updated the URLs to use HTTPS, and the page started working as expected.
It looks like we’ll need to ensure all resource URLs for the new AO page use HTTPS by default to avoid this issue in the future.

Thanks,
Lakshay
