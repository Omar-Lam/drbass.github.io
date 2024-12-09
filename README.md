# username.github.io
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>قائمة الأسماء مع خانة البحث</title>
    <b:include data='blog' name='all-head-content'/>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f4f4f9;
        }
        .search-container {
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .search-container input {
            padding: 10px;
            width: 80%;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .search-container button {
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }
        .search-container button:hover {
            background-color: #45a049;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        th, td {
            padding: 10px;
            text-align: center;
            border: 1px solid #ddd;
            background-color: #fff;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        h1 {
            color: #333;
        }
    </style>
</head>
<body>

    <h1>قائمة الأسماء مع خانة البحث</h1>

    <div class="search-container">
        <input type="text" id="searchInput" placeholder="ابحث عن الاسم...">
        <button onclick="filterTable()">بحث</button>
    </div>

    <table id="nameTable">
        <thead>
            <tr>
                <th>الاسم الكامل</th>
                <th>اسم الأم</th>
                <th>المدينة</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>أحمد سعيد</td>
                <td>فاطمة محمد</td>
                <td>القاهرة</td>
            </tr>
            <tr>
                <td>محمد علي</td>
                <td>سارة حسين</td>
                <td>الإسكندرية</td>
            </tr>
            <tr>
                <td>هند عبد الله</td>
                <td>مريم حسن</td>
                <td>الجيزة</td>
            </tr>
            <tr>
                <td>خالد يوسف</td>
                <td>سعاد إبراهيم</td>
                <td>المنصورة</td>
            </tr>
            <tr>
                <td>فاطمة الزهراء</td>
                <td>عايدة فؤاد</td>
                <td>طنطا</td>
            </tr>
        </tbody>
    </table>

    <script>
        function filterTable() {
            let input = document.getElementById("searchInput");
            let filter = input.value.toLowerCase();
            let table = document.getElementById("nameTable");
            let tr = table.getElementsByTagName("tr");

            for (let i = 1; i < tr.length; i++) {
                let td = tr[i].getElementsByTagName("td");
                let match = false;

                // تحقق من وجود النص في أي خلية من الجدول
                for (let j = 0; j < td.length; j++) {
                    if (td[j]) {
                        if (td[j].textContent.toLowerCase().indexOf(filter) > -1) {
                            match = true;
                            break;
                        }
                    }
                }

                if (match) {
                    tr[i].style.display = "";
                } else {
                    tr[i].style.display = "none";
                }
            }
        }
    </script>

</body>
</html>
