---
title: 'C++'
description: 'C++ liceum'
pubDate: '11 08 2023'
heroImage: '/blog-placeholder-3.jpg'
---

<h1> Wektor </h1>
<p> Wszystko o wektorach: </p>

```
#include <vector>

vector <int> wektor;

.push_back() - wysyła element na koniec wektora
.insert() - dodaje element w podanym miejscu
.begin() - wskazuje pierwszy element wektora
.end() - wskazuje na koniec wektora
.size() - zwraca ilość elementów wektora
.erase() - usuwa dany element z wektora
.clear() - usuwa wszystkie elementy z wektora
.sort() - include <algorithm> - sortuje dany zbiór

sort(wektor.begin(),wektor.end())
    wektor[0]	    wektor[1]

```

<p> wpisywanie n elementów do wektora </p>

```
vector<int> Wektor;
int n;
cin >> n;
for(int i=0; i<n; i++>)
{
    int element;
    cout << "Podaj element " << i + 1 << ": ";
    cin >> element;
    Wektor.push_back(element);
}
cout << "Zawartosc wektora:";
for (int i = 0; i < mojWektor.size(); i++)
{
    cout << " " << mojWektor[i];
}

```

<p> TABLICA - wpisywanie n elementów </p>

```
#include <iostream>

using namespace std;

int main()
{
	int n;
	cin >> n;
	int tablica[n];

	cout << "Wprowadz " << n << " elementow do tablicy:" << endl;

	for (int i = 0; i < n; ++i)
	{
		cout << "Element " << i + 1 << ": ";
		cin >> tablica[i];
	}

	cout << "Wprowadzone elementy do tablicy:" << endl;
	for (int i = 0; i < n; ++i)
	{
		cout << tablica[i] << " ";
	}

	return 0;
}


```

<h1> Funkcje </h1>
<p> SILNIA </p>

```
int silnia(int n)
{
	if (n == 0)
	{
		return 1;
	}
	else 
	{
		return n*silnia(n-1);
	}
}

```

<p> NWW </p>

```
int main()
{
	int a,b,c,d,e;
	cin>>a;
	cin>>b;
	d=a*b;
	
	while(b!=0)
	{
		c=b;
		b=a%b;
		a=c;
	}
	e=d/a;
	cout<<"NWW: "<<e;
	return 0;
}

```

<p> NWD </p>

```
int nwd(int a,int b)
{
   if(a==b) return a;
   else if(a>b) return nwd(a-b,b);
   else return nwd(a,b-a);
}
 
int main()
{
	int a, b;
	cin >> a >> b;
	cout<<nwd(a, b);
	return 0;
}

```

<p> FIB </p>

```
int fib(int n)
{
	if (n <= 2)
	{
		return 1;	
	}
	else return fib(n-1)+fib(n-2);
}
 
int main()
{
	int a;
	cin >> a;
	cout<<fib(a);
	return 0;
}

```

<p> Dzielniki - wpisywane do wektora </p>

```
void dz(int x, int &l, int &s)
{
    vector<int> dzielniki;

    for (int i = 1; i <= x; i++)
    {
        if (x % i == 0)
        {
            dzielniki.push_back(i);
        }
    }

    l = dzielniki.size();
    s = 0;

    for (int dzielnik : dzielniki)
    {
        s += dzielnik;
    }
}

int main()
{
    int a;
    int l1, l2;
    cin >> a;
    dz(a, l1, l2);
    cout << "Iloœæ dzielników: " << l1 << endl;
    cout << "Suma dzielników: " << l2 << endl;
}

```

<p> Liczba doskonała </p>

```
bool ld(int x)
{
	int s=0;
	for(int i=1;i<x;i++)
	{
		if(x%i == 0)
		s=s+i;
	}
	if(s==x) return true;
	else return false;
}

int main()
{
	int n, m;
	cin>>n;
	//cout<<ld(n)<<endl;
	for(int i=1;i<=n;i++)
	{
		if(ld(i)==true) cout<<"liczba jest liczba doskonala "<<i<<endl;
	}
	return 0;
}

```

