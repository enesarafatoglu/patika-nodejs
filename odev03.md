Daire alan : circleArea ve daire çevre : circleCircumference fonksiyonları içeren ve consola sonuçları yazdıran circle.js dosyası oluşturunuz.
module.exports yöntemi ile fonksiyonları oluştururken export ediniz.
require ve object destructing kullanarak index.js dosyasında yarıçap (r) 5 olacak şekilde ekran çıktısını alınız.
```JS
//circle.js
function circleArea(radius) {
    return Math.PI * Math.pow(radius, 2);
}

function circleCircumference(radius) {
    return 2 * Math.PI * radius;
}


module.exports = {
    circleArea,
    circleCircumference
};
```

```JS
//index.js
const {circleArea, circleCircumference} = require('./circle');

const radius = 5;

console.log(`Dairenin alanı: ${circleArea(radius).toFixed(2)}`);
console.log(`Dairenin çevresi: ${circleCircumference(radius).toFixed(2)}`);
```
