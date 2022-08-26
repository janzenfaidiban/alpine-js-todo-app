# Learn Alpine JS to create simple Todo App

Belajar Alpine Js dengan studi kasus simple todo app

## Sumber belajar / video tutorial

[AlpineJS - The Most Fun You'll Ever Have Without a JavaScript File](https://youtu.be/AyxAwnc6zN8)


## Screenshot

<img src="https://github.com/janzenfaidiban/alpine-js-todo-app/blob/main/screenshot.png?raw=true">

## Alpine.js

Website Alpine.js kunjungi di sini ```https://alpinejs.dev```

## Menginstal Alpine.js

Tempatkan di dalam elemen ```<head>...</head>```

```html

<head>

    <title>Belajar Alpine.js</title>

    <!-- Alpine JS -->
    <script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>

    <!-- Bootstrap CSS only -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx" crossorigin="anonymous">

</head>

```

## Penerapan 

Penerapan Alpine.js di dalam elemen ```<body>...</body>```

```html

<body>
    <div x-data="{
                    name: 'Toko Sayur',
                    current: '',
                    count: 0,
                    list: ['Bayam', 'Bunga Pepaya', 'Pisang', 'Mangga'], 
                    add() {this.list.push(this.current)},
                    remove(item) {this.list.splice(this.list.indexOf(item), 1)}
                    }" 
        class="container mt-4">

    <h1 x-text="name"></h1>

    <div class="input-group mb-3">
        <input type="text" 
               x-model="current" 
               class="form-control form-control-lg py-3" 
               placeholder="Nama produk...">

        <button x-on:click="add" 
                class="btn btn-primary">
            <span x-text="list.length" 
                  class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger"></span> Tambah
        </button>
    </div>

    <ul class="list-group">
        <template x-for="item in list">
            <li class="list-group-item d-flex justify-content-between align-items-center p-3 mb-2 rounded border shadow-sm">
                <span x-text="item"></span>
                <button @click="remove(item)" 
                        type="button" 
                        class="btn btn-sm btn-danger btn-sm">&times;</button>
            </li>
        </template>
    </ul>

    </div>

</body>

```