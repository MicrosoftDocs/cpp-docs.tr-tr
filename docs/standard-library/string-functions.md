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
ms.openlocfilehash: 828aeb975178850f5c0a7ea3b7e982bbadd6e7c4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455605"
---
# <a name="ltstringgt-functions"></a>&lt;dize&gt; işlevleri

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[Stoi](#stoi)|[STOL](#stol)|[stold](#stold)|
|[Stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[Kur](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>getline

Giriş akışı satır satırından dizeleri ayıkla.

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

*eklenir*\
Bir dizenin ayıklanabileceği giriş akışı.

*üstbilgisine*\
Giriş akışındaki karakterleri okuyan dize.

*delib*\
Satır sınırlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Giriş *akışı.*

### <a name="remarks"></a>Açıklamalar

' Den ayıklama karakteri işaretlenen `(1)` işlev imzalarının çifti, bir karakter *bulunana kadar,* *Str*içinde depolanana kadar *olur* .

İşaretlenen `(2)` işlev imzası çifti, varsayılan satır sınırlayıcısı olarak yeni satırı kullanır ve **getline**(`is`, `str`,, `is`) olarak davranır. `widen`(' `\n`')).

Her bir çiftin ikinci işlevi, [Rvalue başvurularını](../cpp/lvalues-and-rvalues-visual-cpp.md)desteklemeye yönelik bir analog ' dur.

Aşağıdakilerden biri gerçekleştiğinde ayıklama işlemi duraklar:

- Dosyanın sonunda, iç durum bayrağı olarak  `ios_base::eofbit`ayarlanır.

- İşlev, eşit olarak karşılaştırıldığı bir öğeyi ayıkladıktan `delim`sonra, bu durumda öğe hiçbir şekilde geri yerleştirmez veya denetimli diziye eklenmez.

- İşlev `str.` [max_size](../standard-library/basic-string-class.md#max_size) öğelerini ayıkladıktan sonra, bu durumda iç durum bayrağı olarak `ios_base::failbit`ayarlanır.

- Daha önce listelenenden farklı bir hata oluştu, bu durumda iç durum bayrağı *Şu* şekilde ayarlanır`ios_base::badbit`

İç durum bayrakları hakkında daha fazla bilgi için bkz. [ios_base:: iostate](../standard-library/ios-base-class.md#iostate).

İşlev hiçbir öğe ayıkladıysanız, iç durum bayrağı olarak  `ios_base::failbit`ayarlanır. Herhangi bir durumda, `getline` ' *i döndürür.*

Bir özel durum oluşturulursa *, ve* *Str* geçerli bir durumda bırakılır.

### <a name="example"></a>Örnek

Aşağıdaki kod iki modda `getline()` göstermektedir: ilk olarak varsayılan sınırlayıcıyla (yeni satır) ve ikincisi sınırlayıcı olarak boşluk ile. While döngülerinin sonlandırılmasını denetlemek için dosya sonu karakteri (klavyede CTRL-Z) kullanılır. Bu, ' ın `cin` iç durum bayrağını, ikinci while döngüsünün düzgün şekilde çalışması için [](../standard-library/basic-ios-class.md#clear) `eofbit`basic_ios:: Clear () ile temizlenmelidir.

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

## <a name="stod"></a>stod

Bir karakter dizisini **Double**'a dönüştürür.

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
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

**Double** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, çağırarak, işlevine iç bir `val` nesne `_Eptr` olduğu  gibi, çağırarak `strtod( str.c_str(), _Eptr)`Double türünde bir değere dönüştürür. Eğer ` str.c_str() == *_Eptr` türünde`invalid_argument`bir nesne oluşturursa. Böyle bir çağrı ayarlanacaksa `errno`, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr -  str.c_str()` `*idx` depolar ve döndürür `val`.

## <a name="stof"></a>stof

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

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

Float değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, çağırarak `val` `strtof( str.c_str(), _Eptr)`, işlevinin iç bir nesnesi `_Eptr` olduğu gibi **float** türünde bir değere dönüştürür. Eğer ` str.c_str() == *_Eptr` türünde`invalid_argument`bir nesne oluşturursa. Böyle bir çağrı ayarlanacaksa `errno`, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr -  str.c_str()` `*idx` depolar ve döndürür `val`.

## <a name="stoi"></a>Stoi

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

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|Dönüşte dönüştürülmemiş ilk karakterin dizinini içerir.|
|*base*|Kullanılacak sayı temeli.|

### <a name="remarks"></a>Açıklamalar

İşlevi `stoi` *Str* içindeki karakter dizisini **int** türünde bir değere dönüştürür ve değeri döndürür. Örneğin, "10" karakter sırası geçirildiğinde, tarafından `stoi` döndürülen değer 10 ' dur.

`stoi`, işlev içinde `strtol` `_Eptr` `wcstol` çağrıldığında tek baytlık karakterlerin işlevine benzer şekilde davranır; burada işlevin iç bir nesnesidir; ya da benzer şekilde çağrıldığında çok sayıda karakter kullanılır. `strtol( str.c_str(), _Eptr, idx)` `wcstol(Str.c_str(), _Eptr, idx)`. Daha fazla bilgi için bkz. [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

İse `str.c_str() == *_Eptr`, `stoi` türünde`invalid_argument`bir nesne oluşturur. Böyle bir çağrı ayarlanır `errno`veya döndürülen değer **int**türünde bir nesne olarak temsil edimiyorsa, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr - str.c_str()` `*idx`depolar.

## <a name="stol"></a>STOL

Bir karakter dizisini **Long**değerine dönüştürür.

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
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

Uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, çağırarak, işlevinin iç bir `val` nesnesi `_Eptr` olduğu **gibi,** öğesini çağırarak `strtol( str.c_str(), _Eptr, idx)`bir değere dönüştürür. Eğer ` str.c_str() == *_Eptr` türünde`invalid_argument`bir nesne oluşturursa. Böyle bir çağrı ayarlanacaksa `errno`, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr -  str.c_str()` `*idx` depolar ve döndürür `val`.

## <a name="stold"></a>stold

Bir karakter dizisini **Long Double**'a dönüştürür.

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
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

**Long Double** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, çağırarak, işlevine iç bir `val` nesne `_Eptr` olduğu gibi, çağırarak `strtold( str.c_str(), _Eptr)` **Long Double** türünde bir değere dönüştürür. Eğer ` str.c_str() == *_Eptr` türünde`invalid_argument`bir nesne oluşturursa. Böyle bir çağrı ayarlanacaksa `errno`, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr -  str.c_str()` `*idx` depolar ve döndürür `val`.

## <a name="stoll"></a>Stoll

Bir karakter dizisini **uzun bir uzunluğa**dönüştürür.

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
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

**Uzun uzun** değer.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, çağırarak `val` `strtoll( str.c_str(), _Eptr, idx)`, işlevinin iç bir nesnesi `_Eptr` olduğu gibi **uzun uzunlukta** bir değere dönüştürür. Eğer ` str.c_str() == *_Eptr` türünde`invalid_argument`bir nesne oluşturursa. Böyle bir çağrı ayarlanacaksa `errno`, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr -  str.c_str()` `*idx` depolar ve döndürür `val`.

## <a name="stoul"></a>stoul

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

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

İşaretsiz uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, çağırarak, işlevinin iç bir `val` nesnesi `_Eptr` olduğu gibi, öğesini çağırarak `strtoul( str.c_str(), _Eptr, idx)` **işaretsiz Long** türünde bir değere dönüştürür. Eğer ` str.c_str() == *_Eptr` türünde`invalid_argument`bir nesne oluşturursa. Böyle bir çağrı ayarlanacaksa `errno`, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr -  str.c_str()` `*idx` depolar ve döndürür `val`.

## <a name="stoull"></a>stoull

Bir karakter dizisini **işaretsiz Long**Long değerine dönüştürür.

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
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

**İmzasız Long Long** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi, *Str* içindeki öğe dizisini, çağırarak, işlevinin iç bir `val` nesnesi `_Eptr` olduğu gibi, öğesini çağırarak `strtoull( str.c_str(), _Eptr, idx)` **işaretsiz uzun uzunlukta** bir değere dönüştürür. Eğer ` str.c_str() == *_Eptr` türünde`invalid_argument`bir nesne oluşturursa. Böyle bir çağrı ayarlanacaksa `errno`, türünde `out_of_range`bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlevi ' de `*_Eptr -  str.c_str()` `*idx` depolar ve döndürür `val`.

## <a name="swap"></a>Kur

İki dizenin karakter dizilerini değiş tokuş eder.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri başka bir dizeden değiştirilebilen bir dize.

*Right*\
Öğeleri ilk dizeyle takas edilecek diğer dize.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, *sol taraftaki*özelleştirilmiş üye işlevini yürütür. [takas et](../standard-library/basic-string-class.md#swap) (*sağ*) ve sabit karmaşıklığı garanti eden dizeler için.

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

## <a name="to_string"></a>to_string

Bir değeri öğesine `string`dönüştürür.

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
|*Acil*|Dönüştürülecek değer.|

### <a name="return-value"></a>Dönüş Değeri

`string` Değeri temsil eder.

### <a name="remarks"></a>Açıklamalar

İşlevi, öğesini çağırarak `sprintf(Buf, Fmt, Val)`bir dizi nesnesinde `Buf` depolanan bir öğe *dizisine dönüştürür,* burada `Fmt` olduğu gibi

- `"%d"`Eğer `Val` tür **int** ise

- `"%u"`Eğer `Val` tür **işaretsiz int** ise

- `"%ld"`Eğer `Val` tür **Long** ise

- `"%lu"`Eğer `Val` tür **imzasız Long** ise

- `"%lld"`Eğer `Val` tür **uzun uzunsa**

- `"%llu"`Eğer `Val` tür **imzasız uzun uzunsa**

- `"%f"`Eğer `Val` **float** veya **Double** türünde

- `"%Lf"`Eğer `Val` tür **Long Double** ise

İşlev döndürür `string(Buf)`.

## <a name="to_wstring"></a>to_wstring

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

İşlevi, öğesini `Val` çağırarak `Buf` `swprintf(Buf, Len, Fmt, Val)`bir dizi nesnesinde depolanan bir öğe dizisine dönüştürür; burada `Fmt`

- `L"%d"`Eğer `Val` tür **int** ise

- `L"%u"`Eğer `Val` tür **işaretsiz int** ise

- `L"%ld"`Eğer `Val` tür **Long** ise

- `L"%lu"`Eğer `Val` tür **imzasız Long** ise

- `L"%lld"`Eğer `Val` tür **uzun uzunsa**

- `L"%llu"`Eğer `Val` tür **imzasız uzun uzunsa**

- `L"%f"`Eğer `Val` **float** veya **Double** türünde

- `L"%Lf"`Eğer `Val` tür **Long Double** ise

İşlev döndürür `wstring(Buf)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)
