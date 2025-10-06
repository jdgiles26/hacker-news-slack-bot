Slacker

Slacker is a bot that notifies you on Slack whenever your company or product is mentioned on Hacker News.

---

Steps to Run

Set up a Vercel cron job that pings the /api/cron endpoint every 60 seconds.
Store configuration in Upstash, including the lastCheckedId and the list of keywords to monitor.
Check for new posts using the Hacker News API’s maxitem endpoint, comparing posts between the last checked and the latest post ID for matches to your keywords.
Send notifications to Slack using the chat.postMessage method for any post that matches your keywords.
Unfurl links in Slack when the link_shared event triggers by sending a POST request to Slack using the chat.unfurl method.

---

Tech Summary

Vercel Functions for cron processes and webhook event subscriptions.
Vercel Cron Jobs to automatically trigger the cron endpoint.
Hacker News API to fetch new post data.
Slack API to send notifications and unfurl links.
Upstash (Redis) for maintaining state and storing the last checked post ID and monitored keywords.

---

Authentication Details

To authorize Slacker to your Slack workspace:

Click the Add to Slack button below.
Grant the requested scopes: chat:write, chat:write.public, links:read, links:write, commands, team:read.

[](https://slack.com/oauth/v2/authorize?scope=chat:write,chat:write.public,links:read,links:write,commands,team:read&client_id=12364000946.3845028209600)

You can also choose to deploy your own instance by following the same authentication process with your own Slack app credentials.
