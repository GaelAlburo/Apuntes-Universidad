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
