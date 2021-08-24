# dynamically generate OpenGraph images from Hugo and Netlify

## goal

Context: I like how OpenGraph images look in link unfurls, for example on social media and in chat apps, but I don't like manually creating a new image for each blog post I write.

Goal: Figure out how to generate OpenGraph images dynamically based on page/post metadata!

[https://twitter.com/shelbyspees/status/1395117343487893505](https://twitter.com/shelbyspees/status/1395117343487893505)

## resources

what is OpenGraph?

[Open Graph protocol](https://ogp.me/)

ways to check image unfurls:

[Meta Tags - Preview, Edit and Generate](https://metatags.io/)

- instructions for other platforms

    video:

    [Cloudinary Academy | Online Training for API and DAM Users](https://training.cloudinary.com/learn/video/devjams-episode-3-creating-social-sharing-images-with-cloudinary-and-svelte)

    tutorials:

    [Automatic Social Share Images](https://www.ryanfiller.com/blog/automatic-social-share-images)

    [Generating Dynamic Open Graph Images with Azure Functions](https://thecloudblog.net/lab/generating-dynamic-open-graph-images-with-azure-functions/)

    couldn't figure out how to get this one running locally as a node app instead of setting up vercel credentials

    [vercel/og-image](https://github.com/vercel/og-image)

### netlify build

for a gatsby site

note: gatsby is javascript but it basically does what hugo does

[Generating Open Graph images during Netlify deploy](https://gersom.nl/post/og-images-on-netlify/)

[gersomvg/gersom.nl](https://github.com/gersomvg/gersom.nl/tree/main/src/scripts/generate-og-images)

can trigger during build instead of calling out to functions, but it requires taking a screenshot of each the dynamically-generated image and saving it to a static directory:

> 5. Making a screenshot and saving it to /public
6. Repeating steps 4 and 5 for all posts.

this happens at build time, and I could figure out how to use images from the cache if there aren't any changes

### netlify functions

do I even need this?

for things that change between deploys, or to over-engineer my own OpenGraph image cards

[Playground - Netlify Functions](https://functions.netlify.com/playground/)

## notes

technologies involved:

- Netlify running the code
- HTML(?) template for OpenGraph image
- OpenGraph-compatible metadata tags
- JavaScript(?) to plug the metadata into the template? I'll do this in Python if they let me

poc: 

[shelbyspees/og-script](https://github.com/shelbyspees/og-script)

on my actual website:

[shelbyspees/website](https://github.com/shelbyspees/website/tree/main/netlify/functions)