Hepimizin Matematik derslerinden bildiği üzere Dairenin Alanı = π x r2 şeklinde hesaplanır. Node.JS Javascript çalışma ortamında yarıçap değerini konsoldan parametre olarak girerek alanı bulmaya çalışacağız. Konsol çıktısı: Yarıçapı (Yarıçap) olan dairenin alanı: (Alan) şeklinde olmalıdır.
```JS
// process.argv ile komut satırı argümanlarını alıyoruz
const args = process.argv;

// İkinci argüman yarıçap olmalı
const radius = parseFloat(args[2]);

// Yarıçapın geçerli bir sayı olup olmadığını kontrol etme
if (isNaN(radius) || radius <= 0) {
    console.log('Lütfen geçerli bir yarıçap değeri girin.');
} else {
    // Dairenin alanını hesaplama
    const area = Math.PI * Math.pow(radius, 2);
    
    // Sonucu konsola yazdırma
    console.log(`Yarıçapı ${radius} olan dairenin alanı: ${area.toFixed(2)}`);
}
```
