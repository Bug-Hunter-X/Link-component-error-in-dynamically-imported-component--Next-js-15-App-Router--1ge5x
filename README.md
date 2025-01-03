# Next.js 15 App Router: Link Component Error in Dynamic Imports

This repository demonstrates a bug encountered when using the `next/link` component within a dynamically imported component in Next.js 15's App Router.  The issue manifests as an error during the client-side navigation, potentially related to the timing of component hydration or the resolution of the `href` property within the dynamic context.

## Steps to Reproduce

1. Clone the repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Navigate to the homepage.  Attempting to click either link will result in a client-side error.

## Solution

A potential solution is to use a suspense boundary around the dynamically imported component. This will prevent the application from crashing and provide a loading indicator while the component loads, fixing the timing issue with the `Link` component. See `bugSolution.js` for details.