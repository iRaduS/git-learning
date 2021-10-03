# git-learning
Here lives a demo project of how to use GIT

test razvan

## Contahelper

### **Introducere**

Aceasta este documentația oficială a proiectului **Contahelper**. Proiectul reprezintă o soluție inedită în ținerea unei evidențe coezive pentru o companie ce are în subordine un parc de automobile, cât și situația angajaților din firma respectivă. Aplicația a pornit din necesitatea trecerii în mediul digital a unor rapoarte care erau importante în monitorizarea diverselor statistici legate de angajați.

---

### **Tehnologiile utilizate și arhitectura aplicației**

Aplicația din punct de vedere arhitectural se prezintă ca un [_monolith_](https://en.wikipedia.org/wiki/Monolithic_application), aceasta utilizând următoarele:

1. **Laravel (8.x)** - framework de PHP (a fost utilizat în totalitate pentru partea de backend)
2. **Vue** - framework de JavaScript (a fost utilizat pentru a crea componentele, elementele de UI, cât și paginile propriu-zise)
3. **TailwindCSS** - librărie de CSS (a fost utilizat pentru a aplica componentelor construite partea de design)
4. **Docker** - pentru a rula aplicația în containere și a facilita dezvoltarea acesteia
5. **MySQL** - baza de date pe care se bazează aplicația

Am ales aceste tehnologii (arhitectură) din mai multe puncte de vedere precum volumul datelor, volumul de trafic și totodată din cauza perioadei scurte de timp de care am beneficiat pentru a termina în totalitate aplicația.

---

### **Utilizarea aplicației în regim local**

1. Se vor instala dependențele necesare prin utilizarea comenzilor:

```
composer install
npm install
```

2. Se va forma un fișier **.env** prin utilizarea comenzii și se va completa cu datele necesare:

```
cp .env.example .env
```

3. Se va porni aplicația prin utilizarea comenzii:

```
./vendor/bin/sail up
```

Este necesar ca pe stația de unde se încearcă pornirea proiectului să se regăsească **npm**, **composer** și **docker**

---

### **Descriere detaliată**

Aplicația a fost construită în jurul unor _module_ pentru a asigura un flow coerent pentru utilizatorul ce folosește aplicația de față. Astfel, aceste module sunt:

1. **Autentificare & Profil** - așa cum îi spune și numele acest modul a fost construit pentru a asigura autentificarea în cadrul platformei, incluzând bineînțeles partea de resetare a parolei, toate acestea fiind furnizate de către framework-ul în speță. De asemenea, după ce un utilizator se autentifică, acestuia îi este prezentată pagina de profil unde poate să își actualizeze datele actuale (nume și adresă de e-mail), totodată își poate actualiza parola, poate beneficia de autentificare în doi pași prin intermediul _Google Authenticator_, poate să verifice sesiunile de pe care este autentificat și să se deconecteze de pe acestea.

2. **Sistem de permisiuni** - pentru sistemul de permisiuni și roluri m-am ajutat de pachetul [_spatie/laravel-permission_](https://github.com/spatie/laravel-permission), rămânând ca acestea să fie structurate și adaptate pe măsura nevoilor.

3. **Modulul de utilizatori** - pentru acest modul s-a folosit o funcționalitate de tip _CRUD_ (acronim pentru Create, Read, Update, Delete), de aici se controlează accesul utilizatorilor pe platformă, repsectiv se pot dezactiva/activa conturile create. Prin opțiunea de a edita un utilizator putem să edităm rolul acestuia sau permisiunile în cazul în care acesta nu este un administrator al platformei. În momentul în care un utilizator este creat, acesta va primi un e-mail cu datele de conectare la platforma.

4. **Modulul de monitorizare** - aici se văd majoritatea activităților pe care utilizatorii le fac pe platformă, incluzând adresa IP, cât și data la care s-a făcut acțiunea.

5. **Modulul de salarii & proiecte & locații** - folosesc un principiu asemănător pentru procesarea datelor, se pot crea (șterge) diverse intrări.

6. **Modulul de rapoarte** - se bazează pe statisticile înregistrate în platformă

### **Roby**

1. **Roby** Roby! - Roby
2. **Roby** Roby ;-;
