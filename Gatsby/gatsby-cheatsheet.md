# installing Gatsby

`npm install -g gatsby-cli`
installing globally, one time only

# creating a new gatsby project

there are different ways, easiest one is:
`npm init gatsby`and follow the prompt, it will ask for the name of the directory where gatsby project will be created, and other stuff

# running the site locally

`npm run develop` will run a development server and default to port 8000, `http://localhost:8000``

# working with markdown files

We have two choices: working with plain MD files, or working with MDX, markdown with embedded React JSX components.

## working with MD

We'll need to install a couple of plugins:

```
npm install gatsby-source-filesystem gatsby-transformer-remark
```

After installing, add them to `plugins` array in `gatsby-config.js`

## provide site-wide metadata

such as `siteUrl`, `title`, `description`... whatever small piece of data we want to acces site wide.

In `gatsby-config.js` add a `siteMetadata` object to `module.exports`, such as:

```js
module.exports = {
  siteMetadata: {
    title: 'My Site',
    description: 'A blog about all things JS',
    siteUrl: 'https://www.mysite.dev',
  },
  plugins: [
    ...
  ],
}
```
