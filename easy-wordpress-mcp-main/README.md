# easy-wordpress-mcp

**The easiest way to connect Claude AI to your WordPress site.**

No plugins to install on WordPress. No config files to edit by hand. No terminal expertise needed. Claude guides you through everything.

> Built and maintained by [vincentquero](https://github.com/vincentquero)

---

## What is this?

**easy-wordpress-mcp** is a bridge that lets Claude AI read and manage your WordPress site — write posts, update pages, moderate comments, manage WooCommerce products and orders, and much more.

It works with **Claude Code** (terminal) and **Claude Cowork** (desktop).

**Why this one instead of others?**

| Other WordPress MCPs | easy-wordpress-mcp |
|---|---|
| Require installing a PHP plugin on your WordPress server | **Nothing to install on WordPress** |
| Need composer, npm, and build steps | **One command, that's it** |
| Require JWT tokens and manual JSON config | **Claude walks you through setup** |
| Designed for developers | **Designed for everyone** |

---

## Installation Guide (5 minutes, one time only)

### Prerequisites

Before you start, you need two things on your computer:

1. **Node.js 18 or newer** — Check if you have it by opening your terminal and typing:
   ```
   node --version
   ```
   If you see `v18.x.x` or higher, you're good. If not, download it from [nodejs.org](https://nodejs.org/) (choose the "LTS" version, click the big green button, install it).

2. **Claude Code** or **Claude Cowork** — You should already have one of these installed. If not:
   - Claude Code (terminal): [claude.ai/code](https://claude.ai/code)
   - Claude Cowork (desktop): available through Anthropic

---

### Step 1: Add the MCP to Claude

Open your terminal (on Mac: search for "Terminal" in Spotlight) and run this single command:

```bash
claude mcp add easy-wordpress-mcp -- npx easy-wordpress-mcp
```

**What this does:** It tells Claude Code "hey, I want you to be able to talk to WordPress." Claude remembers this, so you only run it once.

**Where this runs:** On your computer. Nothing is installed on your WordPress site.

---

### Step 2: Create an Application Password on your WordPress site

This is how Claude will securely log into your WordPress site. It takes 30 seconds:

1. Open your browser and go to your **WordPress admin dashboard**
   (usually `https://yoursite.com/wp-admin`)

2. In the left sidebar, click **Users**, then click **Profile**

3. Scroll down until you see the section called **"Application Passwords"**

4. In the **"New Application Password Name"** field, type:
   ```
   Claude AI
   ```

5. Click the **"Add New Application Password"** button

6. WordPress will show you a password that looks like this:
   ```
   ABCD 1234 EFGH 5678 IJKL 9012
   ```

7. **Copy this password immediately and save it somewhere** (a note, a text file, etc.)

   > WordPress only shows this password ONCE. If you close the page without copying it, you'll need to create a new one.

---

### Step 3: Connect your site

1. Start a new conversation in Claude Code or Claude Cowork

2. Tell Claude something like:
   ```
   Connect to my WordPress site
   ```

3. Claude will ask you for three things. Give them one at a time or all at once:

   - **Your site URL** — e.g., `https://mysite.com` (include the `https://`)
   - **Your WordPress username** — the one you log in with
   - **The Application Password** you just created — paste the whole thing with spaces

4. Claude will test the connection and confirm it works.

**That's it. You're done. This setup is saved permanently.**

From now on, just open Claude and ask it to do anything with your WordPress site.

---

### Step 4 (optional): Managing multiple sites

If you manage more than one WordPress site, just tell Claude:
```
Connect another WordPress site
```
Claude will walk you through the same steps. You can then say "switch to my other site" to toggle between them.

---

## What Can You Do?

Just talk to Claude naturally. Here are some examples:

### Writing & Content
- *"Write a blog post about our spring sale"*
- *"Show me all my draft posts"*
- *"Update the About page with this new text: ..."*
- *"Create a new page called Contact Us"*
- *"Delete the old test post"*

### Comments & Moderation
- *"What comments are waiting for approval?"*
- *"Approve all pending comments"*
- *"Mark that spam comment as spam"*

### Organization
- *"List all my categories"*
- *"Create a new category called Tutorials"*
- *"Show me all tags"*

### Media
- *"Show me recent images in my media library"*
- *"What's the URL of media item 42?"*

### Site Administration
- *"What plugins are installed?"*
- *"What theme is active?"*
- *"Show me my site settings"*
- *"Change the site tagline to: Your new tagline"*

### WooCommerce (auto-detected if installed)
- *"List our products sorted by price"*
- *"Create a new product: Premium Widget at $49.99"*
- *"Show me today's orders"*
- *"Mark order #1234 as completed"*

---

## All 49 Available Tools

<details>
<summary>Click to see the full list of tools</summary>

### Setup & Connection
| Tool | Description |
|------|-------------|
| `setup_wordpress` | Connect a new WordPress site (guided wizard) |
| `connection_status` | Check if your connection is working |
| `list_sites` | See all your connected sites |
| `switch_site` | Switch active site |
| `remove_site` | Remove a saved site |

### Posts
| Tool | Description |
|------|-------------|
| `list_posts` | Search and list blog posts |
| `get_post` | Get a post with full content |
| `create_post` | Create a new post |
| `update_post` | Edit an existing post |
| `delete_post` | Trash or delete a post |

### Pages
| Tool | Description |
|------|-------------|
| `list_pages` | List website pages |
| `get_page` | Get a page with full content |
| `create_page` | Create a new page |
| `update_page` | Edit an existing page |
| `delete_page` | Trash or delete a page |

### Media
| Tool | Description |
|------|-------------|
| `list_media` | Browse media library |
| `get_media` | Get media file details |
| `delete_media` | Delete a media file |

### Comments
| Tool | Description |
|------|-------------|
| `list_comments` | List and filter comments |
| `get_comment` | Read a specific comment |
| `create_comment` | Post a new comment |
| `update_comment` | Edit or moderate a comment |
| `delete_comment` | Delete a comment |

### Categories
| Tool | Description |
|------|-------------|
| `list_categories` | List all categories |
| `create_category` | Create a new category |
| `update_category` | Rename/edit a category |
| `delete_category` | Delete a category |

### Tags
| Tool | Description |
|------|-------------|
| `list_tags` | List all tags |
| `create_tag` | Create a new tag |
| `update_tag` | Edit a tag |
| `delete_tag` | Delete a tag |

### Users
| Tool | Description |
|------|-------------|
| `list_users` | List site users |
| `get_user` | Get user details |
| `get_me` | See your own profile |

### Site Info & Settings
| Tool | Description |
|------|-------------|
| `get_site_info` | General site information |
| `get_site_settings` | All WordPress settings |
| `update_site_settings` | Change site settings |

### Plugins
| Tool | Description |
|------|-------------|
| `list_plugins` | List installed plugins |
| `activate_plugin` | Activate a plugin |
| `deactivate_plugin` | Deactivate a plugin |

### Themes
| Tool | Description |
|------|-------------|
| `list_themes` | List installed themes |
| `activate_theme` | Switch active theme |

### Menus
| Tool | Description |
|------|-------------|
| `list_menus` | List navigation menus |
| `get_menu_items` | Get items in a menu |

### WooCommerce
| Tool | Description |
|------|-------------|
| `woo_list_products` | List products |
| `woo_get_product` | Get product details |
| `woo_create_product` | Create a product |
| `woo_update_product` | Update a product |
| `woo_list_orders` | List orders |
| `woo_get_order` | Get order details |
| `woo_update_order_status` | Change order status |

</details>

---

## Requirements

| What | Minimum Version | How to Check |
|------|----------------|-------------|
| **WordPress** | 5.6+ (Dec 2020) | WordPress Admin > Dashboard > Updates |
| **Node.js** | 18+ | Run `node --version` in terminal |
| **WordPress account** | Administrator role | You should be an admin on your site |

---

## Where Are Things Stored?

| What | Where | Purpose |
|------|-------|---------|
| MCP server code | Downloaded automatically by `npx` from npm | The program itself |
| Your site credentials | `~/.easy-wordpress-mcp/config.json` | Saved locally on YOUR computer only |
| MCP registration | Claude's settings (managed by `claude mcp add`) | Tells Claude this MCP exists |

**Nothing is stored on your WordPress site.** No plugins, no files, no database entries.

Your credentials never leave your computer — they go directly from your machine to your WordPress site via HTTPS.

---

## Troubleshooting

### "I don't see Application Passwords in my WordPress profile"

This feature has been built into WordPress since version 5.6 (December 2020). If you don't see it:

- **Check your WordPress version:** Go to Dashboard > Updates. If it's below 5.6, update WordPress first.
- **Hosting provider:** Some hosts (like WP Engine or managed WordPress hosts) may disable Application Passwords. Contact your host to enable it.
- **Security plugins:** Plugins like Wordfence, iThemes Security, or Sucuri can hide this section. Check their settings for "Application Passwords" or "REST API" options.
- **Your site must use HTTPS:** Application Passwords are disabled on sites without SSL. If your URL starts with `http://` instead of `https://`, you need to set up SSL first (most hosts offer free SSL).

### "Authentication failed"

- You need an **Application Password**, NOT your regular WordPress login password. They are different.
- The Application Password includes spaces — copy the **entire** thing: `ABCD 1234 EFGH 5678 IJKL 9012`
- Make sure your **username** is correct (it's the one you type when logging into WordPress).
- Go to Users > Profile and check that the Application Password is still listed (it may have been revoked).

### "Could not reach your site"

- Make sure you included `https://` at the beginning of your URL.
- Visit your site in a browser to confirm it's online.
- If your site is on localhost or behind a VPN/firewall, Claude can still reach it if your computer can.

### "Permission denied"

- You need an **Administrator** WordPress account for full access.
- Editor accounts can manage posts and pages but cannot manage plugins, themes, or settings.

### "WooCommerce tools not working"

- WooCommerce must be **installed and activated** on your WordPress site.
- The WooCommerce REST API is enabled by default. If it was disabled, go to WooCommerce > Settings > Advanced > REST API.

### "npx: command not found"

- This means Node.js isn't installed. Download it from [nodejs.org](https://nodejs.org/) (LTS version).
- After installing, close and reopen your terminal, then try again.

### "I want to disconnect / start over"

- Tell Claude: *"Remove my WordPress site connection"*
- Or manually delete the file: `~/.easy-wordpress-mcp/config.json`
- To remove the MCP from Claude entirely: `claude mcp remove easy-wordpress-mcp`

---

## Privacy & Security

- Your credentials are stored **only on your computer** at `~/.easy-wordpress-mcp/config.json`
- **No data is sent to any third party.** Communication goes directly: Your Computer → Your WordPress Site
- Application Passwords can be **revoked at any time** from your WordPress profile (Users > Profile > Application Passwords > Revoke)
- Your regular WordPress password is never used or stored
- We strongly recommend using **HTTPS** on your WordPress site

---

## Uninstalling

1. Remove from Claude: `claude mcp remove easy-wordpress-mcp`
2. Delete saved credentials: `rm -rf ~/.easy-wordpress-mcp`
3. (Optional) Revoke the Application Password in WordPress: Users > Profile > Application Passwords > Revoke

---

## License

MIT License. Built and maintained by [vincentquero](https://github.com/vincentquero).
