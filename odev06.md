Koa.js ile web sunucumuzu yazalım.

- koa paketini indirelim.
- index, hakkimda ve iletisim sayfaları oluşturalım.
- Sayfalara içerik olarak xxx sayfasına hoşgeldiniz şeklinde h1 başlıkları yazdıralım.
- port numarası olarak 3000'i kullanalım.
```JS
const Koa = require('koa');
const app = new Koa();

app.use(async ctx => {
    switch (ctx.path) {
        case '/':
            ctx.status = 200;
            ctx.body = '<h1>INDEX SAYFASINA HOSGELDINIZ</h1>';
            break;
        case '/hakkimda':
            ctx.status = 200;
            ctx.body = '<h1>HAKKIMDA SAYFASINA HOSGELDINIZ</h1>';
            break;
        case '/iletisim':
            ctx.status = 200;
            ctx.body = '<h1>ILETISIM SAYFASINA HOSGELDINIZ</h1>';
            break;
        default:
            ctx.status = 404;
            ctx.body = '<h1>404 SAYFA BULUNAMADI</h1>';
    }
});

const port = 3000;

app.listen(port, () => {
    console.log(`Sunucu port ${port} üzerinde çalışmaya başladı.`);
});
```
