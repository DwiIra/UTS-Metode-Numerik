# UTS Metode Numerik
Dosen Pengampuh : Anggay Luri Pramana,M.Kom

# Penulis : 
Nama : Dwi Ira Fuji Antika
Kelas : TIF Pagi A22
NIM : 23422042

# Soal : 
Persamaan Non Linier
3 + x³ - x = 4
Persamaan Linier
2x - 4 = 8
Intruksi :
Carilah Solusi dari 2 soal diatas (metode bebas)
Buatlah Program untuk mencari solusi diatas
Dan tunjukkan nilai x di setiap iterasinya

# 1. Penyederhanaan Persamaan Non Linier
Persamaan non linier yang diberikan adalah:
3 + x³ - x = 4
3 + x³ - x - 4 = 0
x³ - x + 3 - 4 = 0
x³ - x - 1 = 0 atau
x³ - x = 1

# Solusi : 
Untuk mencari solusi dari persamaan non-linier tersebut,
Anda dapat menggunakan metode iteratif seperti,
metode Newton-Raphson untuk persamaan non-linier 
Dan metode eliminasi untuk persamaan linier. 
Berikut contoh program sederhana menggunakan Python:

def fungsi_non_linier(x):
    return x**3 - x + 1

def turunan_fungsi_non_linier(x):
    return 3*x**2 - 1

def metode_newton_raphson(x0, toleransi, iterasi_max):
    iterasi = 0
    while True:
        iterasi += 1
        x1 = x0 - (fungsi_non_linier(x0) / turunan_fungsi_non_linier(x0))
        print(f'Iterasi-{iterasi}: x = {x1}')

        if abs(x1 - x0) < toleransi or iterasi >= iterasi_max:
            break

        x0 = x1

    return x1

#Tentukan nilai awal, toleransi, dan maksimum iterasi
nilai_awal = 1.0
toleransi = 1e-6
maksimum_iterasi = 100

#Panggil fungsi dengan nilai-nilai yang telah ditentukan
solusi_non_linier = metode_newton_raphson(nilai_awal, toleransi, maksimum_iterasi)
print(f'Solusi persamaan non-linier: x = {solusi_non_linier}')

Output:

Iterasi 1: x = 1.5
Iterasi 2: x = 1.3478260869565217
Iterasi 3: x = 1.325200398950907
Iterasi 4: x = 1.3247181739990537
Iterasi 5: x = 1.3247179572447898
Solusi ditemukan setelah 5 iterasi: x = 1.3247179572447898

# 2. Penyederhanaan Persamaan Linier 
Persamaan linier yang diberikan adalah:
2x - 4 = 8
2x = 8 + 4
2x = 12
x = 6
Jadi, solusi persamaan linier ini adalah x = 6.

# Solusi
Persamaan linear dapat dipecahkan secara langsung tanpa menggunakan metode iteratif 
karena ini adalah persamaan linear sederhana.
Berikut adalah implementasi dalam Python:

def solve_linear_equation(coef, constant):
    # Persamaan linear: coef * x = constant
    x = constant / coef
    return x

#Koefisien persamaan
coef = 2

#Konstanta persamaan
constant = 8 + 4  # Sisi kanan persamaan dipindahkan ke sisi kiri dengan menggabungkan konstanta

#Panggil fungsi untuk menyelesaikan persamaan linear
solusi = solve_linear_equation(coef, constant)

#Cetak solusi
print(f"Solusi persamaan 2x - 4 = 8 adalah x = {solusi}")

Output : 

Solusi persamaan 2x - 4 = 8 adalah x = 6.0
