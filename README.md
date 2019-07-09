# vue-elements
Creating custom elements with your existing Vue App or Component

## Getting Started
```
git clone https://github.com/aelbore/vue-elements.git
npm install
```

## Bundle to `custom elements`
```
npm run build.card.wc
```

## Update `./dist/demo.html`
- lit-html (this didnt work)
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Vue Elements</title>
    <script src="https://unpkg.com/vue"></script>
    <script src="./ar-card.js"></script>
  </head>
  <body>
    
    <div id="cards"></div>

    <script type="module">
      import { render, html } from 'https://unpkg.com/lit-html@1.1.0/lit-html.js'
    
      const profiles = [{
          name: "Jane Doe",
          profession: "Framework Developer",
          motto: "I never wanted to be famous, I wanted to be great.",
          photo: "https://pymwoqn637.codesandbox.io/default.png"
        },
        {
          name: "Kurtis Weissnat",
          profession: "Developer",
          motto: "When in doubt, iterate faster!",
          photo: "https://pymwoqn637.codesandbox.io/default.png"
        }
      ]

      const cards = () => {
        return html `${profiles.map(profile => {
          return html `<ar-card .profile=${profile}></ar-card>`
        })}`
      }

      render(cards(), document.getElementById('cards'))
    </script>

  </body>
  </html>

  ``` 
- raw javascript (this works)
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Vue Elements</title>
    <script src="https://unpkg.com/vue"></script>
    <script src="./ar-card.js"></script>
  </head>
  <body>
    
    <div id="cards"></div>

    <script>
      const profiles = [{
          name: "Jane Doe",
          profession: "Framework Developer",
          motto: "I never wanted to be famous, I wanted to be great.",
          photo: "https://pymwoqn637.codesandbox.io/default.png"
        },
        {
          name: "Kurtis Weissnat",
          profession: "Developer",
          motto: "When in doubt, iterate faster!",
          photo: "https://pymwoqn637.codesandbox.io/default.png"
        }
      ]

      const root = document.getElementById('cards')
      
      profiles.forEach(profile => {
        const card = document.createElement('ar-card')
        root.appendChild(card)

        card.profile = { ...profile }
      })
    </script>

  </body>
  </html>
  ```  
 
### Run demo
```
http-server ./dist

browse to http://localhost:8080/demo.html
```
