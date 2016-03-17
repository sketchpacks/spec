# sketchpack.json specification

`sketchpack.json` is used for configuring packages that can be used as a dependency of another package. This is similar to Node’s `package.json` or Ruby’s `Gemfile`.

<pre><code>{
  <a href="#name">"name"</a>: "greatest-plugin",
  <a href="#owner">"owner"</a>: "owner": {
    "name": "John Doe",
    "email": "john@doe.com",
    "homepage": "http://johndoe.com"
  },
  <a href="#description">"description"</a>: "This is only a tribute to the greatest plugin in the world",
  <a href="#repository">"repository"</a>: {
    "type": "git",
    "url": "https://github.com/tenaciousd/greatest-plugin"
  },
  <a href="#keywords">"keywords"</a>: [
    "artboart",
    "duplication",
    "easy"
  ]
}</code></pre>

## name

**Required**

Type: `String`

The name of the plugin as stored in the registry.

* Must be unique.
* Should be slug style for simplicity, consistency and compatibility. Example: `unicorn-cake`
* Lowercase, a-z, can contain digits, 0-9, can contain dash or dot but not start/end with them.
* Consecutive dashes or dots not allowed.
* 50 characters or less.


### description

*Recommended*

Type: `String`

Any character. Max 140.

Help users identify and search for your package with a brief description. Describe what your package does, rather than what it's made of. Will be displayed in search/lookup results on the CLI and the website that can be used to search for packages.


### keywords

*Recommended*

Type: `Array` of `String`

Same format requirements as [name](#name).

Used for search by keyword. Helps make your package easier to discover without people needing to know its name.


### owner

Type: `Object`

A list of people that authored the contents of the package.

```json
"owner": {
  "name": "John Doe",
  "email": "john@doe.com",
  "homepage": "http://johndoe.com"
}
```

### homepage

Type: `String`

URL to learn more about the package. Falls back to GitHub project if not specified and it’s a GitHub endpoint.


### repository

Type: `Object`

The repository in which the source code can be found.

```json
"repository": {
  "type": "git",
  "url": "https://github.com/foo/bar"
}
```

Currently only plugins hosted on Github are supported. Bitbucket and others may be supported in the future with your help.
