# gama.ppa

This action creates a GitHub Pages site using Jekyll and CloudFlare Pages.
It is triggered by either a `workflow_dispatch` or a `workflow_call` event, both with the `tag` input referring to the tag attached to the release you wish to publish.

# Setup instructions

- Go to your CloudFlare dashboard
- Click on `Workers & Pages`, then `Pages` and `Connect to git`
- Select the repository
- Set framework as `Jekyll`
- Set build command as `jekyll build && mv __site/* _site` to enable the use of redirects and headers
- Set the following secrets: 
    - `BOT_GH_EMAIL` (the email of the bot account)
    - `BOT_GH_NAME` (the name of the bot account)
- Trigger the action and you are good to go 🎉! To add the repository do the following commands:
```bash
sudo -i
apt update
apt install ca-certificates
echo "deb [trusted=yes] https://<url to the CF Pages site> ./" | sudo tee -a /etc/apt/sources.list
``` 