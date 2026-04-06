# Alternative Docs Domain Deploy for Multi-Scrobbler

[Multi-Scrobbler](https://github.com/FoxxMD/multi-scrobbler) has historically used [foxxmd.github.io/multi-scrobbler](https://foxxmd.github.io/multi-scrobbler/) for docs. Unfortunately, migrating to a custom domain is not seamless WRT SEO changes:

* Google search console does not allow moving domain address when you are not the owner of the TLD (github.io)
* Although switching to a custom domain for gh pages will do a redirect, google search console treats this as an invalid page and de-indexes it

Effectively, moving to a custom domain wipes all page ranking/SEO for the gh pages subdomain path. :(

The workaround is deploy to both domains simultaneously and let the old path-docs unwind over time:

* Deploy pages to a custom domain using a **different** repository.
* Switch all URLs in docs/repo to use the new domain
* Wait (indefinitely) for page ranking/SEO for new domain to (hopefully) get to parity with old path-docs
* Eventually, switch main repo gh pages to use custom domain

___

This repository deploys docs with the same behavior as the main repository: on manual dispatch or on [Release/Tag](https://github.com/FoxxMD/multi-scrobbler/releases) creation (new version) for MS. The docs are exactly the same as you would find at foxxmd.github.io/multi-scrobbler.