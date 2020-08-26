---
title: '&lt;dize &gt; işlevleri'
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
ms.openlocfilehash: 350a66481c7061322f08a768ec1628598f4af68e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843189"
---
# <a name="ltstringgt-functions"></a>&lt;dize &gt; işlevleri

[getline](#getline)\
[stod](#stod)\
[stof](#stof)\
[Stoi](#stoi)\
[STOL](#stol)\
[stold](#stold)\
[Stoll](#stoll)\
[stoul](#stoul)\
[stoull](#stoull)\
[Kur](#swap)\
[to_string](#to_string)\
[to_wstring](#to_wstring)

## <a name="getline"></a><a name="getline"></a> getline

Giriş akışı satır satırından dizeleri ayıkla.

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
Bir dizenin ayıklanabileceği giriş akışı.

*üstbilgisine*\
Giriş akışındaki karakterleri okuyan dize.

*ayırıcı*\
Satır sınırlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Giriş akışı *in_stream*.

### <a name="remarks"></a>Açıklamalar

`(1)` *Ayırıcı* bulunana kadar *in_stream* ayıklama karakterlerini işaretlenen işlev imzası çifti, bunları *Str*içinde depolar.

İşaretlenen işlev imzası çifti, `(2)` varsayılan satır sınırlayıcısı olarak yeni satırı kullanır ve gibi davranır `getline(in_stream, str, in_stream. widen('\n'))` .

Her bir çiftin ikinci işlevi, [Rvalue başvurularını](../cpp/lvalues-and-rvalues-visual-cpp.md)desteklemeye yönelik bir analog ' dur.

Aşağıdakilerden biri gerçekleştiğinde ayıklama işlemi duraklar:

- Dosyanın sonunda, *in_stream* iç durum bayrağı olarak ayarlanır `ios_base::eofbit` .

- İşlev, eşit *sınırlayıcıyla*karşılaştırılmış bir öğeyi ayıkladıktan sonra. Öğe, denetimli diziye geri yerleştirmez veya eklenmez.

- İşlev `str.` [max_size](../standard-library/basic-string-class.md#max_size) öğeleri ayıkladıktan sonra. *İn_stream* iç durum bayrağı olarak ayarlanır `ios_base::failbit` .

- Daha önce listelenenlerden farklı başka bir hata; *in_stream* iç durum bayrağı olarak ayarlanır `ios_base::badbit` .

İç durum bayrakları hakkında daha fazla bilgi için bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate).

İşlev hiçbir öğe ayıkladıysanız, *in_stream* iç durum bayrağı olarak ayarlanır `ios_base::failbit` . Herhangi bir durumda `getline` *in_stream*döndürür.

Bir özel durum oluşturulursa, *in_stream* ve *Str* geçerli bir durumda bırakılır.

### <a name="example"></a>Örnek

Aşağıdaki kod `getline()` iki modda göstermektedir: ilk olarak varsayılan sınırlayıcıyla (yeni satır) ve ikincisi sınırlayıcı olarak boşluk ile. While döngülerinin sonlandırılmasını denetlemek için dosya sonu karakteri (klavyede CTRL-Z) kullanılır. Bu değer, ' ın iç durum bayrağını `cin` `eofbit` , ikinci while döngüsünün düzgün şekilde çalışması için, [basic_ios:: Clear ()](../standard-library/basic-ios-class.md#clear) ile temizlenmelidir.

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

## <a name="stod"></a><a name="stod"></a> stod

Bir karakter dizisini öğesine dönüştürür **`double`** .

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

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

**`double`** Değer.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, **`double`** çağırarak `strtod( str.c_str(), _Eptr)` , `_Eptr` işlevinin iç bir nesnesi olduğu gibi, öğesini çağırarak bir değere dönüştürür. İse `str.c_str() == *_Eptr` , türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanacaksa `errno` , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi ' `*_Eptr -  str.c_str()` de depolar `*idx` ve değeri döndürür.

## <a name="stof"></a><a name="stof"></a> stof

Bir karakter dizisini float öğesine dönüştürür.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

**`float`** Değer.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, **`float`** çağırarak `strtof( str.c_str(), _Eptr)` , `_Eptr` işlevinin iç bir nesnesi olduğu gibi, öğesini çağırarak bir değere dönüştürür. İse `str.c_str() == *_Eptr` , türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanacaksa `errno` , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi ' `*_Eptr -  str.c_str()` de depolar `*idx` ve değeri döndürür.

## <a name="stoi"></a><a name="stoi"></a> Stoi

Bir karakter dizisini tamsayıya dönüştürür.

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

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="remarks"></a>Açıklamalar

İşlevi `stoi` *Str* içindeki karakter dizisini türünde bir değere dönüştürür **`int`** ve değeri döndürür. Örneğin, "10" karakter sırası geçirildiğinde, tarafından döndürülen değer `stoi` 10 ' dur.

`stoi` , `strtol` işlev içinde çağrıldığında tek baytlık karakterlerin işlevine benzer şekilde davranır `strtol( str.c_str(), _Eptr, idx)` `_Eptr` ; Bu, işlevin iç bir nesnesidir; ya da `wcstol` benzer biçimde çağrıldığında çok sayıda karakter için `wcstol(Str.c_str(), _Eptr, idx)` . Daha fazla bilgi için bkz. [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

İse `str.c_str() == *_Eptr` , `stoi` türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanır `errno` veya döndürülen değer türünde bir nesne olarak temsil edimiyorsa **`int`** , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi `*_Eptr - str.c_str()` ' de depolar `*idx` .

## <a name="stol"></a><a name="stol"></a> STOL

Bir karakter dizisini öğesine dönüştürür **`long`** .

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

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

Uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, **`long`** çağırarak `strtol( str.c_str(), _Eptr, idx)` , `_Eptr` işlevinin iç bir nesnesi olduğu gibi, öğesini çağırarak bir değere dönüştürür. İse `str.c_str() == *_Eptr` , türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanacaksa `errno` , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi ' `*_Eptr -  str.c_str()` de depolar `*idx` ve değeri döndürür.

## <a name="stold"></a><a name="stold"></a> stold

Bir karakter dizisini öğesine dönüştürür **`long double`** .

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

**`long double`** Değer.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, **`long double`** çağırarak `strtold( str.c_str(), _Eptr)` , `_Eptr` işlevinin iç bir nesnesi olduğu gibi, öğesini çağırarak bir değere dönüştürür. İse `str.c_str() == *_Eptr` , türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanacaksa `errno` , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi ' `*_Eptr -  str.c_str()` de depolar `*idx` ve değeri döndürür.

## <a name="stoll"></a><a name="stoll"></a> Stoll

Bir karakter dizisini öğesine dönüştürür **`long long`** .

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

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

**`long long`** Değer.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, **`long long`** çağırarak `strtoll( str.c_str(), _Eptr, idx)` , `_Eptr` işlevinin iç bir nesnesi olduğu gibi, öğesini çağırarak bir değere dönüştürür. İse `str.c_str() == *_Eptr` , türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanacaksa `errno` , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi ' `*_Eptr -  str.c_str()` de depolar `*idx` ve değeri döndürür.

## <a name="stoul"></a><a name="stoul"></a> stoul

Bir karakter dizisini işaretsiz bir Long değerine dönüştürür.

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

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

İşaretsiz uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, **`unsigned long`** çağırarak `strtoul( str.c_str(), _Eptr, idx)` , `_Eptr` işlevinin iç bir nesnesi olduğu gibi, öğesini çağırarak bir değere dönüştürür. İse `str.c_str() == *_Eptr` , türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanacaksa `errno` , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi ' `*_Eptr -  str.c_str()` de depolar `*idx` ve değeri döndürür.

## <a name="stoull"></a><a name="stoull"></a> stoull

Bir karakter dizisini bir öğesine dönüştürür **`unsigned long long`** .

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

*üstbilgisine*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

**`unsigned long long`** Değer.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, **`unsigned long long`** çağırarak `strtoull( str.c_str(), _Eptr, idx)` , `_Eptr` işlevinin iç bir nesnesi olduğu gibi, öğesini çağırarak bir değere dönüştürür. İse `str.c_str() == *_Eptr` , türünde bir nesne oluşturur `invalid_argument` . Böyle bir çağrı ayarlanacaksa `errno` , türünde bir nesne oluşturur `out_of_range` . Aksi halde, *idx* null bir işaretçi değilse, işlevi ' `*_Eptr -  str.c_str()` de depolar `*idx` ve değeri döndürür.

## <a name="swap"></a><a name="swap"></a> Kur

İki dizenin karakter dizilerini değiş tokuş eder.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri başka bir dizenin öğeleriyle birlikte takas edilecek bir dize.

*Right*\
Öğeleri ilk dizeyle takas edilecek diğer dize.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, *sol taraftaki*özelleştirilmiş üye işlevini yürütür. Sabit karmaşıklığı garanti eden dizeler için [takas](../standard-library/basic-string-class.md#swap)(*sağ*).

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

## <a name="to_string"></a><a name="to_string"></a> to_string

Bir değeri öğesine dönüştürür `string` .

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

*deeri*\
Dönüştürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

`string`Değeri temsil eder.

### <a name="remarks"></a>Açıklamalar

İşlevi, öğesini *value* çağırarak bir Array nesnesinde depolanan bir öğe dizisine `Buf` `sprintf(Buf, Fmt, value)` , `Fmt`

- `"%d"`*değer* tür ise**`int`**

- `"%u"`*değer* tür ise**`unsigned int`**

- `"%ld"`*değer* tür ise**`long`**

- `"%lu"`*değer* tür ise**`unsigned long`**

- `"%lld"`*değer* tür ise**`long long`**

- `"%llu"`*değer* tür ise**`unsigned long long`**

- `"%f"`*değer* tür ise **`float`** veya**`double`**

- `"%Lf"`*değer* tür ise**`long double`**

İşlev döndürür `string(Buf)` .

## <a name="to_wstring"></a><a name="to_wstring"></a> to_wstring

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

*deeri*\
Dönüştürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden geniş dize.

### <a name="remarks"></a>Açıklamalar

İşlevi, öğesini *value* çağırarak bir Array nesnesinde depolanan bir öğe dizisine `Buf` `swprintf(Buf, Len, Fmt, value)` , `Fmt`

- `L"%d"`*değer* tür ise**`int`**

- `L"%u"`*değer* tür ise**`unsigned int`**

- `L"%ld"`*değer* tür ise**`long`**

- `L"%lu"`*değer* tür ise**`unsigned long`**

- `L"%lld"`*değer* tür ise**`long long`**

- `L"%llu"`*değer* tür ise**`unsigned long long`**

- `L"%f"`*değer* tür ise **`float`** veya**`double`**

- `L"%Lf"`*değer* tür ise**`long double`**

İşlev döndürür `wstring(Buf)` .

## <a name="see-also"></a>Ayrıca bkz.

[\<string>](../standard-library/string.md)
