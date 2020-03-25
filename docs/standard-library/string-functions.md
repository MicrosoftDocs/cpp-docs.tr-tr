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
ms.openlocfilehash: dbcc4a86731bba092d8358a046fd3f9eb949f91f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214974"
---
# <a name="ltstringgt-functions"></a>&lt;dize&gt; işlevleri

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[Stoi](#stoi)|[STOL](#stol)|[stold](#stold)|
|[Stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[Kur](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a><a name="getline"></a>getline

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

*str*\
Giriş akışındaki karakterleri okuyan dize.

*sınırlayıcı*\
Satır sınırlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Giriş akışı *in_stream*.

### <a name="remarks"></a>Açıklamalar

*Ayırıcı* bulunana kadar *in_stream* karakter Ayıkla `(1)` işaretlenen işlev imzası çifti, bunları *Str*içinde depolar.

`(2)` işaretlenen işlev imzası çifti, varsayılan satır sınırlayıcısı olarak yeni satırı kullanır ve `getline(in_stream, str, in_stream. widen('\n'))`gibi davranır.

Her bir çiftin ikinci işlevi, [Rvalue başvurularını](../cpp/lvalues-and-rvalues-visual-cpp.md)desteklemeye yönelik bir analog ' dur.

Aşağıdakilerden biri gerçekleştiğinde ayıklama işlemi duraklar:

- Dosyanın sonunda, *in_stream* iç durum bayrağı `ios_base::eofbit`olarak ayarlanır.

- İşlev, eşit *sınırlayıcıyla*karşılaştırılmış bir öğeyi ayıkladıktan sonra. Öğe, denetimli diziye geri yerleştirmez veya eklenmez.

- İşlev `str.`[max_size](../standard-library/basic-string-class.md#max_size) öğelerini ayıkladıktan sonra. *İn_stream* iç durum bayrağı `ios_base::failbit`olarak ayarlanır.

- Daha önce listelenenlerden farklı başka bir hata; *in_stream* iç durum bayrağı `ios_base::badbit`olarak ayarlanır.

İç durum bayrakları hakkında daha fazla bilgi için bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate).

İşlev hiçbir öğe ayıkladıysanız, *in_stream* iç durum bayrağı `ios_base::failbit`olarak ayarlanır. Herhangi bir durumda, `getline` *in_stream*döndürür.

Bir özel durum oluşturulursa, *in_stream* ve *Str* geçerli bir durumda bırakılır.

### <a name="example"></a>Örnek

Aşağıdaki kod iki modda `getline()` gösterir: ilk olarak varsayılan sınırlayıcıyla (yeni satır) ve ikincisi sınırlayıcı olarak boşluk ile. While döngülerinin sonlandırılmasını denetlemek için dosya sonu karakteri (klavyede CTRL-Z) kullanılır. Bu değer, `cin` iç durum bayrağını `eofbit`olarak ayarlar; bu, ikinci while döngüsünün düzgün çalışması için önce [basic_ios:: Clear ()](../standard-library/basic-ios-class.md#clear) ile temizlenmelidir.

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

Bir karakter dizisini **`double`** dönüştürür.

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

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

**`double`** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtod( str.c_str(), _Eptr)`çağırarak **`double`** bir değere dönüştürür; burada `_Eptr` işlevin dahili bir nesnesidir. `str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve değeri döndürür.

## <a name="stof"></a><a name="stof"></a>stof

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

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

**`float`** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtof( str.c_str(), _Eptr)`çağırarak **`float`** bir değere dönüştürür; burada `_Eptr` işlevin dahili bir nesnesidir. `str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve değeri döndürür.

## <a name="stoi"></a><a name="stoi"></a>Stoi

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

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="remarks"></a>Açıklamalar

İşlevi `stoi` *Str* içindeki karakter dizisini **`int`** türünde bir değere dönüştürür ve değeri döndürür. Örneğin, "10" karakter dizisini geçtiğinde, `stoi` tarafından döndürülen değer 10 ' dur.

`stoi`, işlevin iç bir nesne olduğu `strtol( str.c_str(), _Eptr, idx)`şekilde çağrıldığında tek baytlı karakterler için `strtol` işlev `_Eptr` gibi davranır. ya da `wcstol` benzer şekilde çağrıldığında geniş karakterler için `wcstol(Str.c_str(), _Eptr, idx)`. Daha fazla bilgi için bkz. [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

`str.c_str() == *_Eptr`, `stoi` `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa veya döndürülen değer **`int`** türünde bir nesne olarak temsil edimiyorsa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx``*_Eptr - str.c_str()` depolar.

## <a name="stol"></a><a name="stol"></a>STOL

Bir karakter dizisini **`long`** dönüştürür.

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

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

Uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtol( str.c_str(), _Eptr, idx)`çağırarak **`long`** bir değere dönüştürür; burada `_Eptr` işlevin dahili bir nesnesidir. `str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve değeri döndürür.

## <a name="stold"></a><a name="stold"></a>stold

Bir karakter dizisini **`long double`** dönüştürür.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

**`long double`** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtold( str.c_str(), _Eptr)`çağırarak **`long double`** bir değere dönüştürür; burada `_Eptr` işlevin dahili bir nesnesidir. `str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve değeri döndürür.

## <a name="stoll"></a><a name="stoll"></a>Stoll

Bir karakter dizisini **`long long`** dönüştürür.

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

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

**`long long`** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtoll( str.c_str(), _Eptr, idx)`çağırarak **`long long`** bir değere dönüştürür; burada `_Eptr` işlevin dahili bir nesnesidir. `str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve değeri döndürür.

## <a name="stoul"></a><a name="stoul"></a>stoul

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

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

İşaretsiz uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtoul( str.c_str(), _Eptr, idx)`çağırarak **`unsigned long`** bir değere dönüştürür; burada `_Eptr` işlevin dahili bir nesnesidir. `str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve değeri döndürür.

## <a name="stoull"></a><a name="stoull"></a>stoull

Bir karakter dizisini bir **`unsigned long long`** dönüştürür.

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

*str*\
Dönüştürülecek karakter sırası.

*idx*\
İlk dönüştürülmemiş karakterin dizin değeri.

*temel*\
Kullanılacak sayı temeli.

### <a name="return-value"></a>Dönüş Değeri

**`unsigned long long`** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtoull( str.c_str(), _Eptr, idx)`çağırarak **`unsigned long long`** bir değere dönüştürür; burada `_Eptr` işlevin dahili bir nesnesidir. `str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve değeri döndürür.

## <a name="swap"></a><a name="swap"></a>Kur

İki dizenin karakter dizilerini değiş tokuş eder.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
Öğeleri başka bir dizenin öğeleriyle birlikte takas edilecek bir dize.

*sağ*\
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

## <a name="to_string"></a><a name="to_string"></a>to_string

Bir değeri `string`dönüştürür.

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

*değer*\
Dönüştürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden `string`.

### <a name="remarks"></a>Açıklamalar

İşlev *değeri* , `Fmt` olduğu gibi `sprintf(Buf, Fmt, value)`çağırarak işlevin iç `Buf` bir dizi nesnesinde depolanan öğelerin dizisine dönüştürür.

- *değer* tür ise `"%d"` **`int`**

- *değer* tür ise `"%u"` **`unsigned int`**

- *değer* tür ise `"%ld"` **`long`**

- *değer* tür ise `"%lu"` **`unsigned long`**

- *değer* tür ise `"%lld"` **`long long`**

- *değer* tür ise `"%llu"` **`unsigned long long`**

- *değer* **`float`** veya **`double`** türünde ise `"%f"`

- *değer* tür ise `"%Lf"` **`long double`**

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

*değer*\
Dönüştürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden geniş dize.

### <a name="remarks"></a>Açıklamalar

İşlev *değeri* , `Fmt` olduğu gibi `swprintf(Buf, Len, Fmt, value)`çağırarak işlevin iç `Buf` bir dizi nesnesinde depolanan öğelerin dizisine dönüştürür.

- *değer* tür ise `L"%d"` **`int`**

- *değer* tür ise `L"%u"` **`unsigned int`**

- *değer* tür ise `L"%ld"` **`long`**

- *değer* tür ise `L"%lu"` **`unsigned long`**

- *değer* tür ise `L"%lld"` **`long long`**

- *değer* tür ise `L"%llu"` **`unsigned long long`**

- *değer* **`float`** veya **`double`** türünde ise `L"%f"`

- *değer* tür ise `L"%Lf"` **`long double`**

İşlev `wstring(Buf)`döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)
