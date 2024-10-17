It's a React framework

React is a programming language, with its benefits of watching changes of Web UI in real time (messenger, ig, fb) (writing in real time)

NextJS offers advanced funciotnalities of React
- Server side rendering (SSR)
	- Client doesnt load the graphics, client doesnt need much connection power
- Generating static pages (SSG)
	- A page that doesnt have a connection with a back end
- Incremental Static Regeneration (ISR)
	- Updates static pages according the demand
- Routing systems are based on directories (NextJS)
	- With React we have to code them manually each route (`/home`, `/`, etc.)

React develops front
NextJS can develop front and back

> But we're gonna write the 

___

REact
From /frontend/examples
TO create a new react project: npx create-next-app@latest bookshelf
ESLint: yes > linter
alias: no
tailwind: yes
src/directory: no
app router: yes
we enter bookshelf (cd)
we run the app: npm run dev
structure:
- app/page


- public: images
- app/styles: CSS
- app/components
- app/constants
then we delete the css files, logos and images
after we rename two files: layout.js to layout.jsx and page.js to page.jsx
ON LAYOUR.JSX:
	delete the global.css
	METADATA:
	Modify title: Bookshelf
	also the description: Book management app
	
ON PAGE.JSX:	on home() we delete the return and return react empty object
we create contact/page.jsx and about/page.jsx inside the /app directory
on both os these: return (`<div><h1>About</h1></div>`)
we can use LInk component: <LInk></>

MATERIAL UI
stylized components and ready to use
we install MUI with the onw on thei web page
and install also mui icons: on web page too
we create /styles/global-theme.jsx

inside it:
	"use client"; (we tell next.js this is front)
	import (createTheme) from "@mui/....."
	export const theme = createTheme({
		palette: {
			primary: (
				main: "#005682"
			),
			secondary: (
				main: "#dc004e"
			)
		},
		typography : {
			fontFamily: "Arial, san-serif"
		}
	})
	
ON LAUYOUT.JSX:
WE ADD <ThemeProvider theme=(theme)><CssBaseline /> {children}</Theme Provier>
___
# Material UI

## Components

Create new file. Inside /folders/app-bar-global.jsx. This inside /app

```jsx
import {AutoStoriesIcon} from "@mui/icons-material/Auostories";

export default function AppbarGlobal() {
	const navItems = {
		{label: "Home", href: "/"},
		{label: "About", href: "/about"},
		{label: "Contact", href: "/contact"}
	};
	
	return (
		<AppBar position="static" sx={{ mb: 4 }}>
			<Toolbar>
				<AutoStoriesIcon sx={{display: {xs:"flex"}, mr: 1 }}/>
				<Typography variant="h6" noWrap component={Link} href="/" 
					sx={{ display: {xs: "none", md: "flex", mr= 1},
						  fontFamily: "monospace",
						  fontWeight: 700,
						  letterSpacing: ".2rem",
						  color: "inherit",
						  textDecoration: "none" }} >		
					BookShelf
				</Typography>
				<Box sx={{ ml: "auto", display={xs:"block"} }} >
					{navItems.map( (item) => (
						<Button key={item.label} component={Link} href={item.href} color="inherit">
							{item.label}
						</Button>
					))}
				</Box>
			</Toolbar>
		</AppBar>
	);
}
```

We add AppbarGlobal inside `RootLayout` on layout.jsx. 

sx -> MUI property. Defines styles to components


___

# Good Practices

- Use of `console`
```JSX
console.log
console.warn //Normal errors taht doesnt stop the app
console.error //Critical errors that stop the app's flow
console.info //Messages for the programmer
```

- Code format `Prettier`
```bash
npm install prettier
```

linter: verify a code and give suggestions
```bash
npm install eslint-config-prettier
```

Now we have to configure the package inside our Next.js project.
Inside the `package.json` we configure two scripts:
```json
 "format": "prettier --check --ignore-path .gitignore .",
 "format:fix": "prettier --write --ignore-path .gitignore ."
```

Now when we execute `npm format` it will execute the command written.

`npm run format:fix --write` 
With the `--write` the tool will modify the tabs of the project. if we dont add it, it will only show in terminal the changes needed, it wont do them

# Deploying the app

- Through cloud
- Containers

Containerizing the app:
1. Config in `next.config.mjs`: It will tell the working directory where it will store all the files. The directory will be created in the same level as `/app`, `/public`

```jsx
/** @type {import('next').NextConfig} */
const nextConfig = {
    output: "standalone",
};

export default nextConfig;

```

3. Create a dockerfile: Create it inside the projetc

```dockerfile
FROM node:22.8.0-alpine3.20

RUN addgroup -g 1001 bookshelf && adduser -D -u 1001 -G bookshelf bookshelf

WORKDIR /app

COPY --chown=bookshelf .next/standalone ./
COPY --chown=bookshelf .next/static ./.next/static
COPY --chown=bookshelf public ./public

ENV NODE_ENV=production
ENV PORT=3000

USER bookshelf

EXPOSE 3000

HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 CMD curl --fail http://${ip -o -4 addr list | grep eth0 | awk '{print $4}'}

CMD ["node", "server.js"]
```

The CMD of the HEALTHCHECK obtains the ip of the container, since it always changes, we want to know which is it



Now we build the app
`npm run build`

When it finishes it will appear `/.next/standalone/public`

Now we actually build the image
`docker build -t bookshelf-ui:v1.0.0 .`

When we view the images, it will appear

Now we create the container
`docker run -name bookshelf-ui -d -p 3000:3000 bookshelf-ui:v1.0.0`

Now we enter the container
`docker exec -ti bookshelf-ui sh`

Inside it we do `ls -la` to view all the files
If we do `id`


Now if in our local machine we access the localhost:3000 the app will appear


`docker push __name`

We can push our container to:
- gcr -- google
- ecr - aws
- acr - azure
- quay.io - redhat

`docker login` - to login to one of the cloud services available


SOA - Service of Architecture
-> Microservices

Restful API - Type of microservice


Most of the work in backend is migrating SOA to Microservices.

FIRST PROJECT: 5 november (frontend)
SECOND PROJECT: 21 november (backend)
3 december: FINAL PROJECT
5 december: grades


documentation of projects: user manual, what is the app, how it built, commands of image, flow of the project

draw.io , lucidchart, to create the flow of the app
- could be diagram of the architecture
- sequence diagram
- mocks
- READMEs
- docstrings, comments in code (this function is to create a login)

well redacted: grammarly

no cover is needed, just well structured.