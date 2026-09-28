# Mitcham Properties Ltd website

A standalone static website for GitHub and Cloudflare Pages. No ChatGPT hosting or build tools are required.

## Deploy with GitHub and Cloudflare Pages

1. Create a new GitHub repository and upload the contents of this folder (`public/` and this `README.md`) to its `main` branch. If using GitHub's web upload, extract the ZIP first and upload the files and folder rather than the ZIP itself.
2. In Cloudflare, open **Workers & Pages → Create application → Pages → Import an existing Git repository**. Connect the new GitHub repository.
3. Use these build settings:
   - Production branch: `main`
   - Framework preset: `None`
   - Build command: `exit 0`
   - Build output directory: `public`
4. Deploy and check the assigned `*.pages.dev` address.
5. In that Pages project, open **Custom domains → Set up a domain**, enter `mitchamproperties.co.uk`, and follow Cloudflare's DNS prompt. The domain must be a zone in the same Cloudflare account. Cloudflare normally creates the required CNAME for an apex domain whose nameservers are already on Cloudflare.

Do not use the earlier A/TXT records for ChatGPT Sites. If you added those records, remove the two apex A records pointing to `162.159.143.30` and `172.66.3.26`, and the `_openai-site-verification` and `_cf-custom-hostname` TXT records before connecting this Pages project. Preserve unrelated DNS records, especially mail records.

## Editing

Edit the HTML files and `styles.css` under `public/`, then push to GitHub. Cloudflare Pages redeploys the connected branch.

The Rent and Sell listings are labeled samples with illustrative photos and prices. The Contact form opens the visitor's email app with the message prepared; it does not send from a server. The contact email and phone links work directly.

References: https://developers.cloudflare.com/pages/framework-guides/deploy-anything/ and https://developers.cloudflare.com/pages/configuration/custom-domains/
