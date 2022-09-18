<h1 align="center"><b>Time Complexity dan Big-O Notation</b></h1>
<br>

<p align="justify">Setiap programmer yang baik akan menggunakan cara yang paling efektif dan efisien dalam menyelesaikan suatu permasalahan. Dan untuk bisa melakukan hal tersebut, <b>kita harus bisa meminimalisir kompleksitas dari algoritma yang kita gunakan.</b></p>

<p align="justify">Kompleksitas suatu algoritma dibagi menjadi 2, yaitu <i>Time Complexity</i> dan <i>Space Complexity</i>.</p>

<p align="justify"><b>Time Complexity</b> adalah seberapa lama waktu yang diperlukan untuk menjalankan suatu algoritma. Sedangkan <b>Space Complexity</b> adalah seberapa besar memori yang kita gunakan untuk menjalankan suatu algoritma. Dan disini kita hanya akan membahas tentang Time Complexity.</p><br>

### **Apa itu Algoritma?**

<br>

<p align="justify">Algoritma adalah serangkaian proses yang dilakukan secara berurutan untuk menyelesaikan sebuah permasalahan. Algoritma bisa bermacam-macam tergantung kepada siapa yang membuat algoritma tersebut. Namun permasalahannya adalah <b><i>algoritma mana yang lebih efektif dan efisien?</i></b></p>

<p align="justify"><b>Time Complexity Analysis</b> adalah <i>suatu cara sederhana untuk mengetahui berapa lama waktu yang dibutuhkan untuk menjalankan suatu algoritma dengan input tertentu (n).</i> Biasanya lebih dikenal dengan sebutan <b>Big-O Notation</b>.</p>

<p align="justify"><i><b>Big-O Notation</b></i> digunakan untuk mengukur tingkat kompleksitas suatu algoritma.</p><br>

<h2 align="center"><b>Big-O Nation</b></h2>

<br>

<p align="justify">Big-O Notation adalah cara untuk mengkonversi keseluruhan langkah-langkah suatu algoritma kedalam bentuk Aljabar, yaitu dengan menghiraukan konstanta yang lebih kecil dan koefisien yang tidak berdampak besar terhadap keseluruhan kompleksitas permasalahan yang diselesaikan oleh algoritma tersebut.</p>

<p align="justify">Mari kita lihat contoh dibawah ini:</p>

```
Regular       Big-O
2             O(1)   --> It's just a constant number
2n + 10       O(n)   --> n has the largest effect
5n^2          O(n^2) --> n^2 has the largest effect
```

<p align="justify">Sederhananya, semua contoh yang ada diatas mengatakan bahwa <i><b>“kita hanya akan melihat faktor yang memiliki dampak paling besar terhadap nilai yang dihasilkan oleh algoritma tersebut”</b></i>.</p>


<p align="justify">Terdapat beberapa macam **time complexity**, diantaranya :</p><br>

## **O(1) — Constant Time**

<br>

<p align="justify"><b>Constant Time</b> artinya banyaknya input yang diberikan kepada sebuah algoritma, tidak akan mempengaruhi waktu proses <i>(runtime)</i> dari algoritma tersebut.</p>

```
let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
function getFirst(input){
   return input[0]; // selalu melakukan 1 langkah
}
let firstEl = getFirst(myArray);
```

<p align="justify">Dari contoh di atas, terdapat sebuah fungsi untuk mengambil elemen pertama dari sebuah input array. Kita bisa melihat bahwa berapapun jumlah array yang diberikan kepada fungsi tersebut, dia akan selalu melakukan 1 hal, yaitu mengambil elemen pertama. Itu artinya <b>jumlah input yang diberikan tidak mempengaruhi waktu proses <i>(runtime)</i> dari algoritma tersebut.</b></p>

![Figure]()

<br>

## **O(log n) — Logarithmic Time**

<br>

<p align="justify"><b>Logarithmic Time</b> artinya ketika kita memberikan input sebesar n terhadap sebuah fungsi, jumlah tahapan yang dilakukan oleh fungsi tersebut berkurang berdasarkan suatu faktor. Salah satu contohnya adalah algoritma <b>Binary Search.</b></p>

<p align="justify"><b>Binary Search</b> adalah algoritma yang kita gunakan dalam mencari posisi nilai dari suatu array dengan cara ‘mengeliminasi’ setengah dari array input untuk mempercepat proses pencarian.</p>

```
let sortedArray = [11, 24, 30, 43, 51, 61, 73, 86];
function isExists(number, array){
    var midPoint = Math.floor( array.length /2 );
    if( array[midPoint] === num) return true;
    let isFirstHalf = false;
    if( array[midPoint] < num ) isFirstHalf = true;
  
    else if( array[midpoint] > num ) isFirstHalf = false;
    if (array.length == 1) return false;
    else { 
        // memanggil fungsi yang sama dengan mengeleminiasi setengah dari input array
        if (isFirstHalf) 
            return isExists(number, getFirstHalf(array));
        else 
            return isExists(number, getSecondHalf(array));
    }
}
isExists (24, sortedArray); // return true
isExists (27, sortedArray); // return false
```

_Note: Fungsi rekursif biasanya Logarithmic_

<br>

## **O(n) — Linear Time**

<p align="justify"><b>Linear Time</b> adalah ketika <i>runtime</i> dari fungsi kita berbanding lurus dengan jumlah input yang diberikan.</p>

```
let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
function getMax(input){
    var max = 0;
    for (var i=0; i<input.length; i++){
        if (max < input[i])
            max = input[i];
    }
    return max;
}
let maxNumber = getMax(myArray);
```

<p align="justify">Kita bisa melihat bahwa <b>semakin banyak jumlah input yang diberikan, maka waktu proses/<i>runtime</i> dari fungsi tersebut akan semakin besar.</b></p>

![Figure]()

<br>

## **O(n²) — Quadratic Time**

<br>

<p align="justify"><b>Quadratic Time</b> adalah ketika runtime dari fungsi kita adalah sebesar</p>

```
n^2
```
<p align="justify">dimana </p>

```
n
```

<p align="justify">adalah jumlah input dari fungsi tersebut. Hal tersebut bisa terjadi karena kita menjalankan <b>fungsi linear didalam fungsi linear</b> (n*n).</p>

```
let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
function sort(input){
    var sortedArray = [];
    for (var i=0; i<input.length; i++){ // O(n)
        let min = input[i];
        for (var j=i+1; i<input.length; i++){ // O(n)
            if (input[i] < input[j])
                min = input[j];
        }
        sortedArray.push(min);
    }
    return sortedArray;
}
let sortedArray = sort(myArray);
```

![Figre]()

<br>


## **O(2^n) — Exponential Time**

<p align="justify"><b>Exponential Time</b> biasanya digunakan dalam situasi dimana kita tidak terlalu tahu terhadap permasalahan yang dihadapi, sehingga mengharuskan kita mencoba setiap <b>kombinasi</b> dan <b>permutasi</b> dari semua kemungkinan.</p>

![Figre]()

<br>

### **Kesimpulan**

<p align="justify">Sebagai <i>programmer</i>, kita sering kali dihadapkan dengan adanya beberapa solusi untuk sebuah permasalahan dan kita dibingungkan dengan pertanyaan <b><i>“mana solusi yang lebih efisien?”</i></b>.</p>

<p align="justify">Dengan memahami <b>Big-O Notation</b>, kita akan lebih mudah dalam melihat mana algoritma yang lebih efisien yang bisa kita gunakan untuk menyelesaikan permasalahan yang sedang dihadapi.</p>