# Scrimba Meme Generator project with React & NodeJs

## Screenshot
![memegenerator-screenshot](https://user-images.githubusercontent.com/109000703/191742981-82cde79e-5b62-42e7-99a7-4f3b65447900.png)


## Built With
- HTML5
- CSS / Flexbox
- React.js
- Node.js
- CSS Grid

## What I Learned
- How to use Hooks 
1. State  
```
const [meme, setMeme] = React.useState({
        topText: "",
        bottomText: "",
        randomImage: "http://i.imgflip.com/1bij.jpg"
});
```
2. Side Effects & Fetch
```
const [allMemes, setAllMemes] = React.useState([])

  React.useEffect(() => {
      fetch("https://api.imgflip.com/get_memes")
      .then(res => res.json())
      .then(data => setAllMemes(data.data.memes))
}, []);
```
- Conditional Rendering  
```
function getMemeImage() {
        const randomNumber = Math.floor(Math.random() * allMemes.length)
        const url = allMemes[randomNumber].url
        setMeme(prevMeme => ({
            ...prevMeme,
            randomImage: url
        }));
}
```

