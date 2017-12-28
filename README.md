# Blog

## Context

Github pages just publishes static content on *.github.io subdomain. Generation happens
 at user's computer then `git push`. There must be HTML generation software.

Github recommends Jekyll templating engine (requires Ruby install). I have chosen to user Hexo
 because it uses node.js and I have it.

## Branches

 * source: that's what Hexo uses
 * master: generated blog html and assets.

## Initial checkout

TBD

## Maintaining the blog

The source posts are Markdown files under source/. So first I am editing my_new_post.md in there. Then:
 * `hexo generate` -- creates / deletes / changes files in public/ dir;
 * `hexo server` -- starts local web server at http://localhost:4000/index.html to review how it'll look like;
 * I copy public/ into git-working-dir/ and `git gui` in there (add, commit, push);
 * View changes at https://vkovalchuk.github.io/

## Plans

Later I am going to configure hexo-generation-1/blog/_config.yml "deploy: type: git".

Hexo uses themes. Those are not Jekyll themes. To change, in \_config.yml specify "theme: bootstrap-blog"
 and clone theme repo under themes/ dir.
