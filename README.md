# Klasifikasi Jamur Menggunakan Artificial Neuron Network dan Genetic Algorithm

Oleh:
- Aldi Oktaviana Hidayat
- Muhammad Naufal Abdillah
- Mohammad Thareeq Izzulhaq
- Muhammad Dwiki Ramdhani
- Muhammad Rayhan Adyatma 

## Problem Statement

- Mushroom hunting(shrooming)
- Aturan pengenalan tidak sederhana
- Klasifikasi ke dalam dua kategori yaitu aman dikonsumsi(edible) dan beracun(poisonous)
- 23 spesies jamur dari famili Agaricus dan Lepiota dengan total sample sebanyak 8124.


## Approach

- Bagaimana mengoptimasi pembobotan yang digunakan pada Artificial Neural Network(ANN) untuk menentukan class jamur yang ada pada dataset ia beracun atau tidak.
- Fungsi aktivasi yang digunakan sigmoid
- Genetic algorithm digunakan untuk menentukan pembobotan pada node di semua layer yang ada di ANN untuk menentukan klasifikasi jamur ini. 


## Arsitektur ANN

<img alt="Arsitektur" src="">
<br><br>
Arsitektur ini terdiri atas 4 layer dengan 22 node di layer input, 2 hidden layer dengan masing-masing node berjumlah 128 node dan 64 node, terakhir layer yang digunakan adalah output layer dengan 2 node.


## Implementasi

Secara garis besar, tahapan implementasi yang dilakukan adalah sebagai berikut:
1. Import dataset ke workspace
2. Karena terdapat missing value pada kolom stalk root pada dataset yang digunakan, maka perlu dilakukan data cleaning missing value tersebut dengan metode modus. 
3. Melabeli semua data yang sebelumnya bertipe objek/string dikodekan menjadi angka dari 0 hingga banyaknya objek yang unik dari data kolom tersebut menggunakan label encoder.
4. Dilakukan pembagian dataset menjadi data train dan data test dengan perbandingan 80%:20%.
5. Menentukan parameter yang akan digunakan pada proses genetic algorithm nantinya. Parameter yang digunakan adalah solution_per_population = 8, num_parents_mating = 4, num_generations = 100, mutation_percent = 0.1-1. Di proyek ini digunakan banyaknya parents mating saja tanpa menggunakan crossover_rate, pemilihan parents ini dilakukan secara acak 
6. Setiap bobot per layer pada proses Artificial Neural Network (ANN) dilakukan inisiasi awal
7. Proses utama optimasi bobot pada tiap node di setiap layer ANN menggunakan algoritma genetic algorithm.


## Proses Genetic Algorithm

<img alt="Proses Genetic Algorithm" src="">

## Hasil

<img alt="Error Rate Vs. Mutation Percent" src="">
<br><br>
- Percobaan terhadap perubahan nilai Mutation rate dari 10% - 90%
- Nilai mutasi terbaik didapat ketika nilai Mutation rate 10%
- Semakin besar mutation-rate-nya, error-rate-nya cenderung lebih besar
- terdapat dua nilai yang mengalami penurunan error rate :
  * Mutation rate 30% ke 40%
  * Mutation rate 70% ke 80%


## Kesimpulan

- Pendekatan GA dapat dilakukan untuk penentuan bobot dari ANN
- Perubahan nilai Mutation rate mempengaruhi nilai fitness secara negatif
- Nilai mutation rate terbaik untuk kasus ini yaitu 10%
- Akurasi dari model terbaik yaitu 85.44%
- Penerapan data test pada model mendapatkan akurasi sebesar 85.47%
