<!DOCTYPE html>
<html>
<head>
    <title>Поиск картинок</title>
    <style>
        /* Стили для внешнего вида */
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        h1 {
            text-align: center;
        }

        .form-container {
            max-width: 400px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 10px;
        }

        .btn {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: #FFF;
            text-align: center;
            text-decoration: none;
            cursor: pointer;
        }

        .result {
            margin-top: 20px;
            text-align: center;
        }

        img {
            max-width: 100%;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>Поиск картинок</h1>

    <div class="form-container">
        <div class="form-group">
            <label for="imageType">Выберите тип картинки:</label>
            <select id="imageType">
                <option value="nature">Природа</option>
                <option value="animals">Животные</option>
                <option value="food">Еда</option>
                <option value="sports">Спорт</option>
            </select>
        </div>

        <button class="btn" onclick="searchImage()">Поиск</button>
    </div>

    <div class="result" id="result"></div>

    <script>
        function searchImage() {
            // Получение выбранного типа картинки
            var imageType = document.getElementById("imageType").value;

            // Формирование URL для поиска картинки
            var searchUrl = "";

            if (imageType === "nature") {
                searchUrl = "https://example.com/search?type=nature";
            } else if (imageType === "animals") {
                searchUrl = "https://example.com/search?type=animals";
            } else if (imageType === "food") {
                searchUrl = "https://example.com/search?type=food";
            } else if (imageType === "sports") {
                searchUrl = "https://example.com/search?type=sports";
            }

            // Очистка предыдущего результата (если есть)
            document.getElementById("result").innerHTML = "";

            // Создание элемента img и добавление его на страницу
            var image = document.createElement("img");
            image.src = searchUrl;
            document.getElementById("result").appendChild(image);
        }
    </script>
</body>
</html>
