# 🛟 data_api_vue_fetch

Simple data fetching from API to Vue application using the JSON Placeholder API to render todos.

## ⚙️ Code

1. In order to get the data from the API, the fetch() API was used. This takes one argument: the API url. 

```
fetch("https://jsonplaceholder.typicode.com/todos/")
      .then((response) => response.json())
      .then((json) => (this.todos = json));
```

2. Then, the data fetched from the API is converted to JSON and then assigned to the todos property in data() for the component. 

```
.catch(error => {console.log("Error while fetching data: ", error)})
```

3. Because there can always be possibility for errors while fetching data from an API, there is a catch to log an error in case the request has failed.

```
<div v-for="(item, index) in todos" :key="index">
      <ul>
        <section>
          <h4>{{ item.userId }}</h4>
          <h4>{{ item.title }}</h4>
        </section>
      </ul>
```

4. The data is then rendered in the component through a v-for since the todos property in data() is an array and must be iterated in order to be displayed in the child elements of the parent element (div).

<img width="400" alt="Screenshot 2022-10-27 at 13 50 00" src="https://user-images.githubusercontent.com/72168158/198289012-a875af97-d3e2-4621-a442-9ab3d82a483e.png">

4. The UI looks as below 👆

🎉🎉🎉

## Resources

JSON Placeholder API: https://jsonplaceholder.typicode.com/

Fetch API: https://www.koderhq.com/tutorial/vue/http-fetch/

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

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
