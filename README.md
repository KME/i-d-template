# Internet Draft Template Repository

The contents of this repository can be used to get started with a new internet
draft.

## Getting Started

This all assumes that you have an [account](https://github.com/join) with
GitHub.

### Working Group Setup

Make a [new organization](https://github.com/organizations/new) for your working
group.  This guide will use the name `unicorn-wg` for your working group.

### New Draft Setup

[Make a new repository](https://github.com/new).  This guide will use the
name name `unicorn-protocol` here.

When prompted, select the option to initialize the repository with a README.

Clone that repository:
```sh
$ git clone https://github.com/unicorn-wg/unicorn-protocol.git
```
Copy the contents of this respository in:
```sh
$ cd unicorn-protocol
$ git remote add i-d-template https://github.com/martinthomson/i-d-template.git
$ git fetch i-d-template
$ git reset i-d-template/master --hard
$ git push -f origin master
```
(Note that git reset is a sharp tool, especially with the `--hard` option.
So is push with the `-f` option.)

Choose whether you want to use markdown, outline, or xml as your input form.
If you already have a draft, then that decision is already made for you.

Make a draft file.  The name of the file is important, make it match the name of
your draft.  You can take a copy of the template files if you are starting from
scratch.

Edit the draft so that it has both a title and the correct name.  This template
uses the `-latest` suffix in place of the usual number ('-00', or '-08').  The
number is generated automatically when you use `make submit`.

In XML, you should have something like:
```xml
<rfc docName="draft-ietf-unicorn-protocol-latest"
     ... other attributes ...>
  <front>
    <title abbrev="Unicorns!!!">The Unicorn Protocol</title>
```

Markdown is similar:
```yaml
docname: draft-ietf-unicorn-protocol-latest
title: The Unicorn Protocol
```

The makefile has a `setup` target that you can now run.
```sh
$ make setup
```

This removes unused templates, updates `README.md` with guesses about your
draft, sets up a `gh-pages` branch for your editor's copy.

Check that everything looks OK, then push.
```sh
$ git push
```


### Updating The Editor's Copy

You can maintain `gh-pages` manually by running the following command
occasionally.

```sh
$ make ghpages
```

Or, you can setup an automatic commit hook using Travis.


### Automatic Update for Editor's Copy

This requires that you sign in with [Travis](https://travis-ci.org/).

First enable builds for the new repository on the Travis site.  (Hit the button
with a '+' on it once you are logged in.)  Note that Travis only synchronizes
repositories with GitHub once a day, so you might have to force a refresh.

Then, you need to get yourself a [new GitHub application
token](https://github.com/settings/tokens/new).  The application token only
needs the `public_repo` privilege.  This will let it push updates to your
`gh-pages` branch.

You can add environment variables using the Travis interface.  Include a
variable with the name `GH_TOKEN` and the value of your newly-created
application token.  Leave the value of "Display value in build log" disabled, or
you will be making your token public.

**WARNING**: You might want to use a dummy account for application tokens to
minimize any problems from accidental leaks of your key.

Once you enable pushes from Travis, be very careful merging pull requests that
alter `.travis.yml` or `Makefile`.  Those files can cause the value of the token
to be published for all to see.  You don't want that to happen.  Even though
tokens can be revoked easily, discovering a leak might take some time.  Only
pushes to the main repository will be able to see the token, so don't worry
about pull requests.

As a side benefit, Travis will now also check pull requests for errors, letting
you know if things didn't work out so that you don't merge anything suspect.


## Updating the Makefile

Occasionally improvements and changes are made to the Makefile or the support
files in this repository.  The `update` make target looks after the update of
the core files.

```sh
$ make update
$ git commit
```

This script is cunning enough to handle merging any simple changes that you
might have made to the Makefile yourself, such as adding targets.  It doesn't
deal well with more substantial changes that might introduce conflicts, sorry.


## Submitting Drafts

See `SUBMITTING.md`.
