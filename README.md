<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kamus Bahasa Inggris</title>
<style>
    body {
        font-family: Arial, sans-serif;
    }
    #searchInput {
        padding: 5px;
        width: 250px;
        margin-bottom: 10px;
    }
    #result {
        margin-top: 10px;
    }
</style>
</head>
<body>

<h2>Kamus Bahasa Inggris</h2>

<input type="text" id="searchInput" placeholder="Cari kata...">
<div id="result"></div>

<script>
    // Data kamus
    var dictionary = [
        { word: "apple", definition: "a round fruit with red or green skin and a whitish interior" },
        { word: "banana", definition: "a long curved fruit which grows in clusters and has soft pulpy flesh and yellow skin when ripe" },
        { word: "cat", definition: "a small domesticated carnivorous mammal with soft fur" },
        { word: "dog", definition: "a domesticated carnivorous mammal that typically has a long snout, an acute sense of smell, and a barking, howling, or whining voice" }
        // tambahkan kata-kata lain di sini
    ];

    // Fungsi pencarian
    function searchDictionary() {
        var input = document.getElementById("searchInput").value.toLowerCase();
        var resultDiv = document.getElementById("result");
        resultDiv.innerHTML = ""; // Mengosongkan hasil sebelumnya

        if (input.trim() === "") {
            resultDiv.innerHTML = "Masukkan kata untuk mencari.";
            return;
        }

        var found = false;
        for (var i = 0; i < dictionary.length; i++) {
            if (dictionary[i].word.toLowerCase().includes(input)) {
                resultDiv.innerHTML += "<b>" + dictionary[i].word + "</b>: " + dictionary[i].definition + "<br>";
                found = true;
            }
        }

        if (!found) {
            resultDiv.innerHTML = "Kata tidak ditemukan dalam kamus.";
        }
    }

    // Memanggil fungsi searchDictionary saat tombol ditekan
    document.getElementById("searchInput").addEventListener("keyup", function(event) {
        if (event.key === "Enter") {
            searchDictionary();
        }
    });
</script>

</body>
</html>
