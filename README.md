# ofc

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
### General description:
The main App compone is the parent to the index. The index contains to HTTP request, one which is called upon search
and another which only gets called when certain conditions apply. 
Atemplate then generates certain UI elements according to criteria which eventually determin but the API responces. 
Upon loading the app an SVG logo will animate. Ideally this item would be it's own component,
however due to this being my first time handling svg animation, my efforts in creating a seperate component did not succeed.
I'm am happy with the final results tho.

When the search ends with certain criteria being filled, a card with the player details will generat. Said card will disappear when
user triggers a new search.

### Suggested test cases

1. search Fabio/fabio. Card should be generated
2. search FrancescofFrancesco. snackbar will popup with message player not found
3. search Giorgio/giorgio. snackbar will popup with message player is inactive
4. search any string, snackbar will popup with message player not found
5. trigger the search with clicking the button "go" or by pressing the "enter"key
6. on load - logo should animate
7. when hovering over go button - button should animate
8. changing viewport size will trigger layout changes which should not break the ui.

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
