```js
<body>
    <ul id="ul">
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
    </ul>
    <script>
        let ul = document.getElementById('ul')
        ul.addEventListener('click',ulClick)
        function ulClick(e) {
            let event = e
            let target = event.target;
            if(target.nodeName.toLowerCase() === 'li') {
                console.log(target.innerHTML);
            }
        }
    </script>
</body>
```

