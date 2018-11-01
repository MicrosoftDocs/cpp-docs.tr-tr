---
title: '&lt;dize&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: 7707f1239bb8612b1c454997a98d134165f09b75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544293"
---
# <a name="ltstringgt-functions"></a>&lt;dize&gt; işlevleri

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[değiştirme](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>  getline

Dizeleri giriş akışında satır-tarafından-satırından ayıklayın.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*is*<br/>
Bir dize ayıklanacak olduğu giriş akışı.

*str*<br/>
Karakterleri giriş akışından okuma dize.

*Delim*<br/>
Satır sınırlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Giriş akışı *olduğu*.

### <a name="remarks"></a>Açıklamalar

İşlev imzası çiftinin işaretlenmiş `(1)` karakterlerin ayıklanacağı *olduğu* kadar *delim* bulunamadı, içinde depolamadan *str*.

İşlev imzası çiftinin işaretlenmiş `(2)` varsayılan satır ayırıcı olarak yeni satır kullanın ve olarak davranır **getline**(`is`, `str`, `is`. `widen`(' `\n`')).

İkinci her çiftinin bir analog desteklemek için ilk bir işlevdir [rvalue başvuruları](../cpp/lvalues-and-rvalues-visual-cpp.md).

Aşağıdakilerden biri oluştuğunda ayıklama durdurur:

- En son dosya, bu durumda iç durumu bayrak *olduğu* ayarlanır `ios_base::eofbit`.

- İşlev eşit karşılaştıran bir öğe ayıklar sonra `delim`, bu durumda öğe geri put ne denetlenen dizi için eklenmiş.

- İşlev ayıklar sonra `str.` [max_size](../standard-library/basic-string-class.md#max_size) öğeleri, case, iç durum bayrağı *olduğu* ayarlanır `ios_base::failbit`.

- Başka bir hata dışındaki daha önce listelenen, bu durumda iç durumu bayrak *olduğu* ayarlanır `ios_base::badbit`

İç durumu bayrakları hakkında daha fazla bilgi için bkz. [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

İç durumu bayrak işlev hiçbir öğe ayıklar, *olduğu* ayarlanır `ios_base::failbit`. Her iki durumda da `getline` döndürür *olduğu*.

Bir özel durum oluşturulursa *olduğu* ve *str* geçerli bir durumda bırakılır.

### <a name="example"></a>Örnek

Aşağıdaki kodda `getline()` iki modda: varsayılan sınırlayıcı (yeni satır) ile ilk ve ikinci bir boşluk olarak sınırlayıcı ile. Dosya sonu karakteri (CTRL-Z klavyedeki) while sonlandırma denetlemek için kullanılan döngüleri. Bu, iç durumu bayrağını ayarlar `cin` için `eofbit`, hangi işaretinin kaldırılması gerekir ile [basic_ios::clear()](../standard-library/basic-ios-class.md#clear) döngü düzgün çalışması sırasında saniye önce.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}

```

## <a name="stod"></a>  stod

Bir karakter dizisine dönüştürür bir **çift**.

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|İlk Dönüştürülmeyen karakter dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

**Çift** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür bir dizi öğelerinde *str* bir değere `val` türü **çift** buf `strtod( str.c_str(), _Eptr)`burada `_Eptr` bir iç işleve bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stof"></a>  stof

Bir kayan nokta bir karakter dizisine dönüştürür.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|İlk Dönüştürülmeyen karakter dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

Kayan nokta değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür bir dizi öğelerinde *str* bir değere `val` türü **float** buf `strtof( str.c_str(), _Eptr)`burada `_Eptr` bir iç işleve bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoi"></a>  stoi

Bir karakter dizisine bir tamsayıya dönüştürür.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>Dönüş Değeri

Tamsayı değeri.

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|Geri dönüş Dönüştürülmeyen ilk karakter dizinini içerir.|
|*base*|Kullanılacak sayı tabanı.|

### <a name="remarks"></a>Açıklamalar

İşlev `stoi` karakter dizisini dönüştürür *str* türünde bir değer için **int** ve değeri döndürür. Örneğin, bir karakter dizisi "10" geçirildiğinde, değer tarafından döndürülen `stoi` 10 tamsayıdır.

`stoi` işlevine benzer şekilde davranır `strtol` şekilde çağrıldığında tek baytlı karakterler için `strtol( str.c_str(), _Eptr, idx)`burada `_Eptr` bir nesnedir; işlevin iç veya `wcstol` benzer şekilde, çağrıldığında geniş karakterler için `wcstol(Str.c_str(), _Eptr, idx)`. Daha fazla bilgi için [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Varsa `str.c_str() == *_Eptr`, `stoi` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, veya döndürülen değer türünün bir nesnesi olarak temsil edilemiyorsa **int**, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr - str.c_str()` içinde `*idx`.

## <a name="stol"></a>  stol

Bir karakter dizisine dönüştürür bir **uzun**.

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|İlk Dönüştürülmeyen karakter dizin değeri.|
|*base*|Kullanılacak sayı tabanı.|

### <a name="return-value"></a>Dönüş Değeri

Tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür bir dizi öğelerinde *str* bir değere `val` türü **uzun** buf `strtol( str.c_str(), _Eptr, idx)`burada `_Eptr` bir iç işleve bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stold"></a>  stold

Bir karakter dizisine dönüştürür bir **uzun çift**.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|İlk Dönüştürülmeyen karakter dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

**Uzun çift** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür bir dizi öğelerinde *str* bir değere `val` türü **uzun çift** buf `strtold( str.c_str(), _Eptr)`burada `_Eptr` bir iç işleve bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoll"></a>  stoll

Bir karakter dizisine dönüştürür bir **uzun uzun**.

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|İlk Dönüştürülmeyen karakter dizin değeri.|
|*base*|Kullanılacak sayı tabanı.|

### <a name="return-value"></a>Dönüş Değeri

**Uzun uzun** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür bir dizi öğelerinde *str* bir değere `val` türü **uzun uzun** buf `strtoll( str.c_str(), _Eptr, idx)`burada `_Eptr` bir iç işleve bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoul"></a>  stoul

İşaretsiz bir bir karakter dizisine dönüştürür uzun.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|İlk Dönüştürülmeyen karakter dizin değeri.|
|*base*|Kullanılacak sayı tabanı.|

### <a name="return-value"></a>Dönüş Değeri

İşaretsiz uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür bir dizi öğelerinde *str* bir değere `val` türü **işaretsiz uzun** buf `strtoul( str.c_str(), _Eptr, idx)`burada `_Eptr` bir iç işleve bir nesnedir . Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoull"></a>  stoull

Bir karakter dizisine dönüştürür bir **işaretsiz long long**.

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*str*|Dönüştürülecek karakter dizisi.|
|*IDX*|İlk Dönüştürülmeyen karakter dizin değeri.|
|*base*|Kullanılacak sayı tabanı.|

### <a name="return-value"></a>Dönüş Değeri

**İşaretsiz long long** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür bir dizi öğelerinde *str* bir değere `val` türü **işaretsiz long long** buf `strtoull( str.c_str(), _Eptr, idx)`burada `_Eptr` bir nesne için dahili kullanım içindir işlev. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Böyle bir çağrı ayarlayabilir, `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi takdirde *IDX* null işaretçisiyse, işlev depoları değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="swap"></a>  değiştirme

İki dizenin karakter dizileri birbiriyle değiştirir.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Başka bir dizenin olanlar değiştirilecek öğeleri olan bir dize.

*sağ*<br/>
Öğeleri ilk dizeyle değiştirilecek olan dize.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevi şablonu işlevi yürütür *sol*.[ takas](../standard-library/basic-string-class.md#swap)(*doğru*) dizeler için garantileyen sabit karmaşası.

### <a name="example"></a>Örnek

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a>  to_string

Bir değere dönüştürür bir `string`.

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*VAL*|Dönüştürülecek değer.|

### <a name="return-value"></a>Dönüş Değeri

`string` Değeri temsil eden.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür *Val* dizi nesnesinde saklanan öğe sırasını `Buf` buf iç işleve `sprintf(Buf, Fmt, Val)`burada `Fmt` olduğu

- `"%d"` varsa `Val` türünde **int**

- `"%u"` varsa `Val` türünde **işaretsiz int**

- `"%ld"` varsa `Val` türünde **uzun**

- `"%lu"` varsa `Val` türünde **işaretsiz uzun**

- `"%lld"` varsa `Val` türünde **uzun uzun**

- `"%llu"` varsa `Val` türünde **işaretsiz long long**

- `"%f"` varsa `Val` türünde **float** veya **çift**

- `"%Lf"` varsa `Val` türünde **uzun çift**

İşlev döndürür `string(Buf)`.

## <a name="to_wstring"></a>  to_wstring

Bir değeri geniş dizeye dönüştürür.

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Val`|Dönüştürülecek değer.|

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden geniş dize.

### <a name="remarks"></a>Açıklamalar

İşlevi dönüştürür `Val` dizi nesnesinde saklanan öğe sırasını `Buf` buf iç işleve `swprintf(Buf, Len, Fmt, Val)`burada `Fmt` olduğu

- `L"%d"` varsa `Val` türünde **int**

- `L"%u"` varsa `Val` türünde **işaretsiz int**

- `L"%ld"` varsa `Val` türünde **uzun**

- `L"%lu"` varsa `Val` türünde **işaretsiz uzun**

- `L"%lld"` varsa `Val` türünde **uzun uzun**

- `L"%llu"` varsa `Val` türünde **işaretsiz long long**

- `L"%f"` varsa `Val` türünde **float** veya **çift**

- `L"%Lf"` varsa `Val` türünde **uzun çift**

İşlev döndürür `wstring(Buf)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)<br/>
