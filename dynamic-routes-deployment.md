# Dynamic Routes

* In dynamic routes page path depends on external data.
* Next.js allows you to statically generate pages with paths that depend on external data enabling dynamic URLS.
* To create dynamic routes we create a file inside the pages/posts folder (on the example case). The file start with `[` and end with `]` as in `[id].js` 
* Export an async function called `getStaticPaths` from the route page.
* We add a function at the end of the posts file to return a list `an array of objects` of file names with each object with the `params` keyword as in the example below:
```
export function getAllPostIds() {
  const fileNames = fs.readdirSync(postsDirectory)

  // Returns an array that looks like this:
  // [
  //   {
  //     params: {
  //       id: 'ssg-ssr'
  //     }
  //   },
  //   {
  //     params: {
  //       id: 'pre-rendering'
  //     }
  //   }
  // ]
  return fileNames.map(fileName => {
    return {
      params: {
        id: fileName.replace(/\.md$/, '')
      }
    }
  })
}
```
* Import the `getAllPostIds` function as below:
```
import { getAllPostIds } from '../../lib/posts'

export async function getStaticPaths() {
  const paths = getAllPostIds()
  return {
    paths,
    fallback: false
  }
}
```
* To fetch the posts with the give `id` we add a `getPostData` function to our `lib/posts.js`

To render Markdown we install the `remark` library `npm install remark remark-html` and then add 
```
import { remark } from 'remark'
import html from 'remark-html'
``` 
to the posts.js file.

### Deploying Next.js App to Vercel/production

* Vercel is a serverless platform developed by the creators of Next.js.
* To use Vercel:
    * create user account
    * install Vercel for GitHub and give it access to your repos
    * import your repo from GitHub to Vercel
    * Vercel automatically dectects Next.js apps
    

<br />

### References

[Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)

[Deploying Your Next.js App](https://nextjs.org/learn/basics/deploying-nextjs-app)


<br />

## [<-- Back to home](README.md)
