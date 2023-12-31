# Integration of SEO4Ajax on Akamai

[SEO4Ajax](https://www.seo4ajax.com) is a service that allows AJAX websites
(e.g. based on Angular, React, Vue.js, Svelte, Backbone, Ember, jQuery etc.) to
be indexable by search engines and social networks.

# Configuration

- Open the "Property Manager" in ​Akamai Control Center​
- Add a new "Rule" for SEO4Ajax called for example "Proxy bot requests to SEO4Ajax"
  - Add a "Match All" criteria testing if the "user-agent" is one of the following values: `google`, `bing`, `yandex`, `baidu`
  - Add a "Match All" criteria with the "AND" operator testing if the "file extension" is not of the following values: `jpg`, `gif`, `png`, `ico`, `css`, `woff`, `woff2`, `ttf` (add missing extensions depending on the resource types hosted on your website)
- Define the "Behavior"
  - Set the value of "Server Host Name value" to `api.seo4ajax.com`, make sure "Cache key hostname" and "Forward host header" are set to `Origin Hostname`
  - In the "Modify outgoing request path" section, select `Replace the entire path` for the "Action", and set the "replace with" value to `/<token>{{builtin.AK_ORIGINAL_URL}}` where `<token>` is the token of your website in SEO4Ajax
