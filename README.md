# SPNL-Regula-Falsi
Berikut adalah code yang berhubungan dengan Regula Falsi dengan Python
```python
def f(x):
    return x**2 - 6*x + 5

a = 3.0  # Batas awal selang
b = 6.0  # Batas akhir selang

# Inisialisasi tabel penolong
print("{:<10} {:<10} {:<10} {:<10} {:<10} {:<10} {:<10} {:<10}".format(
    "Iterasi", "a", "b", "f(a)", "f(b)", "x", "f(x)", "Lebar"))

# Lima iterasi
for iterasi in range(7):
    x = (a * f(b) - b * f(a)) / (f(b) - f(a))

    # Hitung f(x)
    f_x = f(x)

    # Cek akar di selang [a, x] atau [x, b]
    if f(a) * f_x < 0:
        b = x
    else:
        a = x

    # Hitung lebar selang
    lebar_selang = abs(a - b)

    # Tampilkan hasil pada tabel penolong
    print("{:<10} {:<10.3f} {:<10.3f} {:<10.3f} {:<10.3f} {:<10.3f} {:<10.3f} {:<10.3f}".format(
        iterasi + 1, a, b, f(a), f(b), x, f_x, lebar_selang))

# Hasil akar pada iterasi ke-5
print("\nAkar yang ditemukan pada iterasi ke-5: {:.3f}".format(x))
```

```
Iterasi    a          b          f(a)       f(b)       x          f(x)       Lebar     
1          4.333      6.000      -2.222     5.000      4.333      -2.222     1.667     
2          4.846      6.000      -0.592     5.000      4.846      -0.592     1.154     
3          4.968      6.000      -0.126     5.000      4.968      -0.126     1.032     
4          4.994      6.000      -0.026     5.000      4.994      -0.026     1.006     
5          4.999      6.000      -0.005     5.000      4.999      -0.005     1.001     
6          5.000      6.000      -0.001     5.000      5.000      -0.001     1.000     
7          5.000      6.000      -0.000     5.000      5.000      -0.000     1.000     

Akar yang ditemukan pada iterasi ke-5: 5.000
```
