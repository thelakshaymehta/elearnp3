Here’s the updated version with that detail included:

⸻

Subject: Re: New AO page keeps spinning during SSO from Schwab.com to Schwabplan.com

Hi Kavitha,

I looked into the issue and found that the AO page was being loaded over HTTP, while the CORS configuration only allows requests from HTTPS (https://www.schwabplan.com).
When I manually changed the URL to HTTPS, the origin matched and the page started working.

Thanks,
Lakshay

⸻
