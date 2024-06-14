Node.js FS Modülü kullanarak CRUD işlemleri yapacağız.

- employees.json dosyası oluşturalım ve içerisine {"name": "Employee 1 Name", "salary": 2000} verisini ekleyelim. (CREATE)
- Bu veriyi okuyalım. (READ)
- Bu veriyi güncelleyelim.
- Dosyayı silelim.


```JS
const fs = require('fs');

// DOSYA OLUSTURMA
function createFile() {
    fs.writeFile('employees.json', '{"name": "Employee 1 Name", "salary": 2000}', 'utf8', (err) => {
        if (err) {
            console.log(err);
        } else {
            console.log('JSON DOSYASI BASARILI BIR SEKILDE OLUSTURULDU');
        }
    });
}

// DOSYA OKUMA
function readFile() {
    fs.readFile('employees.json', 'utf8', (err, data) => {
        if (err) {
            console.log(err);
        } else {
            console.log(data);
            console.log('DOSYA OKUNDU');
        }
    });
}

// DOSYA GUNCELLEME
function updateFile() {
    fs.readFile('employees.json', 'utf8', (err, data) => {
        if (err) {
            console.log(err);
        } else {
            let employee = JSON.parse(data);
            employee.salary = 3000; // Güncellenmiş veri

            fs.writeFile('employees.json', JSON.stringify(employee, null, 2), 'utf8', (err) => {
                if (err) {
                    console.log(err);
                } else {
                    console.log('DOSYA GUNCELLENDI');
                }
            });
        }
    });
}

// DOSYA SILME
function deleteFile() {
    fs.rm('employees.json', (err) => {
        if (err) {
            console.log(err);
        } else {
            console.log('DOSYA SILINDI');
        }
    });
}

// Fonksiyonları ayrı ayrı çağırabiliriz:
// createFile();
// readFile();
// updateFile();
// deleteFile();
```
