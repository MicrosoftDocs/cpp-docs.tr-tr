---
title: '&lt;dize&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 0089a7259601b766bff3b470c5ba23c1b9952fb6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862679"
---
# <a name="ltstringgt-functions"></a>&lt;dize&gt; işlevleri

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[Değiştirme](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>  getline

Dizeleri Giriş akışı satır-tarafından-satırından ayıklayın.

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

`is` Bir dize ayıklanacak olduğu giriş akışı.

`str` Karakterleri giriş akışından okuma dizesi.

`delim` Satır sınırlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Giriş akışı `is`.

### <a name="remarks"></a>Açıklamalar

İşlev imzalarında çiftinin işaretlenmiş `(1)` karakterlerinden ayıklamak `is` kadar `delim` bulunamadı, bunları depolamak `str`.

İşlev imzalarında çiftinin işaretlenmiş `(2)` olarak davranır ve varsayılan satır ayırıcı olarak yeni satır kullanın **getline**( `is`, `str`, `is`. `widen`(' `\n`')).

İkinci her çiftinin bir analog desteklemek için ilk bir işlevdir [rvalue başvuru](../cpp/lvalues-and-rvalues-visual-cpp.md).

Aşağıdakilerden biri oluştuğunda ayıklama durdurur:

- En son dosya, iç durum bayrak; bu durumda `is` ayarlanır `ios_base::eofbit`.

- Eşit karşılaştıran bir öğe işlevi ayıklar sonra **delim**, bu durumda öğesi ne geri alın, ne de denetimli dizisi eklenmiş.

- İşlev ayıklar sonra `str.` [max_size](../standard-library/basic-string-class.md#max_size) , öğeleri durumda iç durum bayrağı `is` ayarlanır `ios_base::failbit`.

- Başka bir hata olanlar dışındaki daha önce listelenen, iç durum bayrak; bu durumda `is` ayarlanır `ios_base::badbit`

İç durumu bayrakları hakkında daha fazla bilgi için bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Öğe işlevi ayıklar, iç durum bayrak `is` ayarlanır `ios_base::failbit`. Her iki durumda da `getline` döndürür `is`.

Bir özel durum, `is` ve `str` geçerli bir durumda bırakılır.

### <a name="example"></a>Örnek

Aşağıdaki kodda `getline()` iki modda: ilk varsayılan sınırlayıcı (yeni satır) ile ikinci ayırıcısı olarak boşluk. Dosya sonu karakteri (CTRL-Z klavyedeki) while sonlandırılması denetlemek için kullanılan döngüler. Bu, iç durum bayrağını ayarlar `cin` için `eofbit`, hangi gerekir temizlenmiş ile [basic_ios::clear()](../standard-library/basic-ios-class.md#clear) döngü düzgün çalışması sırasında ikinci önce.

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

Bir karakter dizisi dönüştüren bir `double`.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|İlk Dönüştürülmeyen karakter dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

`double` Değeri.

### <a name="remarks"></a>Açıklamalar

Öğelerin sırasını işlevi dönüştürür `str` bir değere `val` türü `double` göre çağırma sanki `strtod( str.c_str(), _Eptr)`, burada `_Eptr` bir işlev için dahili bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stof"></a>  stof

Bir karakter dizisi kayana dönüştürür.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|İlk Dönüştürülmeyen karakter dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

Float değeri.

### <a name="remarks"></a>Açıklamalar

Öğelerin sırasını işlevi dönüştürür `str` bir değere `val` türü `float` göre çağırma sanki `strtof( str.c_str(), _Eptr)`, burada `_Eptr` bir işlev için dahili bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoi"></a>  stoi

Bir karakter dizisi bir tamsayıya dönüştürür.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|Geri dönüş Dönüştürülmeyen ilk karakter dizinini içerir.|
|`base`|Kullanılacak sayı temel.|

### <a name="remarks"></a>Açıklamalar

İşlev `stoi` karakter dizisi dönüştürür `str` türünde bir değer için `int` ve değeri döndürür. Örneğin, bir karakter dizisi "10" geçirildiğinde değeri döndürdü `stoi` 10 tamsayıdır.

`stoi` işlevine benzer şekilde davranır `strtol` şekilde çağrıldığında tek baytlı karakterler `strtol( str.c_str(), _Eptr, idx)`, burada `_Eptr` bir işleve; iç nesnedir veya `wcstol` benzer şekilde, çağrıldığında geniş karakterler `wcstol(Str.c_str(), _Eptr, idx)`. Daha fazla bilgi için bkz: [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Varsa `str.c_str() == *_Eptr`, `stoi` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, veya döndürülen değer türünde bir nesne gösterilemezse `int`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr - str.c_str()` içinde `*idx`.

## <a name="stol"></a>  stol

Bir karakter dizisi dönüştüren bir `long`.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|İlk Dönüştürülmeyen karakter dizin değeri.|
|`base`|Kullanılacak sayı temel.|

### <a name="return-value"></a>Dönüş Değeri

Uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Öğelerin sırasını işlevi dönüştürür `str` bir değere `val` türü `long` göre çağırma sanki `strtol( str.c_str(), _Eptr, idx)`, burada `_Eptr` bir işlev için dahili bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stold"></a>  stold

Bir karakter dizisi dönüştüren bir `long double`.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|İlk Dönüştürülmeyen karakter dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

`long double` Değeri.

### <a name="remarks"></a>Açıklamalar

Öğelerin sırasını işlevi dönüştürür `str` bir değere `val` türü `long double` göre çağırma sanki `strtold( str.c_str(), _Eptr)`, burada `_Eptr` bir işlev için dahili bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoll"></a>  stoll

Bir karakter dizisi dönüştüren bir `long long`.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|İlk Dönüştürülmeyen karakter dizin değeri.|
|`base`|Kullanılacak sayı temel.|

### <a name="return-value"></a>Dönüş Değeri

`long long` Değeri.

### <a name="remarks"></a>Açıklamalar

Öğelerin sırasını işlevi dönüştürür `str` bir değere `val` türü `long long` göre çağırma sanki `strtoll( str.c_str(), _Eptr, idx)`, burada `_Eptr` bir işlev için dahili bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoul"></a>  stoul

Bir karakter dizisi imzasız bir dönüştürür uzun.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|İlk Dönüştürülmeyen karakter dizin değeri.|
|`base`|Kullanılacak sayı temel.|

### <a name="return-value"></a>Dönüş Değeri

İmzasız long tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Öğelerin sırasını işlevi dönüştürür `str` bir değere `val` türü `unsigned long` göre çağırma sanki `strtoul( str.c_str(), _Eptr, idx)`, burada `_Eptr` bir işlev için dahili bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="stoull"></a>  stoull

Bir karakter dizisi dönüştüren bir `unsigned long long`.

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
|`str`|Dönüştürülecek karakter dizisi.|
|`idx`|İlk Dönüştürülmeyen karakter dizin değeri.|
|`base`|Kullanılacak sayı temel.|

### <a name="return-value"></a>Dönüş Değeri

`unsigned long long` Değeri.

### <a name="remarks"></a>Açıklamalar

Öğelerin sırasını işlevi dönüştürür `str` bir değere `val` türü `unsigned long long` göre çağırma sanki `strtoull( str.c_str(), _Eptr, idx)`, burada `_Eptr` bir işlev için dahili bir nesnedir. Varsa ` str.c_str() == *_Eptr` türünde bir nesne oluşturur `invalid_argument`. Bu tür bir çağrı ayarlarsanız `errno`, türünde bir nesne oluşturur `out_of_range`. Aksi halde, eğer `idx` işlevi depoları null işaretçi değil `*_Eptr -  str.c_str()` içinde `*idx` ve döndürür `val`.

## <a name="swap"></a>  Değiştirme

İki dizeyi karakter dizilerine değiş tokuş eder.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Başka bir dize olanlar gerek öğeleri olan bir dize.

`right` İlk dizesini takas için öğeleri olan bir dize.

### <a name="remarks"></a>Açıklamalar

Özel üye fonksiyonu şablon işlevi yürütür *sol*.[ takas](../standard-library/basic-string-class.md#swap)(*sağ*) dizeleri için hangi garanti sabit karmaşıklık.

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

Bir değerine dönüştürür bir `string`.

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
|`Val`|Dönüştürülecek değer.|

### <a name="return-value"></a>Dönüş Değeri

`string` Değerini temsil eder.

### <a name="remarks"></a>Açıklamalar

İşlev dönüştürür `Val` bir dizi nesnesindeki öğelerin sırasını `Buf` göre çağırma gibi iç işlevine `sprintf(Buf, Fmt, Val)`, burada `Fmt` olduğu

- `"%d"` varsa `Val` türüne sahip `int`

- `"%u"` varsa `Val` türüne sahip `unsigned int`

- `"%ld"` varsa `Val` türüne sahip `long`

- `"%lu"` varsa `Val` türüne sahip `unsigned long`

- `"%lld"` varsa `Val` türüne sahip `long long`

- `"%llu"` varsa `Val` türüne sahip `unsigned long long`

- `"%f"` varsa `Val` türüne sahip `float` veya `double`

- `"%Lf"` varsa `Val` türüne sahip `long double`

İşlevi döndürür `string(Buf)`.

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

İşlev dönüştürür `Val` bir dizi nesnesindeki öğelerin sırasını `Buf` göre çağırma gibi iç işlevine `swprintf(Buf, Len, Fmt, Val)`, burada `Fmt` olduğu

- `L"%d"` varsa `Val` türüne sahip `int`

- `L"%u"` varsa `Val` türüne sahip `unsigned int`

- `L"%ld"` varsa `Val` türüne sahip `long`

- `L"%lu"` varsa `Val` türüne sahip `unsigned long`

- `L"%lld"` varsa `Val` türüne sahip `long long`

- `L"%llu"` varsa `Val` türüne sahip `unsigned long long`

- `L"%f"` varsa `Val` türüne sahip `float` veya `double`

- `L"%Lf"` varsa `Val` türüne sahip `long double`

İşlevi döndürür `wstring(Buf)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)<br/>
