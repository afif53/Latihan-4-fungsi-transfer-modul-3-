# Latihan-4-fungsi-transfer-modul-3-
tugas class room  dengan link berikut .  https://classroom.google.com/c/ODAyNDczODQxOTQ5/a/ODMxODE5NTA5ODIy/details

NO 1

>> num = [1 1];
den = [1 3 1];
sys = tf(num,den) % Membuat fungsi transfer
sys_zpk = zpk(sys) % Mengubah ke model zpk

sys =
 
      s + 1
  -------------
  s^2 + 3 s + 1
 
Continuous-time transfer function.
Model Properties

sys_zpk =
 
         (s+1)
  -------------------
  (s+2.618) (s+0.382)
 
Continuous-time zero/pole/gain model.
Model Properties
>> z = -2;
p = [-1 -1 -3];
k = 1;
sys = zpk(z,p,k) % membuat model zpk

sys =
 
      (s+2)
  -------------
  (s+1)^2 (s+3)
 
Continuous-time zero/pole/gain model.
Model Properties
>> sys_tf = tf(sys) % mengubah ke model fungsi transfer

sys_tf =
 
          s + 2
  ---------------------
  s^3 + 5 s^2 + 7 s + 3
 
Continuous-time transfer function.
Model Properties
>> s = tf('s');% menetapkan variabel s, sebagai variabel dari fungsi transfer
sys = (s+1)/(s^2+2*s+1)

sys =
 
      s + 1
  -------------
  s^2 + 2 s + 1
 
Continuous-time transfer function.
Model Properties
>> s = zpk('s');%Mengembalikan fungsi transfer dalam bentuk terfaktor
sys = (s+1)/(s^2+2*s+1)

sys =
 
   (s+1)
  -------
  (s+1)^2
 
Continuous-time zero/pole/gain model.
Model Properties
>> s = zpk('s');% Menetapkan variabel s, sebagai variabel dari fungsi transfer
sys = ((s+2)*(s-1))/(((s+3)^2)*(s-5))

sys =
 
   (s+2) (s-1)
  -------------
  (s+3)^2 (s-5)
 
Continuous-time zero/pole/gain model.
Model Properties
>> s = tf('s');% Mengembalikan fungsi transfer dalam bentuk polinomial
sys = ((s+2)*(s-1))/(((s+3)^2)*(s-5))

sys =
 
       s^2 + s - 2
  ---------------------
  s^3 + s^2 - 21 s - 45
 
Continuous-time transfer function.
Model Properties
>> num=[6 0 1];
den=[1 3 3 1];
pzmap(num,den)
title('Pole-zero map');
>> n1=[1 1];
n2=[1 2];
d1=[1 2*i];
d2=[1 -2*i];
d3=[1 3];
num=conv(n1,n2);
den=conv(d1,conv(d2,d3));
printsys(num,den);
pzmap(num,den);
title('Pole-zero map');
 
num/den = 
 
        s^2 + 3 s + 2
   ----------------------
   s^3 + 3 s^2 + 4 s + 12

NO 2.Hasil fungsi transfer berikut ini

Dalam bentuk:
a. Rasio terfaktor
b. Rasio polynomial

>> z = [-15 -26 -72]; % Mendefinisikan Zeros, Poles, dan Gain

p = [0, -55, -56, roots([1 5 30])', roots([1 27 52])'];

k = 5;

disp('a. RASIO TERFAKTOR (Zero-Pole-Gain)');

Gzpk = zpk(z, p, k)% Gunakan fungsi zpk

disp('b. RASIO POLINOMIAL (Transfer Function)');

Gp = tf(Gzpk)% Gunakan fungsi tf() untuk konversi dari ZPK ke TF
a. RASIO TERFAKTOR (Zero-Pole-Gain)

Gzpk =
 
                5 (s+15) (s+26) (s+72)
  ---------------------------------------------------
  s (s+55) (s+56) (s+24.91) (s+2.087) (s^2 + 5s + 30)
 
Continuous-time zero/pole/gain model.
Model Properties
b. RASIO POLINOMIAL (Transfer Function)

Gp =
 
                                                      
                    5 s^3 + 565 s^2 + 16710 s + 140400
                                                      
  ----------------------------------------------------------------------
                                                                        
  s^7 + 143 s^6 + 6849 s^5 + 1.237e05 s^4 + 7.887e05 s^3 + 3.469e06 s^2 
                                                                        
                                                           + 4.805e06 s 
                                                                        
 
Continuous-time transfer function.
Model Properties

NO 3. Dari fungsi transfer berikut ini:
Tunjukkan hasil rasio terfaktor dan rasio polynomial

>> num = [1 25 20 15 42];% Koefisien Pembilang (Numerator)

