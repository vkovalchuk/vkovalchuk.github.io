---
title: "Secrets Vault: what we did not see earlier"
date: 2018-01-12 12:54:11
tags:
 - DevOps
 - rant
---
Couple years ago I have heard about Hashicorp Vault for secrets storage. "So you don't store them in files." Of course Vault stores them in files; it just uses network protocol instead of file API. How it's different from, let's say, using NFS server? I had to look closer and found: lease and renewal.

This is like file ACL with expiry dates. Never heard of this idea; we all _feel_ that files are for storage and the storage is forever. Use case of secrets/passwords is different: they must be volatile. But the concept of temporary persistent file is not automated into file systems. As well as expiring file ACLs.

OTOH expiring secrets (leases/renewals) means human attention; how this renewal gets approved? Aren't these renewal similar to using OTP / 2FA?