<p> Macierze wektor - wszystko </p>

```
#include <iostream>
#include <vector>

using namespace std;

// Funkcja do wczytywania macierzy
vector<vector<int>> wczytajMacierz(int m, int n) {
    vector<vector<int>> macierz(m, vector<int>(n, 0));

    cout << "Wprowadz elementy macierzy:" << endl;
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            cin >> macierz[i][j];
        }
    }

    return macierz;
}

// Funkcja do wyświetlania macierzy
void wyswietlMacierz(const vector<vector<int>>& macierz) {
    int m = macierz.size();
    int n = macierz[0].size();

    cout << "Macierz:" << endl;
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            cout << macierz[i][j] << "\t";
        }
        cout << endl;
    }
}

// Funkcja do mnożenia macierzy przez skalar
vector<vector<int>> pomnozMacierzPrzezSkalar(const vector<vector<int>>& macierz, int k) {
    int m = macierz.size();
    int n = macierz[0].size();

    vector<vector<int>> wynik(m, vector<int>(n, 0));

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            wynik[i][j] = macierz[i][j] * k;
        }
    }

    return wynik;
}

// Funkcja do mnożenia macierzy A i B
vector<vector<int>> pomnozMacierze(const vector<vector<int>>& A, const vector<vector<int>>& B) {
    int m = A.size();
    int n = A[0].size();
    int p = B[0].size();

    vector<vector<int>> wynik(m, vector<int>(p, 0));

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < p; j++) {
            for (int k = 0; k < n; k++) {
                wynik[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    return wynik;
}

int main() {
    int n, m;

    cout << "Podaj liczby n i m (wymiar macierzy):" << endl;
    cin >> m >> n;

    vector<vector<int>> A = wczytajMacierz(m, n);
    vector<vector<int>> B = wczytajMacierz(m, n);

    wyswietlMacierz(A);
    wyswietlMacierz(B);

    cout << endl;
    cout << "Wybierz opcje:" << endl;
    cout << "1. Mnozenie macierzy A przez skalar" << endl;
    cout << "2. Mnozenie macierzy B przez skalar" << endl;
    cout << "3. Mnozenie macierzy A i B" << endl;

    int opcja;
    cin >> opcja;

    if (opcja == 1) {
        int k;
        cout << "Podaj skalar: ";
        cin >> k;
        vector<vector<int>> wynik = pomnozMacierzPrzezSkalar(A, k);
        wyswietlMacierz(wynik);
    } else if (opcja == 2) {
        int k;
        cout << "Podaj skalar: ";
        cin >> k;
        vector<vector<int>> wynik = pomnozMacierzPrzezSkalar(B, k);
        wyswietlMacierz(wynik);
    } else if (opcja == 3) {
        if (n != m) {
            cout << "Liczba kolumn macierzy A musi byc rowna liczbie wierszy macierzy B." << endl;
        } else {
            vector<vector<int>> wynik = pomnozMacierze(A, B);
            wyswietlMacierz(wynik);
        }
    } else {
        cout << "Niepoprawna opcja." << endl;
    }

    return 0;
}

```
<h1> SORTOWANIE </h1>
<p> Sortowanie - bąbelkowe </p>

```
#include <iostream>

using namespace std;

void zamien (int &a, int &b)
{
	int temp = a;
	a = b;
	b = temp;
}

void sortowanie_babelkowe(int tab[], int n)
{
	int temp;
	for(int j=n-1; j>0; j--)
	{
		for(int i=0; i<j; i++)
		{
			if(tab[i]>tab[i+1])
				zamien(tab[i],tab[i+1]);
		}
	}
}

int main()
{
	int n;
	cin >> n;
	int tablica[n];

	cout << "Wprowadz " << n << " elementow do tablicy:" << endl;

	for (int i = 0; i < n; ++i)
	{
		cout << "Element " << i + 1 << ": ";
		cin >> tablica[i];
	}

	sortowanie_babelkowe(tablica, n);
	for (int i = 0; i < n; ++i)
	{
		cout << tablica[i] << " ";
	}

	return 0;
}

```

