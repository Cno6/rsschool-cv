# Vadim Igumnov

## Contacts

- **E-mail:** vad.igumnoff@gmail.com
- **Github:** [cno6](https://github.com/Cno6)
- **Telegram:** [\@wearecno6](https://t.me/wearecno6)

## About me

I am a final year MTUCI student. I have been learning to be a Front-end Developer for a few months. I am interested in this direction, because I like the combination of programming and design. 

In my free time I read literature of different nature. I study blockchain technology.  I plan to write useful web-application on the blockchain.

Also in the future I want to learn PWA technology and write web applications in Electron framework to create my own comprehensive productivity application.

## Skills

- HTML5, CSS3
- JavaScript (ECMAScript 6)
- TypeScript
- REST
- Git
- VSCode
- Adobe Photoshop, Figma

## Code Example

The task on parsing parameters of url request.

```js
const inData = "user.name.firstname=Bob&user.name.lastname=Smith&user.favoritecolor=Light%20Blue&experiments.theme=dark";

function queryObjectify(str) {
    let result = {}
    
    let params = inData.split('&')
    params = params.map( param => param.split('=') )
    params = params.map( param => {
        param[0] = param[0].split('.')
        param[1] = param[1].replace('%20', ' ')
        return param
    } )

    for (param of params) {
        let currentObject = result
        param[0].forEach( item => { 
            if (currentObject.hasOwnProperty(item)) {
                currentObject = currentObject[item]
            } else if (item === param[0][param[0].length-1]) {
                currentObject[item] = param[1]
            } else {
                currentObject[item] = {}
                currentObject = currentObject[item]
            }
        } )
    }
    return result
}
```