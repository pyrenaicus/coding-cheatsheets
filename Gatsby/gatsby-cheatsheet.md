# installing Gatsby

`npm install -g gatsby-cli`
installing globally, one time only

# creating a new gatsby project

there are different ways, easiest one is:
`npm init gatsby`and follow the prompt, it will ask for the name of the directory where gatsby project will be created, and other stuff

## creating a new gatsby project, step by step

Create a directory for the project and `cd`into it.

Initialize package: `npm init -y`

install React and Gatsby `npm i gatsby react react-dom`

Open `package.json` and add following scripts:

```js
  "scripts": {
    "develop": "gatsby develop",
    "start": "gatsby develop",
    "build": "gatsby build",
    "serve": "gatsby serve",
    "clean": "gatsby clean"
  },
```

Create a `gatsby-config.js` file and add:

```js
module.exports = {
  plugins: [],
};
```

Create a `gatsby-browser.js` and `gatsby-node.js` files, leave empty by now.

Create a `src` directory.

Initialize git `git init` and create a `.gitignore` file with contents:

```
node_modules/
.cache/
public
```

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

## working with MDX

```
npm i gatsby-source-filesystem gatsby-plugin-page-creator gatsby-plugin-mdx @mdx-js/mdx@v1 @mdx-js/react@v1
```

`gatsby-plugin-page-creator` is not required for MDX, we'll use it later to create pages from a folder full of MDX files.

# provide site-wide metadata

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

# pageContext

Get's passed from `gatsby-node.js`.

# creating pages programatically

# navigate to pages programmatically

for example, after a form submission. Use the `navigate` helper function.

```js
import { navigate } from 'gatsby'

export default function Page() => {
  const navigateTo = () => {
    navigate('/some-page')
  }
  return (
    <div>
      <button onClick={() => navigateTo()}>Go to some page</button>
    </div>
  )
}
```

```js
const Form = () => (
  <form
    onSubmit={(evt) => {
      evt.preventDefault();
      navigate("/thank-you");
    }}
  >
    // form inputs go here
  </form>
);
```
