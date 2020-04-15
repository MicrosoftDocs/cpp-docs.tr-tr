---
title: '&lt;dize&gt; fonksiyonları'
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
ms.openlocfilehash: 3f1dca71a6bb9d5461150378191b9373f907ecd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376655"
---
# <a name="ltstringgt-functions"></a>&lt;dize&gt; fonksiyonları

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[Stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[Stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[Takas](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a><a name="getline"></a>getline

Giriş akışı satır satır dizeleri ayıklayın.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delimiter);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delimiter);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& in_stream,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*in_stream*\
Bir dize ayıklanacak giriş akışı.

*Str*\
Giriş akışındaki karakterleri okunan dize.

*Sınırlayıcı*\
Çizgi delimiter.

### <a name="return-value"></a>Dönüş Değeri

Giriş akışı *in_stream.*

### <a name="remarks"></a>Açıklamalar

İşlev `(1)` imzaları *çifti, in_stream* gelen eserin *delimiter* bulunana kadar ayıklama karakterlerini işaretleyerek *str'de*depolanır.

İşaretli `(2)` işlev imzaçifti varsayılan satır delimiter olarak yeni satır `getline(in_stream, str, in_stream. widen('\n'))`kullanın ve .

Her çiftin ikinci [işlevi, rvalue başvurularını](../cpp/lvalues-and-rvalues-visual-cpp.md)destekleyen ilk intörüne analogdur.

Aşağıdakilerden biri oluştuğunda çıkarma durur:

- Dosyanın sonunda, bu durumda *in_stream* iç durum bayrağı `ios_base::eofbit`ayarlanır.

- Fonksiyon *delimiter*eşit bir öğe ayıklar sonra . Öğe geri konulmaz veya kontrollü sıraya eklenmiyor.

- Fonksiyon sonra `str.` [max_size](../standard-library/basic-string-class.md#max_size) elemanları ayıklar. *in_stream* iç durum bayrağı `ios_base::failbit`ayarlanır.

- Daha önce listelenenler dışında başka bir hata; *in_stream* iç devlet bayrağı `ios_base::badbit`ayarlanır.

İç durum bayrakları hakkında bilgi için [bkz: ios_base:iostate](../standard-library/ios-base-class.md#iostate).

İşlev hiçbir öğeyi ayıklamazsa, *in_stream* iç `ios_base::failbit`durum bayrağı . Her durumda, `getline` *in_stream*döndürür.

Bir özel durum atılırsa, *in_stream* ve *str* geçerli bir durumda bırakılır.

### <a name="example"></a>Örnek

Aşağıdaki kod iki `getline()` modda gösterir: ilk varsayılan delimiter (newline) ve delimiter olarak bir beyaz boşluk ile ikinci. Dosya sonu karakteri (klavyedeki CTRL-Z) while döngülerinin sonlandırılmasını denetlemek için kullanılır. Bu `eofbit`değer, döngü düzgün `cin` çalışırken ikinciden önce [basic_ios::clear()](../standard-library/basic-ios-class.md#clear) ile temizlenmesi gereken iç durum bayrağını ayarlar.

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

## <a name="stod"></a><a name="stod"></a>stod

Karakter dizisini bir **`double`**.

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

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Değeri. **`double`**

### <a name="remarks"></a>Açıklamalar

İşlev, *str'deki* öğelerin dizisini, **`double`** işlevin iç `strtod( str.c_str(), _Eptr)`sel `_Eptr` olduğu bir nesne nin bulunduğu yeri çağırarak sanki bir tür değerine dönüştürür. Eğer, `str.c_str() == *_Eptr`bir tür `invalid_argument`nesne atar. Böyle bir çağrı `errno`ayarlanırsa, bir tür `out_of_range`nesne atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr -  str.c_str()` `*idx` işlev depolar ve değeri döndürür.

## <a name="stof"></a><a name="stof"></a>stof

Karakter dizisini float'a dönüştürür.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Değeri. **`float`**

### <a name="remarks"></a>Açıklamalar

İşlev, *str'deki* öğelerin dizisini, **`float`** işlevin iç `strtof( str.c_str(), _Eptr)`sel `_Eptr` olduğu bir nesne nin bulunduğu yeri çağırarak sanki bir tür değerine dönüştürür. Eğer, `str.c_str() == *_Eptr`bir tür `invalid_argument`nesne atar. Böyle bir çağrı `errno`ayarlanırsa, bir tür `out_of_range`nesne atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr -  str.c_str()` `*idx` işlev depolar ve değeri döndürür.

## <a name="stoi"></a><a name="stoi"></a>Stoi

Karakter dizisini tamsayıya dönüştürür.

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

Sonda değeri.

### <a name="parameters"></a>Parametreler

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

*Temel*\
Kullanılacak sayı tabanı.

### <a name="remarks"></a>Açıklamalar

İşlev `stoi` *str'deki* karakter dizisini bir tür **`int`** değerine dönüştürür ve değeri döndürür. Örneğin, bir karakter dizisi "10" geçirildiğinde, `stoi` döndürülen değer tamsayı 10'dur.

`stoi`şekilde `strtol` `strtol( str.c_str(), _Eptr, idx)`çağrıldığında tek bayt karakterler için işleve benzer şekilde çalışır , `_Eptr` işlevi için bir nesne iç olduğu; ya `wcstol` da geniş karakterler için, benzer şekilde `wcstol(Str.c_str(), _Eptr, idx)`çağrıldığında, . Daha fazla bilgi için [strtol, wcstol, _strtol_l, _wcstol_l.](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)

`str.c_str() == *_Eptr`Eğer, `stoi` türünde `invalid_argument`bir nesne atar. Böyle bir çağrı `errno`ayarlanırsa veya döndürülen değer bir tür **`int`** nesnesi olarak temsil edilenemezse, bir tür `out_of_range`nesnesi atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr - str.c_str()` `*idx`işlev .

## <a name="stol"></a><a name="stol"></a>stol

Karakter dizisini bir **`long`**.

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

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

*Temel*\
Kullanılacak sayı tabanı.

### <a name="return-value"></a>Dönüş Değeri

Uzun sonda değeri.

### <a name="remarks"></a>Açıklamalar

İşlev, *str'deki* öğelerin dizisini, **`long`** işlevin iç `strtol( str.c_str(), _Eptr, idx)`sel `_Eptr` olduğu bir nesne nin bulunduğu yeri çağırarak sanki bir tür değerine dönüştürür. Eğer, `str.c_str() == *_Eptr`bir tür `invalid_argument`nesne atar. Böyle bir çağrı `errno`ayarlanırsa, bir tür `out_of_range`nesne atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr -  str.c_str()` `*idx` işlev depolar ve değeri döndürür.

## <a name="stold"></a><a name="stold"></a>stold

Karakter dizisini bir **`long double`**.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Değeri. **`long double`**

### <a name="remarks"></a>Açıklamalar

İşlev, *str'deki* öğelerin dizisini, **`long double`** işlevin iç `strtold( str.c_str(), _Eptr)`sel `_Eptr` olduğu bir nesne nin bulunduğu yeri çağırarak sanki bir tür değerine dönüştürür. Eğer, `str.c_str() == *_Eptr`bir tür `invalid_argument`nesne atar. Böyle bir çağrı `errno`ayarlanırsa, bir tür `out_of_range`nesne atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr -  str.c_str()` `*idx` işlev depolar ve değeri döndürür.

## <a name="stoll"></a><a name="stoll"></a>Stoll

Karakter dizisini bir **`long long`**.

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

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

*Temel*\
Kullanılacak sayı tabanı.

### <a name="return-value"></a>Dönüş Değeri

Değeri. **`long long`**

### <a name="remarks"></a>Açıklamalar

İşlev, *str'deki* öğelerin dizisini, **`long long`** işlevin iç `strtoll( str.c_str(), _Eptr, idx)`sel `_Eptr` olduğu bir nesne nin bulunduğu yeri çağırarak sanki bir tür değerine dönüştürür. Eğer, `str.c_str() == *_Eptr`bir tür `invalid_argument`nesne atar. Böyle bir çağrı `errno`ayarlanırsa, bir tür `out_of_range`nesne atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr -  str.c_str()` `*idx` işlev depolar ve değeri döndürür.

## <a name="stoul"></a><a name="stoul"></a>stoul

Karakter dizisini imzasız uzuna dönüştürür.

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

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

*Temel*\
Kullanılacak sayı tabanı.

### <a name="return-value"></a>Dönüş Değeri

İmzalanmamış uzun tümseci değeri.

### <a name="remarks"></a>Açıklamalar

İşlev, *str'deki* öğelerin dizisini, **`unsigned long`** işlevin iç `strtoul( str.c_str(), _Eptr, idx)`sel `_Eptr` olduğu bir nesne nin bulunduğu yeri çağırarak sanki bir tür değerine dönüştürür. Eğer, `str.c_str() == *_Eptr`bir tür `invalid_argument`nesne atar. Böyle bir çağrı `errno`ayarlanırsa, bir tür `out_of_range`nesne atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr -  str.c_str()` `*idx` işlev depolar ve değeri döndürür.

## <a name="stoull"></a><a name="stoull"></a>stoull

Karakter dizisini bir **`unsigned long long`**.'e dönüştürür

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

*Str*\
Dönüştürülecek karakter dizisi.

*ıdx*\
Dönüştürülmemiş ilk karakterin dizin değeri.

*Temel*\
Kullanılacak sayı tabanı.

### <a name="return-value"></a>Dönüş Değeri

Değeri. **`unsigned long long`**

### <a name="remarks"></a>Açıklamalar

İşlev, *str'deki* öğelerin dizisini, **`unsigned long long`** işlevin iç `strtoull( str.c_str(), _Eptr, idx)`sel `_Eptr` olduğu bir nesne nin bulunduğu yeri çağırarak sanki bir tür değerine dönüştürür. Eğer, `str.c_str() == *_Eptr`bir tür `invalid_argument`nesne atar. Böyle bir çağrı `errno`ayarlanırsa, bir tür `out_of_range`nesne atar. Aksi takdirde, *idx* null işaretçi değilse, `*_Eptr -  str.c_str()` `*idx` işlev depolar ve değeri döndürür.

## <a name="swap"></a><a name="swap"></a>Takas

İki dizekarakter dizilerini değiştirir.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Öğeleri başka bir dize öğeleri ile takas edilecek olan bir dize.

*Doğru*\
Öğeleri ilk dize ile değiştirilecek olan diğer dize.

### <a name="remarks"></a>Açıklamalar

Şablon *işlevi, soldaki*özel üye işlevini yürütür. [sabit](../standard-library/basic-string-class.md#swap)karmaşıklığı garanti eden dizeleri için takas (*sağ).*

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

## <a name="to_string"></a><a name="to_string"></a>to_string

Bir değeri bir `string`.

```cpp
string to_string(int value);
string to_string(unsigned int value);
string to_string(long value);
string to_string(unsigned long value);
string to_string(long long value);
string to_string(unsigned long long value);
string to_string(float value);
string to_string(double value);
string to_string(long double value);
```

### <a name="parameters"></a>Parametreler

*Değer*\
Dönüştürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

Değeri `string` temsil eden değer.

### <a name="remarks"></a>Açıklamalar

İşlev, *değeri,* bir dizi nesnesi `Buf` içinde depolanan bir öğe `sprintf(Buf, Fmt, value)`dizisine, işlevi arayarak , nerede olduğunu `Fmt`

- `"%d"`*değer* türde ise**`int`**

- `"%u"`*değer* türde ise**`unsigned int`**

- `"%ld"`*değer* türde ise**`long`**

- `"%lu"`*değer* türde ise**`unsigned long`**

- `"%lld"`*değer* türde ise**`long long`**

- `"%llu"`*değer* türde ise**`unsigned long long`**

- `"%f"`*değer* türünde **`float`** ise veya**`double`**

- `"%Lf"`*değer* türde ise**`long double`**

İşlev `string(Buf)`döndürür.

## <a name="to_wstring"></a><a name="to_wstring"></a>to_wstring

Bir değeri geniş dizeye dönüştürür.

```cpp
wstring to_wstring(int value);
wstring to_wstring(unsigned int value);
wstring to_wstring(long value);
wstring to_wstring(unsigned long value);
wstring to_wstring(long long value);
wstring to_wstring(unsigned long long value);
wstring to_wstring(float value);
wstring to_wstring(double value);
wstring to_wstring(long double value);
```

### <a name="parameters"></a>Parametreler

*Değer*\
Dönüştürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden geniş dize.

### <a name="remarks"></a>Açıklamalar

İşlev, *değeri,* bir dizi nesnesi `Buf` içinde depolanan bir öğe `swprintf(Buf, Len, Fmt, value)`dizisine, işlevi arayarak , nerede olduğunu `Fmt`

- `L"%d"`*değer* türde ise**`int`**

- `L"%u"`*değer* türde ise**`unsigned int`**

- `L"%ld"`*değer* türde ise**`long`**

- `L"%lu"`*değer* türde ise**`unsigned long`**

- `L"%lld"`*değer* türde ise**`long long`**

- `L"%llu"`*değer* türde ise**`unsigned long long`**

- `L"%f"`*değer* türünde **`float`** ise veya**`double`**

- `L"%Lf"`*değer* türde ise**`long double`**

İşlev `wstring(Buf)`döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize>](../standard-library/string.md)