den = [1 13 9 37 35 50];% Koefisien Penyebut (Denominator)

disp('a. RASIO POLINOMIAL (Transfer Function)');% Membuat Model Rasio Polinomial (Transfer Function / TF)

Gtf = tf(num, den)

disp('b. RASIO TERFAKTOR (Zero-Pole-Gain) ');% Mengkonversi model Gtf ke bentuk Zero-Pole-Gain (ZPK)

Gzpk = zpk(Gtf)
a. RASIO POLINOMIAL (Transfer Function)

Gtf =
 
      s^4 + 25 s^3 + 20 s^2 + 15 s + 42
  -----------------------------------------
  s^5 + 13 s^4 + 9 s^3 + 37 s^2 + 35 s + 50
 
Continuous-time transfer function.
Model Properties
b. RASIO TERFAKTOR (Zero-Pole-Gain) 

Gzpk =
 
        (s+24.2) (s+1.35) (s^2 - 0.5462s + 1.286)
  ------------------------------------------------------
  (s+12.5) (s^2 + 1.463s + 1.493) (s^2 - 0.964s + 2.679)
 
Continuous-time zero/pole/gain model.
Model Properties

NO 4.% Program MATLAB untuk menghitung Partial-Fraction Expansion F(s)

% Definisi Awal Zeros, Poles, dan Gain (Sesuai F(s))

 
>> z = [-5 -70];

p = [0 -45 -55 roots([1 7 110])' roots([1 6 95])'];

k = 1e4;

[numg, deng] = zp2tf(z', p', k);

disp('Hasil Ekspansi Pecahan Parsial [r, p, k]');
[r, p, k_const] = residue(numg, deng)
Hasil Ekspansi Pecahan Parsial [r, p, k]

NO 5
r =

  -0.0018 + 0.0000i
   0.0066 + 0.0000i
   0.9513 + 0.0896i
   0.9513 - 0.0896i
  -1.0213 - 0.1349i
  -1.0213 + 0.1349i
   0.1353 + 0.0000i


p =

 -55.0000 + 0.0000i
 -45.0000 + 0.0000i
  -3.5000 + 9.8869i
  -3.5000 - 9.8869i
  -3.0000 + 9.2736i
  -3.0000 - 9.2736i
   0.0000 + 0.0000i


k_const =

     []

>> syms s

% --- Bagian (a): G_a(s) ---
Ga_simbolik = 45 * (s^2 + 37*s + 74) * (s^3 + 28*s^2 + 32*s + 16) / ...
    ( (s + 39) * (s + 47) * (s^2 + 2*s + 100) * (s^3 + 27*s^2 + 18*s + 15) );

disp('G_a(s) - Rasio Terfaktor:');
pretty(Ga_simbolik)

disp('G_a(s) - Rasio Polinomial:');
pretty(expand(Ga_simbolik))

% --- Bagian (b): G_b(s) ---
disp(' ');

Gb_simbolik = 56 * (s + 14) * (s^2 + 49*s + 62*s + 53) / ...
    ( (s^3 + 81*s^2 + 76*s + 65) * (s^2 + 88*s + 33) * (s^2 + 56*s + 77) );

disp('G_b(s) - Rasio Terfaktor:');
pretty(Gb_simbolik)

disp('G_b(s) - Rasio Polinomial:');
pretty(expand(Gb_simbolik))
G_a(s) - Rasio Terfaktor:
           2                    3       2
      (45 s  + 1665 s + 3330) (s  + 28 s  + 32 s + 16)
-----------------------------------------------------------
                    2                3       2
(s + 39) (s + 47) (s  + 2 s + 100) (s  + 27 s  + 18 s + 15)

G_a(s) - Rasio Polinomial:
                           2          3         4       5
133200 s   53280   147240 s    51390 s    2925 s    45 s
-------- + ----- + --------- + -------- + ------- + -----
   #1        #1        #1         #1         #1       #1

where

          7        6         5          4           3            2
   #1 == s  + 115 s  + 4499 s  + 70700 s  + 553692 s  + 5201463 s

      + 3483390 s + 2749500


 
G_b(s) - Rasio Terfaktor:
                             2
              (56 s + 784) (s  + 111 s + 53)
----------------------------------------------------------
  2                2                3       2
(s  + 88 s + 33) (s  + 56 s + 77) (s  + 81 s  + 76 s + 65)

G_b(s) - Rasio Polinomial:
                        2       3
89992 s   41552   7000 s    56 s
------- + ----- + ------- + -----
   #1       #1       #1       #1

where

          7        6          5           4            3            2
   #1 == s  + 225 s  + 16778 s  + 427711 s  + 1093333 s  + 1188715 s

      + 753676 s + 165165


>> 