<p> Sortowanie - przez wybór </p>

```
#include <iostream>
#include <iomanip>

using namespace std;

void zamien (int &a, int &b)
{
	int temp = a;
	a = b;
	b = temp;
}

void sortowanie_przez_wybor(int tab[], int n)
{
    int temp, i, j, k;
    for (i = 0; i < n; i++)
    {
        k = i;
        for (j = i + 1; j < n; j++)
        {
            if (tab[j] < tab[k])
                k = j;
        }
        zamien(tab[k], tab[i]);
    }
}


void wypisz (int tab[], int n)
{
	for(int i=0; i<n; i++)
	{
		cout << setw(3) << tab[i];
	}
	cout << endl;
}

int main()
{
	int n;
	cin >> n;
	int tablica[n];

	cout << "Wprowadz " << n << " elementow do tablicy:" << endl;
	for (int i = 0; i < n; ++i)
	{
		cout << "Element " << i + 1 << ": ";
		cin >> tablica[i];
	}

	wypisz(tablica, n);
	cout << "Posortowana tablica: " << endl;
	sortowanie_przez_wybor(tablica,n);
	wypisz(tablica,n);
	getchar();	
	return 0;	
}

```

<p> Sortowanie - przez wstawianie </p>

```
#include <iostream>
#include <iomanip>

using namespace std;

void zamien (int &a, int &b)
{
	int temp = a;
	a = b;
	b = temp;
}

void sortowanie_przez_wstawianie(int tab[], int n)
{
    int elem, i, k;
    for (i = 1; i < n; i++)
    {
        elem = tab[i];
        k = i - 1;
        while(k>=0 && tab[k]>elem)
        {
        	tab[k+1] = tab[k];
        	k--;
		}
		tab[k+1] = elem;
    }
}

void wypisz (int tab[], int n)
{
	for(int i=0; i<n; i++)
	{
		cout << setw(3) << tab[i];
	}
	cout << endl;
}

int main()
{
	int n;
	cin >> n;
	int tablica[n];

	cout << "Wprowadz " << n << " elementow do tablicy:" << endl;
	for (int i = 0; i < n; ++i)
	{
		cout << "Element " << i + 1 << ": ";
		cin >> tablica[i];
	}

	wypisz(tablica, n);
	cout << "Posortowana tablica: " << endl;
	sortowanie_przez_wstawianie(tablica,n);
	wypisz(tablica,n);
	getchar();	
	return 0;	
}

```

<script>
const copyButtonLabel = "Copy Code";

// use a class selector if available
let blocks = document.querySelectorAll("pre");

blocks.forEach((block) => {
  // only add button if browser supports Clipboard API
  if (navigator.clipboard) {
    let button = document.createElement("button");

    button.innerText = copyButtonLabel;
    block.appendChild(button);

    button.addEventListener("click", async () => {
      await copyCode(block, button);
    });
  }
});

async function copyCode(block, button) {
  let code = block.querySelector("code");
  let text = code.innerText;

  try {
    await navigator.clipboard.writeText(text);

    // Visual feedback that the task is completed
    button.innerText = "Code Copied";
    button.classList.add("copied");

    setTimeout(() => {
      button.innerText = copyButtonLabel;
      button.classList.remove("copied");
    }, 700);
  } catch (err) {
    console.error('Unable to copy code', err);
  }
}
</script>

<style>
/* Add your custom styles for the copy button */
button {
  background-color: #4caf50; /* Green background color */
  color: white; /* White text color */
  border: none; /* Remove border */
  padding: 8px 16px; /* Add some padding */
  text-align: center; /* Center text */
  text-decoration: none; /* Remove underline */
  display: inline-block;
  font-size: 14px;
  margin-top: 10px; /* Add some margin at the top for spacing */
  cursor: pointer; /* Add a pointer cursor on hover */
}

/* Change the button color on hover */
button:hover {
  background-color: #45a049;
}

/* Style for the "Code Copied" message */
button.copied {
  background-color: #008CBA; /* Blue background color */
}

</style>