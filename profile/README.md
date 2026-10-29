<p align="center">
  <a href="https://saascustomdomains.com"><img src="logo.svg" width="72" height="72" alt="SaaS Custom Domains"></a>
</p>

<h1 align="center">SaaS Custom Domains</h1>

<p align="center">
  Let your customers use their own domains in your SaaS app. We handle the SSL certificates and the proxy.
</p>

<p align="center">
  <a href="https://saascustomdomains.com">Website</a> ·
  <a href="https://docs.saascustomdomains.com">API docs</a> ·
  <a href="https://help.saascustomdomains.com">Help center</a> ·
  <a href="https://saascustomdomains.com/blog">Guides</a>
</p>

---

SaaS Custom Domains is a managed reverse proxy for multi-tenant apps. Your customers point their domain at us, we issue and renew its TLS certificate, and we forward every request to your app with the customer's domain attached. No certificate servers, edge proxies or DNS checks to run yourself.

## How it works

1. Add your customer's domain in the dashboard or with one API call.
2. Your customer adds a CNAME record pointing to `in.saascustomdomains.com`, or to a hostname on your own domain. Root domains use two A records.
3. We verify the DNS records, issue the certificate and proxy requests to your app.

```
Browser ── shop.acme.com ──▶ SaaS Custom Domains ──▶ your app
                             (TLS certificate,      Host: app.yourapp.com
                              proxy)                X-Served-For: shop.acme.com
                                                    X-SaaS-Domains-Auth-Token: …
```

Your app reads `X-Served-For` to know which customer it's serving, and checks `X-SaaS-Domains-Auth-Token` to make sure the request came through us.

## Example apps

Each example is a small multi-tenant app built the same way: it finds the customer from the hostname, checks the proxy's auth token, adds and removes domains through our API, keeps domain status up to date with webhooks, and runs locally on `*.localhost`. Every one comes with a step-by-step guide.

| Framework | Language | Example app | Guide |
| --- | --- | --- | --- |
| Next.js | TypeScript | [custom-domains-nextjs](https://github.com/saas-custom-domains/custom-domains-nextjs) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-nextjs) |
| Nuxt | TypeScript | [custom-domains-nuxt](https://github.com/saas-custom-domains/custom-domains-nuxt) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-nuxt) |
| SvelteKit | TypeScript | [custom-domains-sveltekit](https://github.com/saas-custom-domains/custom-domains-sveltekit) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-sveltekit) |
| Express | JavaScript | [custom-domains-express](https://github.com/saas-custom-domains/custom-domains-express) | [Read the guide](https://saascustomdomains.com/blog/posts/implementing-custom-domains-for-your-saas-app-in-node-js) |
| Hono | TypeScript | [custom-domains-hono](https://github.com/saas-custom-domains/custom-domains-hono) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-hono) |
| Ruby on Rails | Ruby | [custom-domains-rails](https://github.com/saas-custom-domains/custom-domains-rails) | [Read the guide](https://saascustomdomains.com/blog/posts/best-guide-custom-domains-ruby-on-rails) |
| Django | Python | [custom-domains-django](https://github.com/saas-custom-domains/custom-domains-django) | [Read the guide](https://saascustomdomains.com/blog/posts/implement-custom-domains-in-your-django-saas-app) |
| FastAPI | Python | [custom-domains-fastapi](https://github.com/saas-custom-domains/custom-domains-fastapi) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-fastapi) |
| Laravel | PHP | [custom-domains-laravel](https://github.com/saas-custom-domains/custom-domains-laravel) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-laravel) |
| Go (net/http) | Go | [custom-domains-go](https://github.com/saas-custom-domains/custom-domains-go) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-go) |
| Phoenix | Elixir | [custom-domains-phoenix](https://github.com/saas-custom-domains/custom-domains-phoenix) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-phoenix) |
| ASP.NET Core | C# | [custom-domains-aspnetcore](https://github.com/saas-custom-domains/custom-domains-aspnetcore) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-aspnetcore) |
| Spring Boot | Java | [custom-domains-spring-boot](https://github.com/saas-custom-domains/custom-domains-spring-boot) | [Read the guide](https://saascustomdomains.com/blog/posts/custom-domains-spring-boot) |

Using something else? The [custom domains guide](https://saascustomdomains.com/blog/posts/the-ultimate-guide-to-custom-domains-for-your-saas-app) covers the parts that are the same in every stack.

## Get started

1. [Start a 7-day free trial](https://app.saascustomdomains.com/users/sign_up).
2. Follow the [quickstart](https://docs.saascustomdomains.com/quickstart) to make your first API call.
3. Pick the example for your framework above, or read [how to handle forwarded requests](https://docs.saascustomdomains.com/handling-forwarded-requests) in any stack.

Questions? Chat with us on [saascustomdomains.com](https://saascustomdomains.com).
