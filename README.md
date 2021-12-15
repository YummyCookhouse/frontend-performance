# Frontend performance assertion and optimisation

### Background
Not so long ago, when we talk about a performance issue, it's more likely related to the backend.
However, with fast development of web frontend technologies and more user-friendly modern UX design,
for example, frontend-backend separation, SPA (single page application), fancy animation effects and infinite scrolling, frontend
projects face to more performance challenges than ever before.

### Why is it happening?
Some typical reasons:

- Presentation layer is being moved from backend to frontend

  Unlike SSR web applications (i.e: JSP), backend services are now aiming to provide pure data
  instead of returning mixed content of HTML and data to browser. So the frontend applications need
  to run more javascript to generate HTML and render web page in browser.

- Modern frontend applications bundles all pages/module together

    
- Higher expectation on user experience makes DOM structure becomes more complicated

  Since web 2.0, AJAX gives user more flexibilities on interacting with user interface,
  but it also makes DOM structure become more complicate and larger DOM tree size. For example, with async loading pages,
  infinite scrolling becomes more popular, and all content will be rendered in a same page. Furthermore, 
  more requirements on animation and DND operation also bring more challenges on rendering performance.
  
- CSR exposes more memory leak issues in browser
  
  Memory leak in browser usually not a problem in traditional SSR web application because the browser memory will be refreshed
  during page transition, even the program has memory leak issue, the leaked memory won't be that huge. However, memory leak would be
  more critical in SPA because the leaked memory can be accumulated during page transition and detached node could exist in memory util
  hot reload or close browser.

### Types of frontend performance issues

- Loading performance
- Render performance
- Memory usage performance