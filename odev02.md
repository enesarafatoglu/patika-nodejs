Blog oluşturmaya hazır mısınız? Konsol ekranında postlarımızı sıralayalım, sonrasında yeni bir post oluşturalım ve yeni post ile birlikte postlarımızı tekrar sıralayalım.
```JS
// İlk olarak, mevcut postlarımızı bir dizi içinde tanımlayalım
let posts = [
    { id: 1, title: "First Post", content: "This is the first post." },
    { id: 2, title: "Second Post", content: "This is the second post." },
    { id: 3, title: "Third Post", content: "This is the third post." }
];

// Postları konsol ekranında sıralı şekilde gösteren bir fonksiyon yazalım
function displayPosts() {
    console.log("Current Posts:");
    posts.map(post => {
        console.log(`ID: ${post.id}, Title: ${post.title}, Content: ${post.content}`);
    });
}

// Yeni bir post eklemek için bir fonksiyon yazalım
function addPost(newPost) {
    return new Promise((resolve, reject) => {
        if (newPost && newPost.id && newPost.title && newPost.content) {
            posts.push(newPost);
            resolve("Post added successfully.");
        } else {
            reject("Invalid post data.");
        }
    });
}

// Asenkron bir fonksiyon oluşturalım
async function managePosts() {
    try {
        // Mevcut postları sıralayalım
        displayPosts();

        // Yeni bir post oluşturalım
        let newPost = { id: 4, title: "Fourth Post", content: "This is the fourth post." };

        // Yeni postu ekleyelim ve sonucu bekleyelim
        let message = await addPost(newPost);
        console.log(message);

        // Yeni post eklendikten sonra tekrar postları sıralayalım
        displayPosts();
    } catch (error) {
        console.log(error);
    }
}

// Asenkron fonksiyonu çağırarak işlemleri başlatalım
managePosts();
```
