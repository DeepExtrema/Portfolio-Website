# DNS Configuration Guide for GitHub Pages

This document explains how to configure DNS records for the custom domain `taimoorawan.dev` to work with GitHub Pages.

## Current Configuration

- **Custom Domain**: taimoorawan.dev (configured in CNAME file)
- **GitHub Pages URL**: https://deepextrema.github.io/Portfolio-Website/

## Required DNS Configuration

To fix the "Domain does not resolve to the GitHub Pages server" error, you need to configure DNS records at your domain registrar.

### For Apex Domain (taimoorawan.dev)

Add the following **A records** at your DNS provider:

```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

### Optional: For www Subdomain

If you also want www.taimoorawan.dev to work, add a CNAME record:

```
Type: CNAME
Name: www
Value: deepextrema.github.io
```

## Verification Steps

1. Configure the DNS records at your domain registrar
2. Wait for DNS propagation (can take up to 48 hours, but usually much faster)
3. Verify DNS configuration using: `dig taimoorawan.dev +noall +answer`
4. Check GitHub Pages settings in repository settings
5. Ensure HTTPS is enabled in GitHub Pages settings (may take a few minutes after DNS propagates)

## References

- [GitHub Pages Custom Domain Documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
